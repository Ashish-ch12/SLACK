pipeline {
	agent any 
	
	stages {
	    stage('Checkout') {
	        steps {
			checkout scm			       
		      }}
		stage('Build') {
	           steps {
			  sh '/home/ashish/Documents/mavenfile/apache-maven-3.9.6/bin/mvn install'
	                 }}
		stage('Deployment'){
		   steps {
		sh 'cp target/SLACK.war /home/ashish/Documents/mavenfile/apache-tomcat-9.0.88/webapps'
			}}
		
                   stage('Slack Notification') {
            steps {  
                slackSend baseUrl: 'https://hooks.slack.com/services/', channel: 'Ashish12', color: 'good', message: 'this is slack', notifyCommitters: true, teamDomain: 'slack12', tokenCredentialId: '1bc0b855-a9c6-4803-9147-487b0d243958'
}}
}}
