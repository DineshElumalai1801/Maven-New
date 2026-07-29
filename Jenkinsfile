pipeline{
    agent any
    stages{
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage ('Sonar-Qube') {
            steps {
                withSonarQubeEnv('sonar') {
                    sh 'mvn sonar:sonar'
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
