pipeline {
    agent any
 stages {
  stage('Docker Build and Tag') {
           steps {
              
                sh 'docker build -t my-node-img:latest .' 
                sh 'docker tag my-node-img ijisha27/jenkins-pipeline-repo:latest'
                sh 'docker tag my-node-img lijisha27/jenkins-pipeline-repo:$BUILD_NUMBER'
               
          }
        }
     
  stage('Publish image to Docker Hub') {
          
            steps {
        withDockerRegistry([ credentialsId: "Mydockerhub-credential", url: 
"" ]) {
          sh  'docker push lijisha27/jenkins-pipeline-repo:latest'
          sh  'docker push lijisha27/jenkins-pipeline-repo:$BUILD_NUMBER' 
        }
                  
          }
        }
    }
}
