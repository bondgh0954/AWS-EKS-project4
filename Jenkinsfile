pipeline {
  angent any
  tools {
    maven "maven"
  }
  stages{
    stage("build jar"){
      steps{
        script{
          echo "building image artifact"
        }
      }
    }
    stage("deploying application"){
      environment {
        AWS_ACCESS_KEY = credentialsId("access-key")
        AWS_SECRET_KEY = credentialsId("secrete-key")
      }
      steps{
        script{
          echo "deploying application into kubernetes cluster"
          sh "kubectl create deployment nginx-depl --image=nginx"
        }
      }
    }
  }
}
 