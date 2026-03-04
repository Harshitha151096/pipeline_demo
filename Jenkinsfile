pipeline{
    agent none 
    stages{
        agent ( label 'slave1' ){
            stages{
                stage('Checkout'){
                    steps{
                        echo 'Checking out...'
                    }
                }
            }
        }
        stage('Build'){
            agent ( label 'slave1' ){
            steps{
                echo 'Building...'
            }
        }
        stage('Test'){
            agent ( label 'slave2' )
            steps{
                echo 'Testing...'
            }
        }
        stage('Deploy'){
            agent ( label 'slave2' )
            steps{
                echo 'Deploying...'
            }
        }
    }   
}