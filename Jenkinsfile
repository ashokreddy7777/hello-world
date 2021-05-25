def call ( Map propertyInfo ) {
    def buildOptions = 'build_options'
    
   // node('master') {
   //     stage()
    //}
    def tmpInfo = readProperties file: "${buildOptions}"
    propertyInfo << tmpInfo
}

pipeline {
    agent any //{ label propertyInfo.build_agent_label}
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