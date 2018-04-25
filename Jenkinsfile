pipeline {
    agent { docker { image 'maven:3.3.3' } }
    stages {
        stage('build') {
            steps {
                bat "echo test"
            }
        }
    }
    post {
        failure {
            mail to: 'taha.holawala@deliveryhero.com',
                 subject: "Failed Pipeline: ${currentBuild.fullDisplayName}",
                 body: "Something is wrong with ${env.BUILD_URL}"
        }   
    }
}
