pipeline {
    agent any

    //environment {
        // Variables de entorno globales
        // NODE_VERSION = '18'
    //}

    tools { nodejs "nodejs" }

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: 'main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/LuisLiraC/react-demo-project.git']]])
            }
        }

        stage('Install Dependencies') {
            //environment {
                // Variables de entorno específicas de esta etapa
                // NPM_REGISTRY = 'https://registry.npmjs.org/'
            //}
            steps {
                sh "npm install"
            }
        }

        stage('Run Tests') {
            steps {
                sh "npm test"
            }
        }
    }
}
