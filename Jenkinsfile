properties = null

def loadProperties() {
    node {
        cleanWs()
        checkout scm
        properties = readJSON file: "${productPropertiesFile}"
        echo "Product Properties File: ${productPropertiesFile}"
    }
}

pipeline {
    agent any

    stages {
        stage('prep') {
            steps {
                script {
                    loadProperties()
                    echo "${properties.pollTime}"
                }
            }
        }
        stage('cleanup') {
            steps {
                cleanWs()
            }
        }
    }
}