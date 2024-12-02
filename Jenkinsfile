pipeline{
  agent any
//JAVA와 MAVEN Tool등록
  tools{
    jdk 'jdk17'
    maven 'M3'
  }
  //Docker Hub 접속
  enviroment{
    DOCKER_CREDENTIALS = credentials('dockerCredentials')
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
        sh 'mvn -Dmaven.test.failure.ignore=true clean package'
      }
    }
    stage('Docker Image'){
      steps{
        dir("${env.WORKSPACE}"){
          sh """
          docker build -t jsy964/spring-petclinic:$BUILD_NUMBER .
          docker tag jsy964/spring-petclinic:$BUILD_NUMBER jsy964/spring-petclinic:latest
          """
        }
      }
    }
    stage('Docker Image Push'){
      sh"""
      echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin
      docker push jsy964/spring-petclinic:latest
      """
    }
  }
}
