pipeline {
    agent any
    stages {

        stage('Step 1') {
            steps {
                echo "This is the first step of our pipeline"
            }
        }

        stage('Step 2') {
            steps {
                input('Do you want to proceed?')
            }
        }

        stage('Step 3') {
            steps {
                echo "Just a regular stage. Nothing interesting here"
            }
        }

        stage('Step 4') {
            parallel {
                stage('Parallel Stage 1') {
                    steps {
                        echo "This is the first parallel stage"
                    }
                }
                stage('Parallel Stage 2') {
                    steps {
                        echo "This is the second parallel stage"
                    }
                }
            }
        }

    }
}
