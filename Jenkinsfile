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
                withMaven(maven : 'MAVEN_HOME') {
                    sh 'mvn pom.xml clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'MAVEN_HOME') {
                    sh 'mvn pom.xml test'
                }
            }
        }


        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'MAVEN_HOME') {
                    sh 'mvn pom.xml deploy'
                }
            }
        }
    }
}

