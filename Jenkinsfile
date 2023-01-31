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
}

}
