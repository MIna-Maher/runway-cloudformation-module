//Defining global variable
def DEPLOY_ENVIRONMENT="dev"

pipeline {

       agent any
      
    //parameters {
      //    booleanParam(defaultValue:false, description:'Skip publishing - build only', name:'SKIP_PUBLISH')
          //string(name: 'RUN_AUTOMATION', defaultValue: 'dev', description:'Archive IPA file and run Automated tests')
          //choice(choices: ['dev', 'prod'], name: 'DEPLOY_ENVIRONMENT')
    stages {
        
        stage('Prepare-and-deploy') {
            when {branch 'master'}
            steps {
                    sh 'echo ######################Exporting  DEPLOY_ENVIRONMENT ######'
                    echo DEPLOY_ENVIRONMENT
                    sh """
                    export DEPLOY_ENVIRONMENT=${DEPLOY_ENVIRONMENT}
                    printenv | grep -i DEPLOY_ENVIRONMENT
                    chmod +x runway
                    ./runway destroy --ci
                   """
                }
        }
    }
}
