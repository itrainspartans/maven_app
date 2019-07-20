node {
   stage('Code checkout') { // for display purposes
      // Get some code from a GitHub repository
      git credentialsId: 'githubID', url: 'https://github.com/itrainspartans/maven_app.git'
   }
   stage('Build') {
     withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
      sh 'mvn clean compile'
     } 
   }
   stage('Test') {
    withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
      sh 'mvn test'
     }  
   }
   stage('Sonar CodeAnalysis') {
      withSonarQubeEnv('itrainspartans') {
                sh 'mvn clean verify sonar:sonar'
              }
    }
   stage('Package') {
    withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
      sh 'mvn package'
     }  
   }
   
   
   stage('Artifactory') {
     
   }
   
   stage('Docker Build') {
     
   }
   
   stage('Deploy to Dev') {
     
   }
   stage('Deploy to Stage') {
     
   }
   stage('Deploy to Prod') {
     
   }
}
