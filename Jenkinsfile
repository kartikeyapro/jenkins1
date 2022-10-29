node {  
    stage('git clone') {
	git credentialsId: 'ksgit', url: 'https://github.com/kartikeyapro/ks.git'
       
    }
	stage('maven version') {
	sh 'mvn --version'
     
    }
    stage('maven clean') {
	sh 'mvn clean'
     
    }
    stage('maven validate') {
	sh 'mvn validate'
       
    }
	stage('maven compile') {
	sh 'mvn compile'
     
    }
    stage('maven test') {
	sh 'mvn test'       
    }
	stage('maven package') {
	sh 'mvn package'
       
    }
	stage('maven deployment') {
	sh 'mvn deploy'
       
    }
    
    
}
