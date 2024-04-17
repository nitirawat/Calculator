pipeline {
  agent any
  stages {

    stage('Compile') {
      steps{
        sh 'mvn clean compile'
      }
    }

    stage('Test') {
      steps{
        sh 'mvn clean test'
      }
    }
    
    stage('Package') {
      steps{
        sh 'mvn clean package'
      
    stage('Deliver') {
      steps{
        deploy adapters: [tomcat9(credentialsId: 'Tomcat_user', path: '', url: 'http://54.243.11.143:9090/')], contextPath: null, war: 'target/calculator.war' 	 
      }
    }
  }
}
