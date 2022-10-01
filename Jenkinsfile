pipeline {
    agent {
                label 'built-in'
            }
         stages {
		stage ('install apache') {
			steps {
				sh "yum install httpd -y"
			}
		}	
		stage ('start apache') {
			steps {
				sh "service httpd start"
			}
		}
		stage ('index file deployment') {
                        steps {
                                sh "cp index.html /var/www/html/"
				sh "chmod -R 777 /var/www/html/index.html"
                        }
	       }
		 stage ('node-1') {
			 agent {
				 label {
					 label "172.31.38.56"
				 }
			 }	 
		stage ('install apache') {
			steps {
				sh "yum install httpd -y"
			}
		}	
		stage ('start apache') {
			steps {
				sh "service httpd start"
			}
		}
		stage ('index file deployment') {
                        steps {
                                sh "cp index.html /var/www/html/"
				sh "chmod -R 777 /var/www/html/index.html"
                        }
	       } 
		 }
	 }
	
}
