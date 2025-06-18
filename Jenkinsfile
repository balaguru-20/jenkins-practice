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
}