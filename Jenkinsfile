cat <<EOF > Jenkinsfile
pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/SRIKANTHGOWDA2003/sample-devops-project.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t sample-devops-app:latest .'
            }
        }
        stage('Run Container') {
            steps {
                sh '''
                docker rm -f sample-devops-app || true
                docker run -d --name sample-devops-app -p 8080:8080 sample-devops-app:latest
                '''
            }
        }
    }
}
EOF
