pipeline {
    agent any
    environment {
        BUILD_SCRIPTS_GIT="https://github.com/NguyenVanGiang/projectJenkin.git"
        BUILD_SCRIPTS='mypipeline'
        BUILD_HOME='/git'
      }
   stages {
       stage ('hello'){
           steps{
       
                   echo ${BUILD_SCRIPTS_GIT}
           }
       }
       
  }
  post {
    always {
       cleanWs()
    }
  }
}
