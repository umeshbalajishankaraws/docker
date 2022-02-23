pipeline {
  agent any
  stages {
    stage('Cloning Git') {
      steps {
         sh "
         echo "+++++++cloing repo from git started+++++++"
        git([url: 'https://github.com/umeshbalajishankaraws/docker.git', branch: 'master'])
        sh "echo "+++++++cloing repo from git completed+++++++"
        "
      }
    }
    stage('Building image') {
      steps{
     sh "
     echo "+++++++Docker Image Builg Started+++++++"
     sh "sudo docker build -t nginx:v1 . > build.log"
     sh "echo "+++++++Docker Image Builg Completed+++++++"
     "
          }
      }   
     stage('Docker Creation') {
      steps{
     sh "
     echo "Docker create Build Started"
     sh sudo docker run -dt --name nginx --publish 9000:80 nginx_webserver:v1
     sh echo "Docker create Build Completed"
     "
          }
      } 
  }
}
