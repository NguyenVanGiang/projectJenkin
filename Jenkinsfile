 opipeline {
    agent any
    environment {
        BUILD_SCRIPTS_GIT="https://github.com/NguyenVanGiang/projectJenkin.git"
        BUILD_SCRIPTS='mypipeline'
        BUILD_HOME='/git'
      }
    stages {
        // stage('Stage 1') {
        //     steps {
        //         mvn clean
        //     }
        // }
        stage('Checkout: Code') {
              steps {
                sh "mkdir -p $WORKSPACE/repo;\
                    git clone $BUILD_SCRIPTS_GIT repo/$BUILD_SCRIPTS"
                sh "chmod -R +x $WORKSPACE/repo/$BUILD_SCRIPTS"
              }
        }
        stage('read') {
           steps {
               script {
                   def data = readFile(file: '/src/deploy.yml')
                   echo data
               }
           }
       }

      stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
     
    }
}
