pipeline {
  agent { label 'linux_node1' }
  tools {
    maven 'MAVEN_HOME'
  }
  stages {
    stage('checkout') {
      steps {
        git 'https://github.com/mahasweta-das/myProject.git'
      }
    }
    stage('Build') {
      steps {
        sh 'mvn clean compile'
      }
    }
    stage('Test') {
      steps {
        sh 'mvn test'
        junit '**/target/surefire-reports/TEST-*.xml'
      }
    }
    stage('Package') {
      steps {
        sh 'mvn package'
      }
    }
  }
}
