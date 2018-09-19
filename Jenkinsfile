pipeline {
    agent any
      stages {
         stage('unit Test') {
        steps {
          sh 'ant -f test.xml  '
         
          }
        }
      
         stage('build') {
	 steps {
		sh 'ant -f build.xml '
               }
           }
    
          
   stage('deploy') {

      steps {

      sh "cp dist/rectangle_${env.BUILD_NUMBER}.jar /var/www/html/rectangles/all/"

     }

   }     
 } 
   
  post {
       always {
        archiveArtifacts artifacts: 'dist/*.jar',fingerprint: true
        }
    }
}
