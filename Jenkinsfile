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
   stage('deploy') {

      steps {

      sh "cp dist/rectangles_${env.BUILD_NUMBER}.jar /var/www/html/rectangles/all/"

     }

   }     
 } 
   
  post {
       always {
        archiveArtifacts artifacts: 'dist/*.jar',fingerprint: true
        }
    }
}
