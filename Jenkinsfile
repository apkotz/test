pipeline {
      agent {
	      label {
            label 'built-in'
           }
        }
      stages {
		 
	     stage ('Cloning all branch & copied to node-1 ') {
			
								steps {
									sh "git checkout qa"
									sh " scp -i "MyWS-1.pem" index.html ec2-user@172.31.4.198:/mnt"
									sh "sudo yum install httpd -y"
									sh "sudo service httpd start"
									sh "sudo cp /mnt/index.html /var/www/html/"
				                    
									  }
		}
				                stage ('copied to node-2'){
														
									steps {
									        sh "git checkout dev-1"
									        sh " scp -i "MyWS-1.pem" index.html ec2-user@172.31.40.40:/mnt"
										    sh "sudo yum install httpd -y"
										    sh "sudo service httpd start"
										    sh "sudo cp /mnt/index.html /var/www/html/"
										    sh "sudo chmod -R 777 /var/www/html/index.html"
									
									
									}
								
								
								
								
								}
			                }
		 
} 
	
