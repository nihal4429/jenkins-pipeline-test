pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the project...'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                
                // Create deploy_dir and add an index.html inside
                sh '''
                    mkdir -p deploy_dir
                    echo "<!DOCTYPE html><html><head><title>My App</title></head><body><h1>Hello from Jenkins Pipeline!</h1></body></html>" > deploy_dir/index.html
                '''
                
                script {
                    // Print URL for user to open
                    def url = "${env.BUILD_URL}ws/deploy_dir/index.html"
                    echo "✅ Your app is ready! Open this URL in a new tab:"
                    echo "👉 ${url}"
                }
            }
        }
    }
}
