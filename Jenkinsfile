pipeline{
    agent any

    stages{
        stage('Check Requirements'){
            steps{
                sh'sudo apk update; sudo apk install python3 python3-pip'
                sh'pip3 install flask pylint'
            }
        }
        stage('Code Analysis'){
            steps{
                sh' python3 -m pylint app.py'
            }
        }
        stage('RUN'){
            steps{
                sh' python3 app.py &'
            }
        }
        stage('Test Run'){
            steps{
                sh' curl localhost:5000'
            }
        }

    }
    post{
        always{
            
        echo 'We have reached the post stage'
        }
        }
}
