pipeline {
    agent {
        node {
            label 'maven'
        }
    }
    stages {
        stage('Tests') {
            sh './mvnw clean test'
        }
        stage('Package') {
            sh '''
            ./mvnw package -DskipTests \
            -Dquarkus.package.type=uber-jar
            '''
            archiveArtfacts 'target/*.jar'
        }
    }
}