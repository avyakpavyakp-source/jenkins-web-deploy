pipeline {
    agent any

    triggers {
        githubPush()
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/avyakpavyakp-source/jenkins-web-deploy.git'
            }
        }
        stage('Deploy') {
            steps {
                sh 'cp -r * /var/www/html/'
            }
        }
    }

    post {
        success {
            echo 'Deployment to /var/www/html/ succeeded!'
        }
        failure {
            echo 'Deployment failed!'
        }
    }
}
