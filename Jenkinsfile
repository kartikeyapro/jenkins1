pipeline {
    agent any

    tools {
        maven 'maven-3.8.6'
    }
    stages {
        stage('Git Clone') {
            steps {
			git credentialsId: 'ksgit', url: 'https://github.com/kartikeyapro/ks.git'
               
            }
			}
		stage('Maven Version') {
			steps {
			 sh 'mvn --version'
			}
			}
		stage('Maven Clean'){
		     steps{
			 sh 'mvn clean'
			}
			}
		stage('SonarQube Scan'){
			steps{
			sh 'mvn sonar:sonar -Dsonar.host.url=http://34.125.211.116:9000 -Dsonar.login=a942c851734b6769e63896eb0a0fc198c387f2c7'
			}
			}
			
		stage('Maven Validate') {
			steps {
			 sh 'mvn validate'
			}
			}
		stage('Maven Compile'){
		     steps{
			 sh 'mvn compile'
			}
			}
		stage('Maven Test'){
			steps{
			sh 'mvn test'
            }
			}
		stage('Maven Package'){
			steps{
			sh 'mvn package'
            }
			}
		stage('Maven Deploy'){
			steps{
			sh 'mvn deploy'
            }
			}
    }
}

