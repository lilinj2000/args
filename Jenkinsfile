pipeline {
  agent {
    docker {
      image 'lilinj2000/dev:centos7.gcc'
    }
  }

  environment {
    home_3rd = '/var/jenkins_home/dist_pkg/3rd/centos7'
    home_libs = '/var/jenkins_home/dist_pkg/libs/centos7'
    home_app = '/var/jenkins_home/dist_pkg/app/centos7'
  }

  stages {
    stage('install') {
      steps {
        sh '''
home_args=${home_3rd}/args
make install DESTDIR=${home_args}
   	'''
      }
    }
  }

  post { 
    always { 
      cleanWs()
      }
  }
}
