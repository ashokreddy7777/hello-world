def call ( Map propertyInfo ) {
    def buildOptions = 'build_options'
    def tmpInfo = readProperties file: "${buildOptions}"
    propertyInfo << tmpInfo
}

pipeline {
    agent any //{ label propertyInfo.build_agent_label}
    stages {
        stage ('testing build file') {
            steps {
                sh ''' 
                echo "${propertyInfo.build_agent_label}"
                echo "${propertyInfo.build_technology}"
                echo "${propertyInfo.release_branch}"
                '''
            }
        }
    }
}