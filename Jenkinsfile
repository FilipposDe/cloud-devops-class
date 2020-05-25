pipeline {
     agent any
     environment {

         DOCKER_PATH = credentials('philipposde/udacity2')

	}
     stages {
	stage('Lint HTML') {
              steps {
                  sh 'tidy -q -e *.html'
              }
         }
         stage('Build container') {
             steps {
                 sh 'docker build -t myapp .'
                sh 'docker run -d -p 8080:80 myapp'
             }
         }
	 stage('Test container'){
		sh 'curl -$(docker-machine ip default):80'
	 }
         
         stage('Push container') {
              steps { 
                   withCredentials([usernamePassword( usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD' )]) {
                 sh 'docker login -u $USERNAME -p $PASSWORD'
                 }
                 sh 'docker tag udacity2 $env.DOCKER_PATH'
                 sh 'docker push $env.DOCKER_PATH'
              }
         }         
     //     stage('Deploy to cluster') {
     //          steps { 
                   
     //          }
     //     }         

     }
}
