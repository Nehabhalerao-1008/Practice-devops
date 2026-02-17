pipeline{
    agent any
    stages{
        stage('checkout') {
            steps{
                checkout scm
            }
        }
        stage('install dependencies') {
            steps{
                bat 'npm install'
            }
        }
        stage('build'){
            steps{
                bat 'npm run build'
            }
        }
        stage('archive artifacts') {
            steps{
                archiveArtifacts artifacts: 'dist/**', fingerprint: true
            }
        }
    }
    post {
        always {
            cleanWs()
        }
    }
}