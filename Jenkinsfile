pipeline {
      agent {
	      label {
                      label 'Node-1'
                    }
            }
         stages {
			
	 stage ('on node-1') {
			
					      
								steps { 
										sh "git checkout qa"
										sh "sudo yum install httpd -y"
										sh "sudo service httpd start"
										sh "sudo cp index.html /var/www/html/"
										sh "sudo chmod -R 777 /var/www/html/index.html"
				
				
									  }
							}
									  
				                stage ( 'on node-2'){
								
									agent {
											label {
													label 'Node-2'
									        }
            
									}
									steps {
									    
										sh "git checkout dev-1"
										sh "sudo yum install httpd -y"
										sh "sudo service httpd start"
										sh "sudo cp index.html /var/www/html/"
										sh "sudo chmod -R 777 /var/www/html/index.html"
																			
									}
								
								}
			            }
				
		} 
	
