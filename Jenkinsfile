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
        	withAWS(region:'US East (N. Virginia) us-east-1', credentials:'aws-static') {
            s3Upload(file:'index.html', bucket:'mys3static')
        	  }
              }	 
       	 }
    }
}
