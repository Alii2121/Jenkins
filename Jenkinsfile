pipeline {
    agent any

    

    stages {
        
         stage('Checkout external proj') {
        steps {
            git branch: 'main',
                credentialsId: '3821e5e2-8b79-4097-b2ab-85398faae8c2',
                url: 'https://github.com/Alii2121/Private_Jenkins.git'

            sh "ls -lat"
        }
    }
        
