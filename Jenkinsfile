
pipeline {
    agent any
    stages {
        stage('pre-start'){
            steps{
                sh 'npm install'
            }
        }
        stage('start') {
            steps {
                sh 'npm start'

            }
        }
    }
    post{
        success{
            echo 'okay'
        }
        failure{
           echo 'not oaky'
        }
    }
}