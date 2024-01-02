pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    // Build Docker image with a specific tag
                    docker.build('tejasudarshan58/my-app-1.0-snapshot', '-t tejasudarshan58/my-app-1.0-snapshot:latest .')
                }
            }
        }
        stage('Push to Registry') {
            steps {
                script {
                    // Push Docker image to the registry
                    docker.withRegistry('https://index.docker.io/v1/', 'tejasudarshan58') {
                        docker.image("tejasudarshan58/my-app-1.0-snapshot").push()
                    }
                }
            }
        }
        // Add more stages as needed
    }
    // Add post-build actions as needed
}


