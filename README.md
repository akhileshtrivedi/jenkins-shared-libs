## How to create Jenkins Shared Library

### This is the file structure of shared library

![Screenshot 2021-12-04 at 10 22 37 AM](https://user-images.githubusercontent.com/17960408/144698044-b6ff8ef8-86f1-4151-8c48-64f5c923e18f.png)


### There are 3 steps to configure Jenkins Shared LIbarary
 
 
## Step-1: Create repository for  Shared LIbarary like (https://github.com/akhileshtrivedi/jenkins-shared-libs)
 
## Step-2: Go to Jenkins, then go to Manage Jenkins --> Configure System --> Global Pipeline Libraries
 
## Now you can add a library with the following settings:

Name: first-shared-libs

Default version:  e.g. master or main

Retrieval method: Modern SCM

Select the Git type

Project repository: https://github.com/akhileshtrivedi/jenkins-shared-libs.git


## Step-3:  Create pipeline script 
  
  
  @Library('first-shared-libs') _

pipeline{

    agent any
    
    stages{
    
        stage('Demo'){
        
            steps{
            
              welcome("Akhilesh")
              
              script{
              
                  calculator.add(8,2)
                  
                  calculator.sub(8,2)
                  
                  calculator.mul(8,2)
                  
                  calculator.div(8,2)
                  
              }
              
            }
            
        }
        
    }
  
  
 ## Thanks!
