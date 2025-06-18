pipeline{
    agent { label 'AGENT-1' } //jenkins node name
    environment{
        PROJECT = 'EXPENSE'     //We can use these as global variables
        COMPONENT = 'BACKEND' 
        DEPLOY_TO = "production"
    }
    options{
        disableConcurrentBuilds()  //Builds will not applt at a time
        //timeout(time: 5, unit: 'SECONDS') //timeout after some metioned time
        timeout(time: 30, unit: 'MINUTES') // generally 30 min or based on project
    }
     parameters{
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    stages{
        stage('Build'){
            steps{
                script{
                    sh """
                        echo "Hello, this is build"
                        echo "Project: $PROJECT"
                        echo "Hello ${params.PERSON}"

                        echo "Biography: ${params.BIOGRAPHY}"

                        echo "Toggle: ${params.TOGGLE}"

                        echo "Choice: ${params.CHOICE}"

                        echo "Password: ${params.PASSWORD}"
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
           /*  input {
                message "Should we continue?"
                ok "Yes, we should."
                submitter "alice,bob"
                parameters {
                    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                }
            } */
            when{
                environment name: 'DEPLOY_TO', value: 'production'
            }
            steps{
                script{
                    sh """
                        echo "Hello, this is deploy"
                    """
                }
            }
        } 
        stage('Parallel Stages'){
            Parallel{
                stage('STAGE-1'){

                    steps{
                        script{
                            sh """
                                echo "Hello, this is STAGE-1"
                                sleep 15
                            """
                        }
                    }
                }
                stage('STAGE-2'){

                    steps{
                        script{
                            sh """
                                echo "Hello, this is STAGE-2"
                                sleep 15
                            """
                        }
                    }
                }
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