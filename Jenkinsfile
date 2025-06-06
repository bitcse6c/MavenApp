pipeline{
agent any
tools{
  maven 'Maven'
  jdk 'JDK'
}
stages{
   stage('Checkout'){
      steps{
         git branch:master,url:'https://github.com/bitcse6c/MavenApp.git'
      }
   }
   stage('Build'){
      steps{
        sh 'mvn clean package'
      }
   }      
    stage('Test'){
      steps{
        sh 'mvn test'
      }
   }   
    stage('Run Application'){
      steps{
        sh 'java -jar target/MavenApp-1.0-SNAPSHOT.jar'
      }
   }           
}
post{
  success{
     echo 'Build successful and deployed'
  }
  failure{
     echo 'Build failed'
  }
}
}           
