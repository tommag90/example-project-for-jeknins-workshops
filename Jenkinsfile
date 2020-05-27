pipeline {
    agent any
    tools {
        maven 'MavenJenkins'
    }

    options {
        steps {
            buildDiscarder(logRotator(daysToKeepStr: '1', numToKeepStr: '5', artifactDaysToKeepStr: '2', artifactNumToKeepStr: '1')
        }
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
        stage('sleep') {
            steps {
                sleep(time: 1, unit: 'MINUTES')
                echo('Hello world')
            }
        }
    }
}