#!/user/bin/env groovy


pipeline{
  agent any
  tools{
    maven 'maven'
  }

  stages {
    stage('build jar'){
      steps{
        script{
          echo "building jar file"

        }
      }
      
    }
    stage("deploy"){
    
      steps{
        script{
          echo "deploying into EKS cluster"
          withKubeConfig([credentialsId:"linode-kube", serverUrl: "https://0538af3c-30f6-42f3-a88d-627a5182b1ef.eu-central-2.linodelke.net"]){
            sh "kubectl create deployment ngin-deployment --image=nginx"

          }
          
         

        }
      }
    }
  }
}
 