pipeline {
    agent any
    environment {
     name = 'Vinod'
    }
    parameters {
        string(name: 'person', defaultValue: 'Vinod Kumar', description: "Who are you ?")
        booleanParam(name: 'isMale', defaultValue: true, description: "")
        choice(name: 'City', choices: ['Jammu', 'Chandigarh', 'Delhi'], description: "")
    }
    stages {
        stage('Run  a Command') {
            steps {
                sh 'date'
                sh 'pwd'
            }
        }
        stage('Environment Variable') {
             environment {
                username = 'Lucky'
    }
            steps {
                sh 'echo "$BUILD_ID"'
                sh 'echo "$name"'
                sh 'echo "$username"'
            }
        }
        stage('Parameters') {
            steps {
                echo 'Deploy on test'
                sh 'echo "$username"'
                sh 'echo "$person"'
                sh 'echo "$isMale"'
                sh 'echo "$City"'
            }
        }
        stage('Continue ?') {
            input{
            message"Should we continue?"
            ok "Yes we should"
        }
            steps {
                echo 'Deploy on prod'
            }
        }
        stage('Deploy on prod') {
            steps {
                echo 'Deploy on prod'
            }
        }
    }
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
        failure { 
            echo 'failure'
        }
        success { 
            echo 'Success'
        }
    }    
}
