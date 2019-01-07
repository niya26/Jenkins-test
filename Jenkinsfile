pipeline {
tools {
name: 'JAVA_HOME', type: 'jdk'
name: 'MAVEN_HOME', type: 'maven'
name: 'GIT_HOME', type: 'git'
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
