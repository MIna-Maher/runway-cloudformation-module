//Defining global variable
def DEPLOY_ENVIRONMENT="dev"

pipeline {

       agent any
      
    parameters {
        //booleanParam(defaultValue:false, description:'Skip publishing - build only', name:'SKIP_PUBLISH')
        //booleanParam(defaultValue:false, description:'Archive IPA file and run Automated tests', name:'RUN_AUTOMATION')
        //choice(choices: ['dev', 'prod'],defaultValue: 'dev' , name: 'DEPLOY_ENVIRONMENT')
    }
    stages {
        
        stage('Prepare') {
            when {branch 'main'}
            steps {
                    sh 'whoami'
                    sh 'pwd'
                    echo "######################Exporting  DEPLOY_ENVIRONMENT ###### as ${DEPLOY_ENVIRONMENT}"
                    sh `export DEPLOY_ENVIRONMENT=${DEPLOY_ENVIRONMENT}`
                    sh 'echo $DEPLOY_ENVIRONMENT'

                }
        }
    }    
} 