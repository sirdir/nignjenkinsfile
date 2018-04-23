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
                sh "'/home/kubai/soft/apache-maven-3.5.2/bin/mvn' clean test"
            }
        }
    }
}