pipeline {
    agent { 
        node {
            label 'docker-agent-python' }
    }
    triggers {
   
        pollSCM('*/5 * * * *')
    }
         
    stages {
        stage('Hello World') {
            steps {
                echo "Executing shell hello world"
                sh  'echo "hello world"'
            }
        }
        stage('Testing stage') {
            steps {
                echo "This is the testing stage"
                sh 'echo "Testing stage"'
            }
        }
        stage('Final stage') {
            steps {
                echo 'Final stage'
                sh 'echo "This is the final stage bye bye"'
            }
        }
    }
}
