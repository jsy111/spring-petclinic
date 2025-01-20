pipeline{
  agent any
  //JAVA와 MAVEN Tool등록
  tools{
    jdk 'JDK17'
    maven 'M3'
  }
  //Docker Hub 접속
  environment{
    DOCKERHUB_CREDENTIALS = credentials('dockerCredentials')
    AWS_CREDENTIALS = credentials('AWSCredentials')
    GIT_CREDENTIALS = credentials('gitCredentials')
    REGION = 'ap-northeast-2'
  }

  stages{
    //GitHub에 가서 소스코드 가져오기
    stage('Git Clone'){
      steps{
        echo 'Git Clone'
        git url: 'https://github.com/jsy111/spring-petclinic.git'
          branch: 'main', credentialIdL: 'GIT_CREDENTIALS'
      }
    }
  }
}
