pipeline {
      agent {
	      label {
                      label 'Node-2'
                    }
            }
         stages {
		 
	 stage ('install apache') {
			
					      
								steps { sh "sudo yum install git -y"
										sh "git clone --single-branch --branch qa https://github.com/apkotz/test.git"
										sh "sudo yum install httpd -y"
										sh "sudo service httpd start"
										sh "sudo cp index.html /var/www/html/"
										sh "sudo chmod -R 777 /var/www/html/index.html"
				
				
									  }
							}
									  
				                stage {
								
									agent {
											label {
													label 'Node-1'
									        }
            
									}
									steps {
									    sh "sudo yum install git -y"
										sh "git clone --single-branch --branch dev-1 https://github.com/apkotz/test.git"
										sh "sudo yum install httpd -y"
										sh "sudo service httpd start"
										sh "sudo cp index.html /var/www/html/"
										sh "sudo chmod -R 777 /var/www/html/index.html"
																			
									}
								
								}
			                }
		} 
	
