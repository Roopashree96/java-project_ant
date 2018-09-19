pipeline {
    agent any
      stages {
         stage('unit Test') {
        steps {
          sh 'ant -f test.xml -v '
         
          }
        }
      
         stage('build') {
	 steps {
		sh 'ant -f build.xml -v'
               }
           }
    
          }
      
  
   
  post {
       always {
        archiveArtifacts artifacts: 'dist/*.jar',fingerprint: true
        }
    }
}
