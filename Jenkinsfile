pipeline {
    agent any

    stages {

        stage('STAGE 1') {
            steps {
                sh 'sleep 5'
                echo 'This is the stage 1'
            }
        }

        stage('STAGE 2') {
            steps {
                sh '''
                pwd
                ls -lrt
                whoami
                sleep 5
                echo "This is Linux command"
                '''
            }
        }
    }
}