pipeline {
    agent any
    environment {
        name = 'safaade'
    }
    parameters {
        string(name: 'person', defaultValue: 'Divyesh', description: 'who are you' )
        booleanParam(name: 'isMale', defaultValue: true, description: 'who are you')
        choice(name: 'City', choices: ['Mumbai','Jaipur','Chennai'], description: '')
    }

    stages{
        stage("Test"){
            steps{
                echo "====++++Test stage++++===="
                sh '''
                pwd
                ls
                date
                '''
                
            }
        }
        stage("Environment_Var"){
            steps {
                sh 'echo "${name}" '
                sh 'echo "${BUILD_ID}" '
                sh 'echo "${person}"'
                sh 'echo "${isMale}"'
                sh 'echo "${isMale}"'
            }
        }
        stage("Build"){
            steps{
                echo "====++++Build Step++++===="
            }
        }
        stage("Deploy to Dev") {
            steps{
                echo "====++++Deploying to Dev++++===="
            }
        }
        stage("continue ?") {
            input {
                message "should we continue"
                ok "yes we should"
        }
            steps {
                echo "====++++Deploy to Prod ++++===="
            }
        }
        stage("Deploy to prod") {
            steps{
                echo "====++++Deploying to prod ++++===="
            }
        }
        
    }
    post{
        always{
            echo "Hello again"
        }
        failure {
            echo "Failure"
        }
        success {
            echo "success"
        }
    }
}
