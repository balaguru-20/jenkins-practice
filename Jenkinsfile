pipeline{
    agent { label 'AGENT-1' }
    stages{
        stage('build'){
            steps{
                script{
                    sh """
                        echo "Hello, this is build"
                    """
                }
            }
        }
        stage('Test'){
            steps{
                script{
                    sh """
                        echo "Hello, this is test"
                    """
                }
            }
        }
        stage('Deploy'){
            steps{
                sh """
                    echo "Hello, this is deploy"
                """
            }
        }
    }
    post{
        always{
            echo 'I will always say Hello again!'
        }
        failure{
            echo 'I will run when pipeline is failed'
        }
        success{
            echo 'I will run when pipeline is success'
        }
    }
}