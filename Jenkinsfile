pipeline{
agent any
stages{
  stage(repository){
	step {
	    git('https://github.com/shailja123/springexample.git')
	  }
	}
   
   stage('Build') {
      step {
	     withMaven(maven: 'maven3.3.9'){
	            sh 'mvn clean install'
	                   }
            }
       }
   stage('Results') {
      junit '**/target/surefire-reports/TEST-*.xml'
      archive 'target/*.jar'
            }

  }
}
