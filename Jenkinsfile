pipeline {
    agent {
        docker {
        label 'Linux1'
        image 'maven:3.9.11-eclipse-temurin-21'
    }
    stages {

       stage ('Maven check')
       {
        steps {
            sh 'mvn -version'
        }
       } 
       stage ('git check')
       {
        steps {
            sh 'git --version'
        }
       }
    }
}
