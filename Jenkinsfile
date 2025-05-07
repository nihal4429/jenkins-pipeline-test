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
                sh '''
                    mkdir -p deploy_dir
                    cp index.html deploy_dir/
                    cd deploy_dir
                    nohup python3 -m http.server 5000 &
                '''
            }
        }
    }
}
