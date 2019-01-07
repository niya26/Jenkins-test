pipeline {
        agent any
tools {
maven 'MAVEN_HOME' 
        jdk 'JAVA_HOME'

}
    
    stages {
            stage('check out') {
                          steps {
    git branch: 'master',url: 'https://github.com/niya26/Jenkins-test/'
                          }
                      }
        stage ('Compile Stage') {

            steps {
                
                    sh 'mvn clean compile'
                           }
        }

        stage ('Testing Stage') {

            steps {
               
                    sh 'mvn test'
                           }
        }


        stage ('Deployment Stage') {
            steps {
               
                    sh 'mvn deploy'
                    }
        }
    }
}
