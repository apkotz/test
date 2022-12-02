pipeline {
      agent {
	      label {
            label 'built-in'
           }
        }
      stages {
		 
	     stage ('Cloning all branch & copied to node-1 ') {
			
								steps {
									sh "sudo chmod 700 /mnt/MyWS-1.pem"
									sh "git checkout qa"
									sh " cp /mnt/MyWS-1.pem /root/.jenkins/workspace/new/"
									sh " cd /root/.jenkins/workspace/new/"
									sh "scp -i MyWS-1.pem index.html ec2-user@172.31.4.198:/mnt"
									sh "git checkout dev-1"
									sh "chmod 400 /mnt/MyWS-1.pem"
									sh " cp /mnt/MyWS-1.pem /root/.jenkins/workspace/new/"
									sh "scp -i /root/.jenkins/workspace/new/MyWS-1.pem index.html ec2-user@172.31.40.40:/mnt"
								}
			}
		stage ('install httpd on Node-1') {
								agent {
									label {
										label 'Node-1'
									}
								}	
								steps {
										sh "sudo yum install httpd -y"
									    sh "sudo service httpd start"
										sh "sudo cp /mnt/index.html /var/www/html/"
										sh "sudo chmod -R 777 /var/www/html/index.html"
				                 }
			}
		
	    stage ('install httpd on node-2'){			
								agent {
									label {
										label 'Node-2'
									}
								
								}
									steps {
									        
										    sh "sudo yum install httpd -y"
										    sh "sudo service httpd start"
										    sh "sudo cp /mnt/index.html /var/www/html/"
										    sh "sudo chmod -R 777 /var/www/html/index.html"
									
									
									}

								}
			                }
		 
} 
	
