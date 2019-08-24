
node {
   def mvn = tool (name: 'maven3', type: 'maven') + '/bin/mvn'
   stage('SCM Checkout'){
    // Clone repo
	git branch: 'master', 
	credentialsId: 'github', 
	url: 'https://github.com/ranjanajindal/shopizer.git'
   
   }
   
  
      
   }
   
	
   stage('Mvn Package'){
	   // Build using maven
	   
	   sh "${mvn} clean package deploy"
   }
   
   stage('deploy-dev'){
       def tomcatDevIp = '10.1.160.16'
	   def tomcatHome = 'C:\Program Files\Apache Software Foundation\Tomcat 9.0\bin'
	   def webApps = tomcatHome+'webapps/'
	   //def tomcatStart = "${tomcatHome}bin/startup.sh"
	   //def tomcatStop = "${tomcatHome}bin/shutdown.sh"
	   
	    }
   stage('Email Notification'){
		mail bcc: '', body: """Hi Team, You build successfully deployed
		                       Job URL : ${env.JOB_URL}
							   Job Name: ${env.JOB_NAME}
Thanks,
DevOps Team""", cc: '', from: '', replyTo: '', subject: "${env.JOB_NAME} Success", to: 'hari.kammana@gmail.com'
   
   }
}
