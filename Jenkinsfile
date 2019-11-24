pipeline {
          
              agent {
          
                  label "master"
              }
      
              stages {
          
                  stage("clone code") {
          
                      steps {
          
                          script {
          
                              // Let's clone the source
          
                              git 'https://github.com/kann1bal/CICDMaven.git';
          
                          }
          
                      }
          
                  }
          
                  stage ('Initialize 1sdsd234') {
                      steps {
                          
                              echo "PATH = ${PATH}"
                              echo "M2_HOME = ${M2_HOME}"
                          echo "JAVA_HOME = ${JAVA_HOME}"
                         
                      }
                  }
          
                  stage("mvn clean ") {
          
                      steps {
          
                          script {
          
                              // If you are using Windows then you should use "bat" step
          
                              // Since unit testing is out of the scope we skip them
          
                          bat   " mvn clean "
          
                          }
          
                      }
          
                  }
          
                  stage("mvn package ") {
          
                      steps {
          
                          script {
          
                              // If you are using Windows then you should use "bat" step
          
                              // Since unit testing is out of the scope we skip them
          
                           bat     'mvn package'
          
                          }
          
                      }
          
                  }
                   stage("create docker image ") {                   
                      steps {
				          checkout scm
				          
				              docker.withRegistry('https://registry.hub.docker.com', 'dockerHub') {
				          
				                  def customImage = docker.build("kann1bal/myimage")
				          
				                  /* Push the container to the custom Registry */
				                  customImage.push()
                          }
          
                      }
          
                  }
        

      
    

        

       

}





}