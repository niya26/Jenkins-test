pipeline {
tools {
maven 'M3' 
        jdk 'jdk8'

}
    stage('check out') {
                          steps {
    git branch: 'master',url: 'https://github.com/niya26/Jenkins-test/'
                          }
                      }
    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'MAVEN_HOME') {
                    sh 'mvn -f amrld/pom.xml clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'MAVEN_HOME') {
                    sh 'mvn -f amrld/pom.xml test'
                }
            }
        }


        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'MAVEN_HOME') {
                    sh 'mvn -f amrld/pom.xml deploy'
                }
            }
        }
    }
}
