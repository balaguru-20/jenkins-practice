pipeline{
    agent { label 'AGENT-1' } //jenkins node name
    environment{
        PROJECT = 'EXPENSE'     //We can use these as global variables
        COMPONENT = 'BACKEND'
    }
    options{
        disableConcurrentBuilds()  //Builds will not applt at a time
        //timeout(time: 5, unit: 'SECONDS') //timeout after some metioned time
        timeout(time: 30, unit: 'MINUTES') // generally 30 min or based on project
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