pipeline{
  agent any
//JAVA와 MAVEN Tool등록
  tools{
    jdk 'jdk17'
    maven 'M3'
  }
  stages{
    //GitHub에서 jenkins로 소스코드 복제
    stage('Git Clone'){
      steps{
        git url:'https://github.com/jsy111/spring-petclinic.git', branch:'main'
      }
    }
    stage('Maven Build'){
      steps{
        
      }
    }
    stage('Docker Image'){
      steps{
        
      }
    }
    stage('Docker Image Push'){
      steps{
        
      }
    }
    stage('SSH Publish'){
      
    }
  }
}
