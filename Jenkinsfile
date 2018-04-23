pipeline {
    agent any

    stages {

        stage('sys env') {
            steps {
                sh 'echo $env.JIRA_ISSUE_KEY'
                sh 'echo ${env.JIRA_ISSUE_KEY}'
            }
        }
        stage('Cleanup 1') {
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

        stage('Cleanup 2') {
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
                sh 'cd selenium'
                git branch: 'master',
                        credentialsId: 'xuynana',
                        url: 'git@github.com:sirdir/nngsecondrepo.git'
                sh "'/home/kubai/soft/apache-maven-3.5.2/bin/mvn' clean test"
            }
        }

//        stage('Build Maven') {
//            steps {
//                sh "'/home/kubai/soft/apache-maven-3.5.2/bin/mvn' clean test"
//            }
//        }
    }
}