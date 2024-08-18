pipeline {
    agent { label 'jenkins-agent' }

    tools {
        maven 'maven'
    }

    stages {

        stage('checkout'){
            steps {
                git branch: 'main', url: 'https://github.com/nilupabatawala/spring-petclinic.git'
            }
        }

        stage('Build') {
            steps {
                sh "mvn clean install -DskipTests"
            }
        }
        stage('UnitTest') {
            steps {
                sh "mvn test"
            }
        }
        stage('Integration Test') {
            steps {
                sh 'mvn verify'
            }
        }
    }
}