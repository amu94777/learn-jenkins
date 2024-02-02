
pipeline {
    agent {
       node {
        label 'AGENT-1'
        
       }
    }
    // environment variables //
    environment { 
        GREETING = 'good morning'
    }

    // build ///
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                sh """
                 echo "I write shell script here"
                 env
                 echo "$GREETING"
                 """
            }
        }
    }
    /// post //
     post { 
        always { 
            echo 'I will always say Hello again!'
        }
        success {
            echo 'i will always tell hiii when pipeline is success'
        }
        failure {
            echo ' i will say check once when pipeline is failure'
        }    
} 
    }

