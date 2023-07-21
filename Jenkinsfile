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
       
                 git "https://github.com/NguyenVanGiang/projectJenkin.git"
           }
       }
       
  }
  post {
    always {
       cleanWs()
    }
  }
}
