<h1>Deploy from Jenkins to EKS cluster</h1>
<h2>Technologies used</h2>

- <b>Kubernetes</b> 
- <b>AWS EKS</b>
- <b>Jenkins</b>
- <b>Docker<b/>
- <b>Linux<b/>




<h2>Detailed Description of Project </h2>
1. Install kubectl and aws-am-authenticator on a Jenkins server<br/>
2. Create kubeconfig file to connect to EKS cluster and add it on Jenkins server<br/>
3. Add AWS credentials on Jenkins for AWS account authentication<br/>
4. Extend and adjust Jenkinsfile of the previous CI/CD pipeline to configure connection to EKS cluster<br/>






   <p align="">
   <h2>step 1    Install kubectl and aws-iam-authenticator on a jenkins server</h2>
   ssh into jenkins container as root user ( docker exec -u 0 -it containerNo bash)
   install kubectl 
   check documentation for installation
   curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/          linux/amd64/kubectl

   add execution permission to ./kubectl
   chmod +x ./kubectl

   move ./kubectl to local folder
   mv ./kubectl /usr/local/bin
  
   <img src='./img/w2.png' height="80%" width="80%" alt="Disk Sanitization Steps">

   install aws-iam-authenticator in jenkins container
   check documentation for installation guide

   1. download using curl command

   curl -o aws-iam-authenticator https://amazon-eks.s3.us-west-2.amazonaws.com/1.15.10/2020-02-22/bin/linux/amd64/aws-iam-authenticator

   2. add executable permission to aws-iam-authenticator
      chmod +x ./aws-iam-authenticator

   3. move the file to usr/local/bin folder
      mv ./aws-iam-authenticator /usr/local/bin
   <img src='./img/w3.png' height="80%" width="80%" alt="Disk Sanitization Step">


 


   <h2>step 2  Create kubeconfig file to connect to EKS cluster and add it on Jenkins server</h2>
    
  
  <img src='./img/w3.png' height="80%" width="80%" alt="Disk Sanitization Step"> 

  

   <h2>step 3 Add AWS credentials on Jenkins for AWS account authentication</h2>
   

   <img src='./img/w4.png' height="80%" width="80%" alt="Disk Sanitization Step"> 
   

 
   
   

   <h2>step 4  Extend and adjust Jenkinsfile of the previous CI/CD pipeline to configure connection to EKS cluster</h2>
  
   

   


   <img src='./img/w11.png' height="80%" width="80%" alt="Disk Sanitization Step"> 


   

 
     

</p>
