node {  
    stage('Build') { 
        sh 'mvn compile'
    }
    stage('Test') { 
        sh 'mvn test'
    }
    stage('Package') { 
       sh 'mvn package'
    }
}
