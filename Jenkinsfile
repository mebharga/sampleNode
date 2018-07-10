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
    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
            mail to: 'meha.bhargava2@gmail.com',
             subject: "Success Pipeline",
             body: "Everything is fine"
        }
        failure {
            echo 'This will run only if failed'
            mail to: 'meha.bhargava2@gmail.com',
             subject: "Failed Pipeline: ${currentBuild.fullDisplayName}",
             body: "Something is wrong with ${env.BUILD_URL}"
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
    }
