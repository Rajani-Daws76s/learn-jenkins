pipeline {
    agent {
        node {
            label 'Agent-1'
        }
    }
    environment { 
        GREETING = 'Hello Jenkins'
    }
    // used to get timeour if it takes more than a second
    options {  
        timeout(time: 1, unit: 'HOURS')
        disableConcurrentBuilds() # it will not aloow you to run multiple buils at a time
    }
    //build
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
                     echo  "Here I wrote shell script"
                    echo "$GREETING"
                    sleep 10
                """
            }
        }
    }
// post build
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
        failure { 
            echo 'this runs when pipeline is failed, used generally to send some alerts'
        }
        success{
            echo 'I will say Hello when pipeline is success'
        }
    }
}

