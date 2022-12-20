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
  
          - permission   ### checking the employee belong to s4 session
  - cleaning        ### clean the environment
  - sonarqube   ### test the code using sonarqu
  - build-dev    ### build image for dev environment only 
  - build-sanbox ### build image for sanbox environment only 
  - build-prod  ### build image for prod environment only 
  - login       ### login to company dockerhub account
  - push-to-dockerhub-dev   ### push image for dev environment only 
  - push-to-dockerhub-sanbox   ### push image sandbox  dev environment only 
  - push-to-dockerhub-prod       ### push image for prod  environment only 
  - update helm charts-sanbox   ### update values file  for prod  environment only 
  - update helm charts-dev        ### update values file  for dev  environment only 
  - update helm charts-prod    ### update values file  for test  environment only 
  - wait for argocd      ### waiting for argocd to detect the change 
  - post build report (success, unstable, failure) on slack  development-alerts channel  and clean directory    ### 
 
        stage('permission') {
            steps {
                sh '''
                ls 
                pwd
                '''
            }
        }

        stage('cleaning') {
            steps {
                sh '''
                ls 
                pwd
                '''
            }
        }

        stage('sonarqube') {
            steps {
                sh '''
                ls 
                pwd
                '''
            }
        }

        stage('build-dev') {
            steps {
                sh '''
                ls 
                pwd
                '''
            }
        } 

        stage('build-sanbox') {
            steps {
                sh '''
                ls 
                pwd
                '''
            }
        }

        stage('build-prod') {
            steps {
                sh '''
                ls 
                pwd
                '''
            }
        }

        stage('login') {
            steps {
                sh '''
                ls 
                pwd
                '''
            }
        }

        stage('push-to-dockerhub-dev') {
            steps {
                sh '''
                ls 
                pwd
                '''
            }
        }  

        stage('push-to-dockerhub-sanbox') {
            steps {
                sh '''
                ls 
                pwd
                '''
            }
        }

        stage('push-to-dockerhub-prod') {
            steps {
                sh '''
                ls 
                pwd
                '''
            }
        }

        stage('update helm charts-sanbox') {
            steps {
                sh '''
                ls 
                pwd
                '''
            }
        } 

        stage('update helm charts-dev') {
            steps {
                sh '''
                ls 
                pwd
                '''
            }
        }

        stage('update helm charts-prod') {
            steps {
                sh '''
                ls 
                pwd
                '''
            }
        }

        stage('wait for argocd') {
            steps {
                sh '''
                ls 
                pwd
                '''
            }
        }

        stage('post build report') {
            steps {
                sh '''
                ls 
                pwd
                '''
            }
        }                            '''
                
            }
        }
    }
	post {
    
    success {
      slackSend (channel: '#development-alerts', color: 'good', message: "Images  have been pushed to dockerhub")
    }

    failure {
      slackSend (channel: '#development-alerts', color: '#FF0000', message: "FAILURE: Images  have NOT been pushed to dockerhub")
    }
}
	
	
}

