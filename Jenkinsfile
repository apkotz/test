pipeline {
      agent {
                label '172.31.3.162'
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
