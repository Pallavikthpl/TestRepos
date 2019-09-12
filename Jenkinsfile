pipeline {
    agent any
    stages {
        stage('Build') { 
            
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/Pallavikthpl/TestRepos.git']]])
            }
        }
        stage('Test') { 
               
            steps {
                bat "echo Test"
            }
        }
        stage('Sonarqube') {
		environment {
        scannerHome = tool 'LocalSonarQubeScanner'
		}
		steps {
        withSonarQubeEnv('sonar_server') {
            bat "${scannerHome}/bin/sonar-scanner"
        }
		}
		}
        stage('Deploy') {
                
            steps {
                bat "echo Deploy"
            }
        }
    }
}
