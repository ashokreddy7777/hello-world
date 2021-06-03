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
     //environment {
    //    
    //{ label propertyInfo.build_agent_label}
    propertyInfo = load 'build_options'
    //
    //def buildOptions = 'build_options'

//def propertyInfo = readYaml file: 'build_options.yaml'

      
pipeline {
    agent any 
    stages {
        stage('get info') {
            steps {
                script {
                    checkout scm
                    //def buildOptions = 'build_options.yaml'
                    def propertyInfo = readYaml file: build_options.yaml
                    //propertyInfo << tmpInfo
                }
            }
        }
        stage('testing build file') {
            steps {
                sh '''
                 echo "$(propertyInfo.build_agent_label)" 
                 '''               
            }
        }
    }
}*/
properties = null

def loadProperties() {
    node {
        checkout scm
        properties = readProperties file: "${fileName}"
        echo "Immediate one ${properties.repo}"
    }
}

pipeline {
    agent none

    stages {           
        stage ('prepare') {
            agent any

            steps {
                script {
                    loadProperties()
                    echo "Later one ${properties.ansible}"
                }
            }
        }
        stage('Build') {

            agent any

            steps {
                cat secret.yaml
            }

        }
    }
}