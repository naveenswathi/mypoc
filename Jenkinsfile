node{
  stage('SCM checkout'){
     git 'https://github.com/naveenswathi/mypoc.git'
  }   
  stage('Compile-Package'){
     def mvnHome = tool name: 'MAVEN_HOME', type: 'maven'
     def mvnCMD = "${mvnHome}/bin/mvn"
     sh "${mvnCMD} clean package"
  }
  stage('test'){
     def mvnHome = tool name: 'MAVEN_HOME', type: 'maven'
     def mvnCMD = "${mvnHome}/bin/mvn"
     sh "${mvnCMD} test"
  }  
  stage('deploy war to tomcat'){
     sshagent(['deploy']) {
     sh 'scp -o StrictHostKeyChecking=no target/*.war ec2-user@172.31.7.233:/opt/apache-tomcat-8.5.50/webapps/'  
     }     
  }
}  
         
