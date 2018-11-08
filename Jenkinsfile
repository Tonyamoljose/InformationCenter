pipeline {
	agent none
    stages {
         stage('Build') {
		 agent {docker { image 'maven:3-jdk-8-alpine' 
		 args '-v /data/jenkins/tools/maven/.m2:/root/.m2'
			       } }
            steps {		
                 git credentialsId: 'GitHub', url: 'https://github.com/Tonyamoljose/InformationCenter.git'
                sh 'mvn clean deploy  -Dmaven.test.skip=true sonar:sonar'      
            }
        } 
         
    }
}
