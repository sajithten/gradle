pipeline{
    agent any
    stages{
        stage("sonar quality check"){
           agent {
                docker {
                    image 'openjdk:17'
                }
            }
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'sonar-password') {
                      sh 'chmod +x gradlew'
                      sh './gradlew sonarqube'
                }
            }
        }
    }
}
}