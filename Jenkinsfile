node(){

	def sonarHome = tool name: 'SonarScanner', type: 'hudson.plugins.sonar.SonarRunnerInstallation'
	
	stage('Code Checkout'){
		checkout changelog: false, poll: false, scm: scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'GitHubCreds', url: 'https://github.com/anujdevopslearn/MavenBuild']])
	}
	stage('Build Automation'){
		sh """
			ls -lart
			mvn clean install
			ls -lart target

		"""
	}
	
	stage('Code Scan'){
		withSonarQubeEnv(credentialsId: 'SonarQubeCreds') {
			sh "${sonarHome}/bin/sonar-scanner"
		}
		
	}
	
	stage('Code Deployment'){
		deploy adapters: [tomcat9(credentialsId: 'TomcatCreds', path: '', url: 'http://14.232.210.205:8084//')], contextPath: 'giangnvTest', onFailure: false, war: 'target/*.war'
	}
}
