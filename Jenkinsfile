/*
def call ( Map propertyInfo ) {
    def buildOptions = 'build_options'
    
    node('master') {
        stage('get info') {
            checkout scm

            def tmpInfo = readProperties file: "${buildOptions}"
            propertyInfo << tmpInfo
        }
    }
*/
def buildOptions = 'build_options'
def propertyInfo = readFile ('buildOptions')    
 pipeline {
    agent any //{ label propertyInfo.build_agent_label}
    stages {
        stage('testing build file') {
            steps {
                sh ''' 
                echo $(propertyInfo.build_agent_label)
                '''
            }
        }
    }
}
}