pipeline {
  agent any
    stages {
       stage('build'){
       steps {
                sh 'echo "Hello World"'  
                sh '''
                    echo "Multi line work too"
                    ls -alh   
                   '''
                 }
             }
    	
       stage('Upload to AWS') {
              steps {
                  withAWS(region:'US West (Oregon) us-west-2',credentials:'aws-static') {
                  sh 'echo "Uploading content with AWS creds"'
                      s3Upload(file:'index.html', bucket:'mys3static')
                  }
              }
         
        }
    }
