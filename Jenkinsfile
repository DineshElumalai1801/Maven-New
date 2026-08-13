pipeline {
    agent {
        label 'Linux1'
    }

    tools {
        maven 'Maven 3.9.16'
    }

    stages {

       stage ('Maven check')
       {
        steps {
            sh 'mvn -version'
        }
       } 

       stage ('Docker check')
       {
        steps {
            sh 'docker --version'
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
