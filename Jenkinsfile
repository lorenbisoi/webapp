node{
   stage('SCM checkout'){
      git 'https://github.com/lorenbisoi/webapp'
   }
   stage('compile-package'){
      def mvnHome = tool name: 'maven 3.5.4', type: 'maven'
      sh"${mvnHome}/bin/mvn package"
      sh 'mvn package'
   }
   stage('deploy to tomcat'){
      sshagent(['Tomcat']) {
         sh sshpass -p "lorenbisoi" 'scp -o StrictHostKeyChecking=no target/*.war loren@172.17.0.2://usr/local/tomcat/webapps'
         
      }
   }
}
