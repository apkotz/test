pipeline {
      agent {
	      label {
                      label 'built-in'
                    }
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
		 stage ('index file copy to node dir') {
												steps {
													        	
													        sh "chmod -R 400 /root/MyWS-1"
														sh "scp -i /MyWS-1 /root/.jenkins/workspace/multi-node_master/index.html ec2-user@172.31.3.162:/mnt/jenkins-slave/workspace/"
                        		      		     }
	                                        }
		 stage ('node') {
			 agent {
				 label {
					 label "172.31.3.162"
				       }
			      }
			 steps {
				 sh "yum install httpd -y"
				 sh "service httpd start"
				 sh "cp /mnt/jenkins-slave/workspace/index.html /var/www/html/"
				  sh "chmod -R 777 /var/www/html/index.html"
			       }
		 }
	 }
	
}
