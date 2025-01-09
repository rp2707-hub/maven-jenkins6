pipeline {
    agent any
    tools {
        maven 'maven'
        jdk 'java'
    }
    stages {
        stage('Download code from Git') {
            steps {
                git branch: 'main', url: 'https://github.com/rp2707-hub/maven-jenkins6.git'
            }
        }
        stage('Build java project') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Archvive artifacts') {
            steps {
                archiveArtifacts artifacts: '**/*.war', followSymlinks: false
            }
        }
    }
}
