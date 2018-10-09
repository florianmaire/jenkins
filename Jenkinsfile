// Powered by Infostretch 

timestamps {

node () {

	stage ('APP-IC - Checkout') {
 	 checkout([$class: 'GitSCM', branches: [[name: '*/master']],  doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'git-login',  url: 'https://github.com/florianmaire/jenkins.git']]]) 
	}
	stage ('APP-IC - Build') {
 			// Maven build step
	withMaven(maven: 'maven-3') { 
 			if(isUnix()) {
 				sh "mvn clean package " 
			} else { 
 				bat "mvn clean package " 
			} 
 		} 
	}
}
}
