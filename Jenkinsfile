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
			sh 'mvn sonar:sonar -Dsonar.host.url=http://34.125.90.50:9000 -Dsonar.login=7248e83955b6d29c46e8914613d0b49cbd189809'
			
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

