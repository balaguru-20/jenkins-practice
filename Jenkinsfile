pipeline{
    agent any
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
                        echo "Hello, this is build"
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