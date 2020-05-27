pipeline {
    agent any
    options {
        buildDiscarder(logRotator(daysToKeepStr: '1', numToKeepStr: '5', artifactDaysToKeepStr: '2', artifactNumToKeepStr: '1')
    }
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
        stage('sleep') {
            steps {
                sleep(time: 1, unit: 'MINUTES')
                echo('Hello world')
            }
        }
    }
}