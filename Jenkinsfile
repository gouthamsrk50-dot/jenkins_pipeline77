pipeline{
    agent any

    stages {

        stage('Build') {
            steps {
                echo "Building..."
                sh 'sleep 3'
            }
        }

        stage('Test') {
            steps {
                echo "Testing..."
                sh 'sleep 2'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying....."
            }
        }
    }
}
