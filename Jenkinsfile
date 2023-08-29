pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                url: 'https://github.com/TaemHam/source-maven-java-spring-hello-webapp.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Deploy') {
            steps {
                deploy adapters: [tomcat9(credentialsId: '20e72f78-6260-424d-b518-51e960b3656d', path: '', url: 'http://ec2-54-173-227-101.compute-1.amazonaws.com:8081')], contextPath: null, war: 'target/hello-world.war'
            }
        }
    }
}

