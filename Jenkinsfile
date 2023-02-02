pipeline {
agent any
stages {
  stage('checkout') {
    steps {
      checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'bf75e321-78e0-4cdd-b25f-ba02ffd21d00', url: 'https://github.com/osamanaji/teavm-maven-webapp.git']])
    }
  }
stage('compile') {
    steps {
sh 'mvn compile'
    }
  }
  
  stage('package') {
    steps {
sh 'mvn package'
    }
  }
  
   /*stage('Print-working-directory') {
    steps {
sh 'pwd'
    }
  }*/
  
  
  stage('TomcatDeply') {
    steps {
    sshagent(['tomcat_server']) {
sh 'scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/teavm-maven-webapp-pipeline/target/teavm-maven-webapp-1.0-RELEASE.war ubuntu@172.31.22.111:/var/lib/tomcat9/webapps/'
}
    }
  }
  
 
}

}

