pipeline {
    agent {
        docker {
            image 'dineshelumalai1810/maven:v1'
        }
    }

    stages {

        stage('Maven check') {
            steps {
                sh 'mvn -version'
            }
        }

        stage('Git check') {
            steps {
                sh 'git --version'
            }
        }
    }
}
