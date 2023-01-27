pipeline {
    
	agent any

	tools {
        maven "MAVEN3"
    }
	
    environment {
        SNAP_REPO = 'vprofile-snapshot'
        NEXUS_USER = 'admin'
        NEXUS_PASS = 'Nexus2023'
        RELEASE_REPO = 'vprofile-release'
        CENTRAL_REPO = 'vpro-maven-central'
        NEXUSIP = '54.172.18.146'
        NEXUSPORT = '8081'
        NEXUS_GRP_REPO = 'vpro-maven-group'
        NEXUS_LOGIN = 'nexuslogin'
    }
	
    stages{
        
        stage('BUILD'){
            steps {
                sh 'mvn -s pom.xml -DskipTests install'
            }


}

stage('Test') {
           steps {
            sh 'mvn test'
           }
        }
        
        stage('Checkstyle Analysis'){
            steps {
                sh 'mvn -s pom.xml checkstyle:checkstyle'
            }
        }
    }
}