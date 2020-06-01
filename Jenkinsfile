pipeline {
     agent any
     environment {
          registry = "philipposde/udacity2"
          dockerCredentials = 'docker_id'

	}
     stages {
	//      stage('Lint HTML') {
     //          steps {
     //              sh 'tidy -q -e *.html'
     //          }
     //      }
     //      stage('Build container') {
     //           steps {
     //              script {
     //                   dockerImage = docker.build registry
     //              }
     //           }
     //      }

     //     stage('Push container') {
     //          steps { 
     //               script {
     //                    docker.withRegistry('', dockerCredentials) {
     //                     dockerImage.push()

     //                    }
     //               }
     //          }
     //     }         
         stage('Deploy to cluster') {
              steps { 
                   sh 'ansible-playbook playbook.yml -vvv --become-user=ubuntu'      
              }
         }         

     }
}
 