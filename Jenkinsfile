pipeline {
   agent any
   tools {
      jdk 'JAVA_HOME'
      maven 'MAVEN_HOME'
    }
    stages{
       stage('Build'){
          steps {
                sh 'mvn clean package'       
                sh "docker build -t webapp:${env.BUILD_ID} ."                
                sh 'docker login -u skumar2408 -p Password@123'                
                sh "docker tag webapp:${env.BUILD_ID} skumar24/webapp:${env.BUILD_ID}"                
                sh "docker push satyendrasingh/webapp:${env.BUILD_ID}"
          }
       }
    }
}
