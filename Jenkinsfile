pipeline {
      agent {
	      label {
            label 'built-in'
           }
        }
      stages {
		 
	     stage ('Cloning all branch & copied to node-2 ') {
			
								steps {
									
									sh "git checkout dev-1"
									sh "cd"
									sh "sudo scp -i /root/MyWs-1.pem /root/.jenkins/workspace/multi-branch-deploy/index.html ec2-user@172.31.43.114:/mnt"
									sh "git checkout qa"
									sh "cd"
									sh "sudo scp -i /root/MyWs-1.pem /root/.jenkins/workspace/multi-branch-deploy/index.html ec2-user@172.31.34.207:/mnt"
								}
			}
		stage ('install httpd on Node-2') {
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
		
	    stage ('install httpd on Node-1'){			
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
			                }
		 
} 
	
