pipeline{
    agent any

    stages{

        stage("compile"){
            steps{
                bat 'javac Main.java'
            }
        }

        stage("run"){
            steps{
                bat 'java Main'
            }
        }

    }

    post{
        always{
            bat 'echo "always"'
        }

        success{
            bat 'echo "success"'
        }

        failure{
            bat 'echo "failure"'
        }
    }
}