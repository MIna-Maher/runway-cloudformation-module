pipeline {

    parameters {
        booleanParam(defaultValue:false, description:'Skip publishing - build only', name:'SKIP_PUBLISH')
        booleanParam(defaultValue:false, description:'Archive IPA file and run Automated tests', name:'RUN_AUTOMATION')
    }
    stages {
        stage('Prepare') {
            steps {
                    sh 'whoami'
                    }
                }
            }
}     