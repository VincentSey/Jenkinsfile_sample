pipeline {
    agent any

    stages {
       stage('Stage1_22053098') {
           steps {
               echo "S1_22053098 : Environment Preparation Completed"
           } 
       }
        
       stage('Stage2_22053098') {
           steps {
                sh(script:"""
                    docker run -d -it -p 42000:8080 --name=S2_22053098_Server 22053098_webimage /bin/sh
                    docker rm -f S2_22053098_Server
                """)
                echo "S2_22053098 : Web Server Creation Completed"
           }
       }
       
      stage('Parallel'){
          parallel{
              stage('Stage3_22053098') {
                 steps {
                    echo "S3_22053098 : API Test Completed"
                 } 
              }   
              stage('Stage4_22053098') {
                 steps {
                    echo "S4_22053098 : FileTest Completed"
                 } 
              }  
          }
      }
 
