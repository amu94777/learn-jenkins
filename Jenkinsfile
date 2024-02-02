
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
    // give time limits to run pipeline //
    options {
        timeout(time: 1, unit: 'SECONDS') 
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
                 sleep 10
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

