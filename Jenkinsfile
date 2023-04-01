pipeline{
  agent any
  stages {
    stage ('Building Backend') {
      steps {
        bat 'mvn clean package -DskipTests=true'
      }
    }
    stage ('Unit Tests') {
      steps {
        bat 'mvn test'
      }
    }
    stage ('Deploy Backend') {
      steps {
        deploy adapters: [tomcat8(credentialsId: 'TomcatLogin', path:'', url:'http://localhost:8001/')], contextPath:'tasks-backend', war:'target/tasks-backend.war'
      }
    }
    stage ('API Tests') {
      steps {
        git url: 'git@github.com:nson22/tasks-api-test.git'
        bat 'mvn test'
      }
    }
    stage ('Deploy Frontend') {
      steps {
        dir('frontend'){
          git url: 'git@github.com:nson22/tasks-frontend.git'
          bat 'mvn clean package'
          deploy adapters: [tomcat8(credentialsId: 'TomcatLogin', path:'', url:'http://localhost:8001/')], contextPath:'tasks', war:'target/tasks.war'
        }
      }
    }
    stage ('Functional Tests') {
      steps {
        dir('functional-tests'){
          git url: 'git@github.com:nson22/tasks-functional-test.git'
          bat 'mvn test'
        }
      }
    }
    stage ('Deploy to Prod') {
      steps {
        echo 'Deploying to production'
      }
    }
  }
}