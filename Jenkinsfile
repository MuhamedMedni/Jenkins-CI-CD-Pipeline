pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    if (env.BRANCH_NAME == 'main' || env.BRANCH_NAME == 'development' || env.BRANCH_NAME.startsWith('feature/')) {
                        echo "Building ${env.BRANCH_NAME}"
                        sh 'pip install -r requirements.txt'
                    }
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    if (env.BRANCH_NAME == 'main' || env.BRANCH_NAME == 'development' || env.BRANCH_NAME.startsWith('feature/')) {
                        echo "Testing ${env.BRANCH_NAME}"
                        sh 'pytest'
                    }
                }
            }
        }
        stage('Deploy') {
            when {
                branch 'main'
            }
            steps {
                script {
                    echo "Deploying ${env.BRANCH_NAME}"
                    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub-credentials') {
                        def app = docker.build("your-dockerhub-username/your-app:${env.BUILD_ID}")
                        app.push()
                    }
                }
            }
        }
    }
    post {
        always {
            echo 'Cleaning up...'
            deleteDir()
        }
    }
}
