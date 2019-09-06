pipeline {
    agent none
    stages {
        stage('Build') { 
            agent {label 'slave'}
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/Pallavikthpl/TestRepos.git']]])
            }
        }
        stage('Test') { 
                agent {label 'slave'}
            steps {
                sh "echo Test"
            }
        }
        stage('Deploy') {
                agent {label 'slave'}
            steps {
                sh "echo Deploy"
            }
        }
    }
}
