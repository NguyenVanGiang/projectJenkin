node('master'){
	
	stage('Code Checkout'){
		checkout develop
	}
	
	stage('Build'){
		sh "mvn clean install -Dmaven.test.skip=true"
	}
	
	
	stage('Code Deployment'){
		deploy adapters: [tomcat8.5(credentialsId: 'TomcatCreds', path: '', url: 'http://14.232.210.205:8084//')], contextPath: 'giangnvTest', onFailure: false, war: 'target/*.war'
	}
}
