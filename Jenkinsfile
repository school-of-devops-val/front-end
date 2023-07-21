pipeline {
    agent any

    tools {
      nodejs 'NodeJS 4.8.6'
     }

    stages {
        
        /* stage('SCM-Checkout') {
            steps {
                echo 'SCM-Checkout..'
              git 'https://github.com/school-of-devops-val/front-end.git'
            }
        }
        */
        
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'npm install'
            }
         }

        stage('Test') {
            steps {
                echo 'Test Pass...'
                sh 'npm test'
            }
        }
        stage('Package') {
            steps {
                echo 'Packaging....'
                sh 'npm run package'
                archiveArtifacts artifacts: '**/distribution/*.zip', fingerprint: true
            }
        }
    }
}
