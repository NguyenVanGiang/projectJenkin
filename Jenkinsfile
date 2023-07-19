node('master'){
	
	stage('Code Checkout'){
		checkout develop
	}
	
	stage('Build'){
		sh "mvn clean install -Dmaven.test.skip=true"
	}

}
