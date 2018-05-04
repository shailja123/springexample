env.mvnHome = '/home/ubuntu/maven'
node() {
  stage(repository){
	steps{
	    git('https://github.com/shailja123/springexample.git')
	  }
	}
   
   stage('Build') {
      
          sh "'${mvnHome}/bin/mvn' clean install"
      }
   stage('Results') {
      junit '**/target/surefire-reports/TEST-*.xml'
      archive 'target/*.jar'
   }
}
