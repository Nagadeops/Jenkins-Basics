pipeline{
  agent any
  tools {
        maven 'maven-3' // Define Maven version here
    }
  stages {
    stage ('SCM Checkout') {
      steps {
        git 'https://github.com/Nagadeops/myapp'
      }
    }
    stage ('Compile-Package') {
      steps {
        // Get maven home path
       // def mvnHome =  tool name: 'maven-3', type: 'maven'   
        sh 'mvn clean install'
      }
    }
    stage('Test') {
      steps {
                sh 'mvn test'
      }
    }
    stage ('Email Notification') {
      steps {
        mail bcc: '', body: '''Hi Welcome to jenkins email alerts
        Thanks
        Naga''', cc: '', from: '', replyTo: '', subject: 'Jenkins Job', to: 'nagasang25@gmail.com'
      }
    }
  }
}
