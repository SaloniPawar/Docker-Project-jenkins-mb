pipeline{
    agent any
    stages{
    stage("Build"){
        steps{
            sh 'mvn clean install -Dskiptests'
        }
    }
    stage("Docker build"){
        steps{
            sh 'docker build -t docker-project:v1 .'
        }
    }
    stage("Docker images"){
        steps{
            sh 'docker images'
            sh 'docker ps'
        }
    }
    stage("Docker container"){
        steps{
            sh 'docker run -d -p 8082:8080 docker-project:v1'
            sh 'sleep 20'
            sh 'docker ps'
        }
    }
    }
  }
}
