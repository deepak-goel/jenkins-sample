pipeline {
    agent any
    stages {

        stage('Step 1') {
            agent {
                label 'slave1'
            }
            steps {
                sh 'hostname && pwd'
                echo "This is the first step of our pipeline"
            }
        }

        // stage('Step 2') {
        //     agent {
        //         label 'master'
        //     }
        //     steps {
        //         input('Do you want to proceed?')
        //     }
        // }

        stage('Step 3') {
            agent {
                label 'master'
            }
            steps {
                sh 'hostname && pwd'
                echo "Just a regular stage. Nothing interesting here"
            }
        }

        stage('Step 4') {
            agent {
                label 'slave1'
            }
            steps {
                sh 'hostname && pwd'
                echo "Just a regular stage. Nothing interesting here"
            }
        }

        stage('Step 5') {
            parallel {
                stage('Parallel Stage 1') {
                    steps {
                        sh 'hostname && pwd'
                        echo "This is the first parallel stage"
                    }
                }
                stage('Parallel Stage 2') {
                    steps {
                        sh 'hostname && pwd'
                        echo "This is the second parallel stage"
                    }
                }
            }
        }

    }
}
