pipeline {
    agent none
    stages { 
        stage('Build') {
		     agent { label 'master' } 
            steps {
                sh ''' 
				         cd /home/ec2-user/simple-java-project
                         mvn clearn deploy	
				   '''						
            }
		 }
        stage('Test') {
		      agent { label 'slave1' }  
            steps {
                sh ' echo this is build ' 
            }
        }
        stage('Deploy') {
		      agent { label 'slave1' } 
            steps {
                sh 'echo STAGE 3: This is a Deploy stage'
            }
        }
    }
}

