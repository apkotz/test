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
	 }
	
}
