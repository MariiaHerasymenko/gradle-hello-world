pipeline {
    agent {
        label 'worker'
    }
    tools {
        gradle 'gradle4'
    }
    stages {
        stage('checkout') {
            steps {
                checkout scm
            }
        }
        stage('build') {
            steps {
                echo "Path is" + env.PATH
                sh "gradle build"
            }
        }
    }
    post {
        success {
            addBadge(icon: 'green.gif', text: 'SUCCESS')
        }
        failure {
            addBadge(icon: 'red.gif', text: 'FAILURE')
        }
    }
}
