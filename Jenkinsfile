pipeline {
    agent any
    
    stages {
        stage('Build') {
            // No agent specified here, it will use the global 'agent any'
            steps {
                // Use the docker global variable to run inside a container
                docker.image('node:18-alpine').inside {
                    sh '''
                        ls -la
                        node --version
                        npm --version
                        npm ci
                        npm run build
                        ls -la
                    '''
                }
            }
        }
    }
}