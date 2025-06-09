pipeline {
    agent { label "my-node" }

    stages {
        stage('code clone') {
            steps {
                git url: "https://github.com/arunp-123/django-travel-application.git", branch: "master"
            }
        }
            stage('Build Stage') {
            steps {
                sh "docker build -t arun1278/django-backend:v1 ."
            }
        }

            stage('Deploy') {
            steps {
                echo "docker container deploying..."
                sh "docker run --name my-django-application -d -p 8001:8000 arun1278/django-backend:v1"
            }
        }
    }
}
