pipeline{
    agent {
        docker maven:3.9.11-eclipse-temurin-21
    }
    stages{
        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }
        stage ('Sonar-Qube') {
            steps {
                withSonarQubeEnv('sonar') {
                    bat 'mvn sonar:sonar'
                }
            }
        }

        stage ('Quality-Gate') {
            steps {
                timeout(time:5, unit:'MINUTES') {
                    waitForQualityGate abortPipeline: true
                }
            }
        }
    }
}
