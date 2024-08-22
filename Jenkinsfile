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
      environment {
        AWS_ACCESS_KEY = credentialsId("acess-key")
        AWS_SECRET_KEY = credentialsId("secret-key")
      }
      steps{
        script{
          echo "deploying into EKS cluster"
          sh "kubectl create deployment ngin-deployment --image=nginx"

        }
      }
    }
  }
}
 