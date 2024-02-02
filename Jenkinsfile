
pipeline {
    agent {
       node {
        label 'AGENT-1'
        
       }
    }
    // parameter //
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: 'i am a writer', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    // environment variables //
    environment { 
        GREETING = 'good morning'
    }
    // give time limits to run pipeline //
    options {
        timeout(time: 1, unit: 'HOURS') 
        disableConcurrentBuilds() 
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
                 # sleep 10
                 """
            }
        }

         stage('params check') {
            steps {
                echo "Hello ${params.PERSON}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"
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

