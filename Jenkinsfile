pipeline{
    agent { label 'AGENT-1' } //jenkins node name
    environment{
        PROJECT = 'EXPENSE'     //We can use these as global variables
        COMPONENT = 'BACKEND'
    }
    options{
        disableConcurrentBuilds()
    }
    stages{
        stage('build'){
            steps{
                script{
                    sh """
                        echo "Hello, this is build"
                        echo "Project: $PROJECT"
                        sleep 15
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