node{
  stage('SCM checkout'){
     git 'https://github.com/naveenswathi/mypoc.git'
  }   
  stage('Compile-Package'){
     def mvnHome = tool name: 'MAVEN_HOME', type: 'maven'
     def mvnCMD = "${mvnHome}/bin/mvn"
     sh "${mvnCMD} clean package"
  }   
         
