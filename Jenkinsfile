pipeline {
 agent any
 stages {
 stage('Build') {
 steps {
 echo 'Building..'
 sh 'mvn clean compile'
 }
 }
 stage('Test') {
 steps {
 echo 'Testing..'
 sh 'mvn test'
 }
 }
 stage('Deploy') {
 steps {
 echo 'Deploying..'
 sh "mvn spring-boot:run"
 }
 post{
 always{
 echo 'Saving artifacts..'
 archiveArtifacts artifacts: 'target/*.jar', onlyIfSuccessful: true
 }
 }
 }
 }
}
