pipeline {
     agent any
     stages {
         stage('Build') {
             steps {
                 sh 'echo "Hello World"'
                 sh '''
                     echo "Multiline shell steps works too"
                     ls -lah
                 '''
             }
         }      
         stage('Upload to AWS') {
              steps {
                  withAWS(region:'us-east-1',credentials:'user/jenkins123') 
         {
                  sh 'echo "Uploading content with AWS creds"'
                      s3Upload(file:'app.py', bucket:'jenkins0307')
                  
                  }
              }
         }
     }
}
