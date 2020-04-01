pipeline {
    agent any
     
    stages {
        stage('initialize') {
            steps {
                echo "ok"
            }
        }

         stage('checkout') {
            steps {
                git url:'https://github.com/newmaxx/online-shopping.git'
            }
        }
        
    }
    
    post {
        always {
            emailext body: 'A Test EMail', recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'RequesterRecipientProvider']], subject: 'Test'
        }
    }
}
