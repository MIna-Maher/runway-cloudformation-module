//Defining global variable
def DEPLOY_ENVIRONMENT="dev"

pipeline {

       agent any
      
    //parameters {
      //    booleanParam(defaultValue:false, description:'Skip publishing - build only', name:'SKIP_PUBLISH')
          //string(name: 'RUN_AUTOMATION', defaultValue: 'dev', description:'Archive IPA file and run Automated tests')
          //choice(choices: ['dev', 'prod'], name: 'DEPLOY_ENVIRONMENT')
    stages {
        
        stage('Prepare') {
            when {branch 'master'}
            steps {
                    sh 'echo ######################Exporting  DEPLOY_ENVIRONMENT ######'
                    export DEPLOY_ENVIRONMENT=$DEPLOY_ENVIRONMENT
                    sh '''
                    printenv | grep -i DEPLOY_ENVIRONMENT
                    chmod +x runway
                   '''
                }
        }
        stage('deploy') {
            when {branch 'master'}
            steps {
                    sh 'echo #####################Deploying the app ######'
                    print(DEPLOY_ENVIRONMENT)
                    sh '''
                    ./runway plan --ci
                   '''
                }
        }
    }
}