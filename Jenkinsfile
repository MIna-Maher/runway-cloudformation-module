//Defining global variable
def DEPLOY_ENVIRONMENT="dev"

pipeline {

       agent any
      
    parameters {
          booleanParam(defaultValue:false, description:'Skip publishing - build only', name:'SKIP_PUBLISH')
        //booleanParam(defaultValue:false, description:'Archive IPA file and run Automated tests', name:'RUN_AUTOMATION')
        //choice(choices: ['dev', 'prod'],defaultValue: 'dev' , name: 'DEPLOY_ENVIRONMENT')
    }
    stages {
        
        stage('Prepare') {
            when {branch 'main'}
            steps {
                    sh '''
                    whoami
                    pwd
                    echo "######################Exporting  DEPLOY_ENVIRONMENT ###### as ${DEPLOY_ENVIRONMENT}"
                    export DEPLOY_ENVIRONMENT=env.DEPLOY_ENVIRONMENT
                    echo $DEPLOY_ENVIRONMENT
                   '''
                }
        }
    }    
} 