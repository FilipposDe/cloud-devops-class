pipeline {
     agent any
     environment {
          registry = "philipposde/udacity2"
          dockerCredentials = 'docker_id'

	}
     stages {
	stage('Lint HTML') {
              steps {
                  sh 'tidy -q -e *.html'
              }
         }
         stage('Build container') {
             steps {
                  script {
                       dockerImage = docker.build registry
                  }
             }
         }

         stage('Push container') {
              steps { 
                   script {
                        docker.withRegistry('', dockerCredentials) {
                         dockerImage.push()

                        }
                   }
          //          withCredentials([usernamePassword( usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD' )]) {
          //        sh 'docker login -u $USERNAME -p $PASSWORD'
          //        }
          //        sh 'docker tag udacity2 $env.DOCKER_PATH'
          //        sh 'docker push $env.DOCKER_PATH'
          //     }
         }         
     //     stage('Deploy to cluster') {
     //          steps { 
                   
     //          }
     //     }         

     }
}}
