//Defining global variable
def DEPLOY_ENVIRONMENT="dev"

pipeline {

       agent any
      
    parameters {
          booleanParam(defaultValue:false, description:'Skip publishing - build only', name:'SKIP_PUBLISH')
          string(name: 'RUN_AUTOMATION', defaultValue: 'dev', description:'Archive IPA file and run Automated tests')
          //choice(choices: ['dev', 'prod'], defaultValue: 'dev' , name: 'DEPLOY_ENVIRONMENT')
    }
    stages {
        
        stage('Prepare') {
            when {branch 'main'}
            steps {
                    echo params.RUN_AUTOMATION
                    print(params.RUN_AUTOMATION)
                    sh 'echo ######################Exporting  DEPLOY_ENVIRONMENT ###### as ${DEPLOY_ENVIRONMENT}'
                    sh '''
                    whoami
                    pwd
                    export DEPLOY_ENVIRONMENT=dev
                    echo $DEPLOY_ENVIRONMENT
                    chmod +x runway
                    ./runway plan --ci
                   '''
                }
        }
    }    
} 