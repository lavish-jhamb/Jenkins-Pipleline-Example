// pipeline{
//     agent any
//
//     stages{
//
//         stage("compile"){
//             steps{
//                 bat 'javac Main.java'
//             }
//         }
//
//         stage("run"){
//             steps{
//                 bat 'java Main'
//             }
//         }
//
//     }
//
//     post{
//         always{
//             bat 'echo "always"'
//         }
//
//         success{
//             bat 'echo "success"'
//         }
//
//         failure{
//             bat 'echo "failure"'
//         }
//     }
// }

pipeline{
    agent any

    environment {
        NAME = "Lavish"
    }

    parameters {
      string defaultValue: 'DEMO', name: 'LASTNAME'
    }

    stages{

        stage("Compile"){
            steps{
                bat 'echo "compile step"'
            }
        }

        stage("Test"){
        parallel{
            stage("Test A"){
                steps{
                    echo "This is Test A"
                }
            }

            stage("Test B"){
                steps{
                    echo "This is Test B"
                }
            }
        }
            steps{
                bat 'echo "Test Step"'
            }
        }

        stage("Deploy"){
            steps{
                bat 'echo "Deploy Step"'
            }
        }

        stage("Execute Env variables"){
            steps{
                echo "Hello $NAME ${params.LASTNAME}"
            }
        }
    }
}