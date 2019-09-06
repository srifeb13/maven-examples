node {
   
   stage('Code Checkout') { // for display purposes
    git credentialsId: 'githubID', url: 'https://github.com/itrainpadman/maven-examples.git'  
   }
   stage('Code Build') {
    withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
     sh 'mvn clean compile'
    }  
   }
   stage('Test Run') {
       withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
        sh 'mvn test'
     }  
   }
   stage('Code Quality') {
      sh 'mvn sonar:sonar \
         -Dsonar.projectKey=mavenexap \
         -Dsonar.organization=itrainorg \
         -Dsonar.host.url=https://sonarcloud.io \
         -Dsonar.login=34f6c51fcf349c4426c1169a36943d4830b72a3b'
   } 
   stage('Archive to Jfrog') {
   } 
   stage('Docker Image') {
   } 
   stage('Deploy to Dev') {
   } 
   stage('Deploy to Test') {
   } 
   stage('Deploy to Prod') {
   } 
}
