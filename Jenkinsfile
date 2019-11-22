pipeline {
		agent any
		tools {
		 jdk 'localJDK'
		 maven 'MAVEN_HOME'
    }
	
	stages{
       stage('Build'){
          steps {
		  sh 'mvn clean package'
         
sh "docker build -t webapp:${env.BUILD_ID} ."
                
sh 'docker login -u 96637 -p password@123'
                
sh "docker tag webapp:${env.BUILD_ID} 96637/webapp:${env.BUILD_ID}"
                
sh "docker push 96637/webapp:${env.BUILD_ID}"
          }
      }
   }
}
