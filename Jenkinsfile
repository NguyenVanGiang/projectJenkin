pipeline {
    agent any 
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
    }
}
