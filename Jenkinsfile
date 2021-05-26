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
      
pipeline {
    agent any //{ label propertyInfo.build_agent_label}
    //environment {
    //    propertyInfo = load 'build_options'
    //}
    stages {
        stage('testing build file') {
            steps {
                sh '''
                 echo $propertyInfo.build_agent_label 
                 '''               
            }
        }
    }
}
//def buildOptions = 'build_options'
def buildOptions = 'build_options.yaml'
def propertyInfo = readYaml file: 'build_options.yaml'