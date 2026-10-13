
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                bat 'if not exist build mkdir build'
                bat 'javac -d build Hello.java'
            }
        }

        stage('Test') {
            steps {
                bat 'java -cp build Hello'
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'build/**/*.class',
                                 fingerprint: true
            }
        }
    }
}
