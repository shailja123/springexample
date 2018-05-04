env.mvnHome = '/home/ubuntu/maven'
node() {
  stage(repository){
	steps{
	    git('https://github.com/shailja123/springexample.git')
	  }
	}
   
   stage('Build') {
      
      if (isUnix()) {
         sh "'${mvnHome}/bin/mvn' clean install"
      } else {
         bat(/"${mvnHome}\bin\mvn" -Dmaven.test.failure.ignore clean package/)
      }
   }
   stage('Results') {
      junit '**/target/surefire-reports/TEST-*.xml'
      archive 'target/*.jar'
   }
}
