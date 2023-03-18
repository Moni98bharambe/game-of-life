pipeline {
	agent {
		label {
				label "built-in"
				customWorkspace "/mnt/project"
				}
				
		}
	stages {
		stage ("mvn-install"){
			steps {
				sh "mvn clean install"
			}
		}
		stage ("stage-2") {
			steps {
			sh "docker run -itdp 8081:8080 --name maya tomcat:9"
			sh "docker cp /mnt/project/gameoflife-web/target/gameoflife.war maya:/usr/local/tomcat/webapps/"
			}
		}	
		
	}
	
	
}	
