pipeline{
agent any
stages{
  stage(repository){
	  steps	{
		step {
	    		git('https://github.com/shailja123/springexample.git')
	  		}
		}
  	}
   
   stage('Build') {
	   steps {
      		step {
	     		withMaven(maven: 'maven3.3.9'){
	            					sh 'mvn clean install'
	                   			}
            		}
  		   }
   	}
   
    stage('Results') {
	    steps{
		    step{
			    junit '**/target/surefire-reports/TEST-*.xml'
      			    archive 'target/*.jar'
		    }
	        }
            }
  }

}
