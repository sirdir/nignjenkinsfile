pipeline {
    agent any

    stages {

        stage('Cleanup') {
            steps {
                sh 'pwd'
            }
        }

        stage('ls 1') {
            steps {
                sh 'ls -la'
            }
        }

        stage('Checkout') {
            steps {
                git branch: 'master',
                        credentialsId: 'xuynana',
                        url: 'git@github.com:sirdir/nignjenkinsfile.git'
            }
        }

        stage('ls 2') {
            steps {
                sh 'ls -la'
            }
        }

        stage('Cleanup') {
            steps {
                sh 'rm -rf *'
            }
        }


        stage('ls 3') {
            steps {
                sh 'ls -la'
            }
        }


        stage('make dir') {
            steps {
                sh 'mkdir selenium'
            }
        }


        stage('ls 4') {
            steps {
                sh 'ls -la'
            }
        }

//        stage('Build Maven') {
//            steps {
//                sh "'/home/kubai/soft/apache-maven-3.5.2/bin/mvn' clean test"
//            }
//        }
    }
}