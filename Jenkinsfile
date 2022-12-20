pipeline {
   options {
    buildDiscarder(logRotator(numToKeepStr: '20'))
    disableConcurrentBuilds()
    timeout (time: 60, unit: 'MINUTES')
    timestamps()
  } 
    agent {
      label ("node1 || node2 ||  node3 || node4 ||  node5 ||  branch ||  main ||  jenkins-node || docker-agent ||  jenkins-docker2 ||  preproduction ||  production")
  }

    stages {
      stage('Setup parameters') {
            steps {
                script {
                    properties([
                        parameters([
                        
                        choice(
                            choices: ['Dev', 'Sanbox', 'Prod'], 
                            name: 'Environment'
                                 
                                ),


                          string(
                            defaultValue: 'flavila002',
                            name: 'User',
			                description: 'Required to enter your name',
                            trim: true
                            ),
                          string(
                            defaultValue: 'flavila002',
                            name: 'DB-Tag',
			                description: 'Required to enter the image tag',
                            trim: true
                            ),
                         string(
                            defaultValue: 'flavila002',
                            name: 'UI-Tag',
			                description: 'Required to enter the image tag',
                            trim: true
                            ),
                         string(
                            defaultValue: 'flavila002',
                            name: 'WEATHER-Tag',
			                description: 'Required to enter the image tag',
                            trim: true
                            ),
                         string(
                            defaultValue: 'flavila002',
                            name: 'AUTH-Tag',
			                description: 'Required to enter the image tag',
                            trim: true
                            ),   

                        ])
                    ])
                }
            }
        }
 
        stage('Hello') {
            steps {
                sh '''
                echo 'Hello World'
                ls
  
                '''
                
            }
        }
    }
	post {
    
    success {
      slackSend (channel: '#development-alerts', color: 'good', message: "Images  have been pushed to Nexus")
    }

    failure {
      slackSend (channel: '#development-alerts', color: '#FF0000', message: "FAILURE: Images  have NOT been pushed to Nexus")
    }
}
	
	
}
