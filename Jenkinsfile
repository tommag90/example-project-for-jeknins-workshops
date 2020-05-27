pipeline {
    agent any
    tools {
        maven 'MavenJenkins'
    }

    stages {
        stage('env info') {
            steps {
                bat 'java --version'
            }
        }
        stage('build') {
            steps {
                bat 'mvn compile'
                bat 'mvn package'
            }
        }
    }
}