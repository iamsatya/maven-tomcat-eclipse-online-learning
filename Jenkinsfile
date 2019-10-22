pipeline {
	agent any
	stages {
		stage('pull') {
			steps {
				sh "git pull https://github.com/iamsatya/maven-tomcat-eclipse-online-learning"
			}
		}
		
		stage(clean) {
			steps {
				sh "mvn clean"
			}
		}
		
		stage(build) {
			steps {
				sh "mvn package"
			}
		}
		stage(deploy) {
			steps {
				sh "curl --insecure --user tomcat:password -T ./target/*.war sftp://172.31.42.200/opt/tomcat/webapps/"
				}
			}
		}
	}
