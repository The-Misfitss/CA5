pipeline {
    agent any

    stages {

        stage('Check and Pull Docker Images') {
            steps {
                script {
                    // Define the image names
                    def frontendImageName = 'jawwadhabib/ca4-app:latest'
                    def backendImageName = 'jawwadhabib/ca4-postgres:latest'

                    // Check if the Docker images exist
                    def frontendImageExists = sh(script: "docker image ls -q ${frontendImageName}", returnStatus: true) == 0
                    def backendImageExists = sh(script: "docker image ls -q ${backendImageName}", returnStatus: true) == 0

                    // Pull the images if they don't exist
                    if (!frontendImageExists) {
                        sh "docker pull ${frontendImageName}"
                    }
                    if (!backendImageExists) {
                        sh "docker pull ${backendImageName}"
                    }
                }
            }
        }

        stage('Run Docker Containers') {
            steps {
                script {
                    // Run the Docker containers
                    sh "docker run -d -p 5432:5432 --name ca4-postgres jawwadhabib/ca4-postgres:latest"
                    sh "docker run -d -p 3000:5000 --name ca4-app --link ca4-postgres jawwadhabib/ca4-app:latest"
                }
            }
        }

    }

    post {
        always {
            // Stop and remove the Docker containers
            sh "docker stop ca4-app ca4-postgres"
            sh "docker rm ca4-app ca4-postgres"
        }
    }
}
