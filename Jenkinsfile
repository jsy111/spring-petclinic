pipeline{
  agent any
  //JAVA와 MAVEN Tool등록
  tools{
    jdk 'JDK17'
    maven 'M3'
  }
  //Docker Hub 접속
  environment{
    DOCKERHUB_CREDENTIALS = credentials('dockerCredential')
    AWS_CREDENTIALS = credentials('AWSCredential')
    //GIT_CREDENTIALS = credentials('gitCredential')
    REGION = 'ap-northeast-2'
  }

  stages{
    //GitHub에 가서 소스코드 가져오기
    stage('Git Clone'){
      steps{
        echo 'Git Clone'
        git url: 'https://github.com/jsy111/spring-petclinic.git',
          branch: 'main'
      }
    }
  }
}
