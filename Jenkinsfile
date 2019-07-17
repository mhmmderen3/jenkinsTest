pipeline{
    agent any

    stages{
        stage('Compile Stage'){

            steps{
                withMaven(maven : 'maven_3_6_0'){
                    sh 'mvn clean compile'
                }
            }
        }

          stage('Testing Stage'){

            steps{
                withMaven(maven : 'maven_3_6_0'){
                     sh 'mvn test'
                }
            }
        }

        stage('Deployment Stage'){

           steps{
              withMaven(maven : 'maven_3_6_0'){
                      sh 'mvn deploy'
                }
            }
        }

         stage('Build') {
                    steps {
                        sh 'make' (1)
                        archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true (2)
                    }
                }
    }
}