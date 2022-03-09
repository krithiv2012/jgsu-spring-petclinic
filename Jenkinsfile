// Powered by Infostretch 

timestamps {

node () {

	stage ('spring-petclininc - Checkout') {
 	 checkout([$class: 'GitSCM', branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '', url: 'https://github.com/krithiv2012/jgsu-spring-petclinic.git']]]) 
	}

	stage ('spring-petclininc - Build') {
 			// Shell build step
sh """ 
./mvnw package 
 """
		archiveArtifacts allowEmptyArchive: false, artifacts: 'target/*jar', caseSensitive: true, defaultExcludes: true, fingerprint: false, onlyIfSuccessful: false
		// JUnit Results
		junit 'target/surefire-reports/*xml' 
	}
}
}
