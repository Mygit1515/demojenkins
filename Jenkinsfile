pipeline {
    agent any
    environment {
        name = "bhavna"
    }
    parameters {
        string(name: 'person', defaultValue: 'Seema Singh', description: "who are you?")
        booleanParam(name: 'isMale', defaultValue: true, description: "")
        choice(name: 'City', choices: ['Jaipur', 'Mumbai', 'Pune'], description: "")
    } 

    stages {
        stage('Run A command') {
            steps {
                sh '''
                ls
                date
                pwd
                '''
            }
        }
        stage('Environment Variables') {
            environment {
                username = 'zara'
            }
            steps {
                sh 'echo "${BUILD_ID}"'
                sh 'echo "${name}"'
                sh 'echo "${username}"'
            }
        }
        stage('Parameters') {
            steps {
                echo 'deploy on test'
                sh 'echo "${name}"'
                sh 'echo "${person}"'
            }
        }
        stage('Continue') {
            steps {
                input message: "Should we continue?", ok: "Yes we should"
            }
        }    
        stage('Deploy on prod') {
            steps {
                echo 'deploy on prod'
            }
        }
    }
    
    post {
        always {
            echo "I will always say Hello again!"
        }
        failure{
            echo "Failure"
        }
        success {
            echo "Success"
        }
    }
}
