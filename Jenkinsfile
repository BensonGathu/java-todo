 pipeline {
     agent any
     tools {
         gradle 'Gradle-6'
     }
     stages {
         stage ('Clone repository'){
         steps {
             git 'https://github.com/BensonGathu/java-todo'
         }
         }
         stage ('Build the project'){
             steps{
             sh 'gradle build'
                 
             }
         }
         stage ('Test'){
             steps{
                 sh 'gradle test'
             }
         }
    stage('Deploy to Heroku') {
  steps {
    withCredentials([usernameColonPassword(credentialsId: 'heroku', variable: 'HEROKU_CREDENTIALS' )]){
       
      sh 'git push https://${HEROKU_CREDENTIALS}@git.heroku.com/secret-cove-22020.git master'
    }
  }
} 
    }
 }

