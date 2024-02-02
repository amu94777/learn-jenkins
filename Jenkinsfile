
pipeline {
    agent {
       node {
        label 'AGENT-1'
        
       }
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
        stage('Deploy') 
            steps {
                echo 'Deploying...my project.'
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

