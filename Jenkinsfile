node{
   stage('SCM checkout'){
      git 'https://github.com/lorenbisoi/webapp'
   }
   stage('compile-package'){
      sh 'mvn package'
   }
}
