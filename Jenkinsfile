pipeline{
    agent any

    stages{
        stage("STAGE 1") {
            step1{
                sh 'sleep 5'
                echo "This is the stage 1"
            }
        }
 stage("STAGE 2") {
            step2{
                sh '''
                #!/bin/bash
                pwd
                ls -lrt
                whoami
                sleep 5
                echo "This is Linux command"
                '''
                echo "This is the stage 2"
                
            }
        }
    }
}
