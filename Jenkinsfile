pipeline {
    agent {
        node {
            label "java_slave"
        }
    }
    environment {
        PATH = "/opt/maven/bin:$PATH"
    }
    stages {
        stage("build code") {
            steps {
                sh 'mvn clean install'
            }
        }
    }
    post {
        cleanup {
            echo 'Cleaning up workspace...'
            cleanWs()
        }
    }
}