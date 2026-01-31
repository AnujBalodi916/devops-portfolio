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
        sh 'docker build -t portfolio:latest .'
      }
    }

    stage('SonarQube Scan') {
      steps {
        withSonarQubeEnv('sonarqube') {
          sh '''
            docker run --rm --network host \
              -v "$PWD:/usr/src" \
              sonarsource/sonar-scanner-cli:latest \
              -Dsonar.host.url=$SONAR_HOST_URL \
              -Dsonar.login=$SONAR_AUTH_TOKEN \
              -Dsonar.projectKey=devops-portfolio \
              -Dsonar.sources=.
          '''
        }
      }
    }

    stage('Trivy Image Scan (Report Only)') {
      steps {
        sh '''
          docker run --rm \
            -v /var/run/docker.sock:/var/run/docker.sock \
            aquasec/trivy:latest image \
            --severity HIGH,CRITICAL \
            --exit-code 0 \
            portfolio:latest
        '''
      }
    }

    stage('OWASP Dependency Check (Report Only)') {
      steps {
        sh '''
          set +e
          rm -rf dependency-check-report || true
          mkdir -p dependency-check-report

          docker volume create dependency-check-data >/dev/null 2>&1 || true

          docker run --rm \
            -v "$PWD:/src" \
            -v dependency-check-data:/usr/share/dependency-check/data \
            owasp/dependency-check:latest \
            --scan /src \
            --format HTML \
            --out /src/dependency-check-report
          exit 0
        '''
      }
    }

    stage('Deploy Container') {
      steps {
        sh '''
          docker rm -f portfolio || true
          docker run -d -p 80:80 --name portfolio portfolio:latest
        '''
      }
    }
  }

  post {
    always {
      archiveArtifacts artifacts: 'dependency-check-report/**', allowEmptyArchive: true
    }
  }
}
