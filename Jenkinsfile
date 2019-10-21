pipeline {
	agent any
	stages {
		stage('pull') {
			steps {
				sh "git clone https://github.com/iamsatya/maven-tomcat-eclipse-online-learning.git"
			}
		}
		
		stage(clean) {
			steps {
				sh "/opt/maven/bin/mvn clean"
			}
		}
		
		stage(build) {
			steps {
				sh "/opt/maven/bin/mvn package"
			}
		}
		stage(deploy) {
			steps {
				sh "curl --insecure --user tomcat:password -T /target/*.war sftp://172.31.7.169/opt/tomcat/webapps/"
				}
			}
		}
	}
