pipeline {
    agent any
    tools {
        maven 'M3'
    }
    stages {
        stage('chckout') {
            steps {
                git credentialsId: 'ae6b5a8b-878e-4311-83bb-45d0d35e2550', 
                git branch: 'main', url: 'https://github.com/HarrySewak/spring-petclinic.git'
            }
        }
        stage('build') {
            steps {
                sh 'mvn compile'
            }
        }
        stage('test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('package') {
            steps {
                sh 'mvn package'
            }
        }

stage('deploy') {
    steps {
        sh 'java -jar /home/coder/.jenkins/workspace/PetclinicDeclarativePipeline/target/*.jar'
    }
}
    }
}
