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
                echo "Installing dependencies"
                sh  '''
                python3 -m venv venv
                . ./venv/bin/activate
                cd myapp 
                pip install -r requirements.txt
                '''
            }
        }
        stage('Testing stage') {
            steps {
                echo "This is the testing stage"
                sh '''
                    cd myapp
                    python3 hello.py
                    python3 hello.py --name=Enmanuel
                '''
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
