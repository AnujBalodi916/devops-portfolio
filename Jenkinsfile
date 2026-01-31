pipeline {
  agent any

  environment {
    IMAGE_NAME = "portfolio:latest"
    SONAR_PROJECT_KEY = "devops-portfolio"
  }

  stages {

    stage('Clone Repo') {
      steps {
        git credentialsId: 'github-creds',
            url: 'https://github.com/AnujBalodi916/devops-portfolio.git',
            branch: 'main'
      }
    }

    stage('Build Docker Image') {
      steps {
        sh "docker build -t ${IMAGE_NAME} ."
      }
    }

    stage('SonarQube Scan') {
      steps {
        withSonarQubeEnv('sonarqube') {
          sh """
            docker run --rm --network host \
              -e SONAR_HOST_URL=$SONAR_HOST_URL \
              -e SONAR_LOGIN=$SONAR_AUTH_TOKEN \
              -v "\$PWD:/usr/src" \
              sonarsource/sonar-scanner-cli:latest \
              -Dsonar.projectKey=${SONAR_PROJECT_KEY} \
              -Dsonar.sources=.
          """
        }
      }
    }

    stage('Trivy Image Scan') {
      steps {
        sh """
          docker run --rm \
            -v /var/run/docker.sock:/var/run/docker.sock \
            aquasec/trivy:latest image \
            --severity HIGH,CRITICAL \
            --exit-code 1 \
            ${IMAGE_NAME}
        """
      }
    }

    stage('OWASP Dependency Check') {
      steps {
        sh """
          rm -rf dependency-check-report || true
          mkdir -p dependency-check-report

          docker volume create dependency-check-data >/dev/null 2>&1 || true

          docker run --rm \
            -v "\$PWD:/src" \
            -v dependency-check-data:/usr/share/dependency-check/data \
            owasp/dependency-check:latest \
            --scan /src \
            --format "HTML" \
            --out /src/dependency-check-report
        """
      }
    }

    stage('Deploy Container') {
      steps {
        sh """
          docker rm -f portfolio || true
          docker run -d -p 80:80 --name portfolio ${IMAGE_NAME}
        """
      }
    }
  }

  post {
    always {
      archiveArtifacts artifacts: 'dependency-check-report/**', allowEmptyArchive: true
    }
  }
}

