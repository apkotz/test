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
			stage ('node-1' {
				agent {
						label {
							label "Node-1"
						}
				
				}
				steps {
				git clone --single-branch --branch qa https://github.com/apkotz/test.git
				sh "sudo yum install httpd -y"
				sh "sudo service httpd start"
				sh "sudo cp index.html /var/www/html/"
				sh "sudo chmod -R 777 /var/www/html/index.html"
				
				
				}
			}
		 
		 }
	}
	
