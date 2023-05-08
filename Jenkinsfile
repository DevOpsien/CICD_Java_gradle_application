pipeline{
    agent any
    stages{
        stage("sonar qualtity check "){
            agent {
                docker {
                    image 'openjdk:11'
                }
            }
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'sonar-server') {
                            sh 'chmod +x gradlew'
                            sh './gradlew sonarqube --stacktrace'
                    }

                }
            }
    }
    
}
}