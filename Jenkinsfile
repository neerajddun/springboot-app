pipeline {
    agent any

    tools {
        maven 'Maven 3.9.4'
        jdk 'jdk 17'
    }

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/neerajddun/springboot-app.git', branch: 'master'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package -DskipTests'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                sh 'java -jar target/springboot-app-0.0.1-SNAPSHOT.jar &'
            }
        }
    }
}
