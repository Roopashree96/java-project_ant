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
    stage("Running on Centos") {
       steps {
        
              sh "wget http://roopa/rectangles/all/rectangle_${env.BUILD_NUMBER}.jar" 
              sh "java -jar rectangle_${env.BUILD_NUMBER}.jar 3 4"
             }
         }
     }
               
   
  post {
       always {
        archiveArtifacts artifacts: 'dist/*.jar',fingerprint: true
        }
    }
}
