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


       stage(region:'us-east-1','Upload to AWS') {
       	 steps {
        	withAWS(credentials:'aws-static') {
            s3Upload(file:'index.html', bucket:'mys3static')
        	  }
              }	 
       	 }
    }
}
