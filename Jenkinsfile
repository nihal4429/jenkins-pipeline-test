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
                // Create deploy_dir and index.html
                sh '''
                    mkdir deploy_dir
                    echo ^<html^>^<head^>^<title^>My App^</title^>^</head^>^<body^>^<h1^>Hello from Jenkins Pipeline!^</h1^>^</body^>^</html^> > deploy_dir\\index.html
                '''
                script {
                    def jenkinsHost = "localhost:8080"
                    def url = "http://${jenkinsHost}/job/${env.JOB_NAME}/${env.BUILD_NUMBER}/ws/deploy_dir/index.html"
                    echo "✅ Your app is ready! Open this URL in browser:"
                    echo "👉 ${url}"
                }
            }
        }
    }
}
