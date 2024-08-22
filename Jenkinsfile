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
        AWS_ACCESS_KEY_ID = credentials('aws_access_key')
        AWS_SECRET_ACCESS_KEY = credentials('aws_secret_key')
      }
      steps{
        script{
          echo "deploying into EKS cluster"
          sh "kubectl create deployment nginx-deployment --image=nginx"

        }
      }
    }
  }
}
 