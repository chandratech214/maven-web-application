// Powered by Infostretch 

timestamps {

node () {

	stage ('flipkart-dev - Checkout') {
 	 checkout([$class: 'GitSCM', branches: [[name: '*/development']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'ad17f5ad-53a5-4c65-82fa-bc4a5e471bf7', url: 'https://github.com/chandratech214/maven-web-application.git']]]) 
	}
	stage ('flipkart-dev - Build') {
 			// Maven build step
	withMaven(maven: 'maven3.6.1') { 
 			if(isUnix()) {
 				sh "mvn clean deploy sonar:sonar " 
			} else { 
 				bat "mvn clean deploy sonar:sonar " 
			} 
 		} 
	}
}
}