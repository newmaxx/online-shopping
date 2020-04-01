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
        
        stage('compile-package') {
            steps {
                def mavenhome = tool name: 'maven_3_6_3', type: 'maven'
                sh "${mavenhome}/bin/mvn package"
            }
        }
        
    }
    
    post {
        always {
            emailext body: 'A Test EMail', recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'RequesterRecipientProvider']], subject: 'Test'
        }
    }
}
