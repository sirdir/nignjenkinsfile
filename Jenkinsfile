pipeline {
    agent any

    stages {

        stage('Cleanup') {
            steps {
                sh 'pwd'
            }
        }

        stage('Checkout') {
            steps {
                git branch: 'master',
                        credentialsId: 'xuynana',
                        url: 'git@github.com:sirdir/nignjenkinsfile.git'
            }
        }

        stage('ls') {
            steps {
                sh 'ls -la'
            }
        }

//        stage('Cleanup') {
//            steps {
//                sh 'rm -rf *'
//            }
//        }

        stage('Build Maven') {
            steps {
                mvnHome = tool 'M3'
                if (isUnix()) {
                    sh "'${mvnHome}/bin/mvn' clean test"
                }
            }
        }
    }
}