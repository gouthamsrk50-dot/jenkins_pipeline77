// pipeline{
//     agent any

//     stages {

//         stage('Build') {
//             steps {
//                 echo "Building..."
//                 sh 'sleep 3'
//             }
//         }

//         stage('Test') {
//             steps {
//                 echo "Testing..."
//                 sh 'sleep 2'
// //             }
// //         }

// //         stage('Deploy') {
// //             steps {
// //                 echo "Deploying....."
// //                 sh 'sleep 5'
// //             }
// //         }
// //     }
// // }

// // pipeline {
// //     agent any
// //     parameters {
// //         string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

// //         text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

// //         booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

// //         choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

// //         password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
// //     }
// //     stages {
// //         stage('Example') {
// //             steps {
// //                 echo "Hello ${params.PERSON}"

// //                 echo "Biography: ${params.BIOGRAPHY}"

// //                 echo "Toggle: ${params.TOGGLE}"

// //                 echo "Choice: ${params.CHOICE}"

// //                 echo "Password: ${params.PASSWORD}"
// //             }
// //         }
// //     }
// // }

// pipeline {
//     agent any
//     environment{
//         APP_NAME = "INSTAGRAM"
//         ENV = "dev"
//     }

//     stages {
//         stage('print') {
//             steps {
//                 echo "Application: ${APP_NAME}"
//                 echo "Environment: ${ENV}"
//             }
//         }
//     }
// 
// 

// pipeline {
//     agent any

//     environment {
//         AWS_DEFAULT_REGION = "ap-south-1"
//     }

//     stages {

//         stage('Authenticate AWS') {
//             steps {
//                 sh '''
//                 echo "Checking AWS Identity"
//                 aws sts get-caller-identity
//                 echo "Region: $AWS_DEFAULT_REGION"
//                 '''
//             }
//         }

//     }
// }

pipeline {
    agent any

    environment {
        AWS_DEFAULT_REGION = "ap-south-1"
    }

    stages {

        stage('Authenticate AWS') {
            steps {
                withCredentials([[
                    $class: 'AmazonWebServicesCredentialsBinding',
                    credentialsId: 'aws-creds'
                ]]) {

                    sh '''
                    echo "Checking AWS Authentication..."

                    USERNAME=$(aws sts get-caller-identity \
                    --query Arn \
                    --output text | cut -d'/' -f2)

                    echo "Authenticated AWS User: $USERNAME"
                    echo "Region: $AWS_DEFAULT_REGION"
                    '''
                }
            }
        }

    }
}