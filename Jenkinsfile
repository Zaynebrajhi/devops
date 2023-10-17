pipeline{
  agent any
  tools {
    maven 'maven'
  }
  stages {
    stage ("Clean up"){
      steps {
        deleteDir()
      }
    }
    stage ("Clone repo"){
      steps {
        sh "git clone https://github.com/Zaynebrajhi/devops"
      }
    }
    stage ("Generate backend image"){
      steps{
        dir("devops"){
          sh "mvn clean install"
          sh "docker build -t devops2 ."
        }
      }
    }
    stage ("Run docker compose"){
      steps {
        dir("devops"){
        sh "docker compose up -d"
      }}}}}
