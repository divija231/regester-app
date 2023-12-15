pipeline{
  agent any
  tools{
    jdk 'java17'
    maven 'Maven3'
  }
  stages{
    stage("Cleanup workspace"){
      steps{
        cleanWs()
        
      }
    }
    stage("checkout from scm"){
      steps{
        git branch: 'main', url: 'https://github.com/divija231/regester-app'
      }
    }
    stage("build application"){
      steps{
        sh 'mvn clean package'
      }
    }
    stage("testing aapplication"){
      steps{
        sh 'mvn test'
      }
    }
  }
  
}
