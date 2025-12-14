pipeline {
    agent any

    tools {
        jdk 'JAVA_HOME'
        maven 'M2_HOME'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/sirine259/atelier-jenkins-pipeline.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }
    }
}
