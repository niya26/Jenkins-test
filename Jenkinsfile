pipeline {
    agent any

    stages {
         stage ('SCM checkout') {

            steps {
                git 'https://github.com/niya26/Jenkins-test/'
                }
            }
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'MAVEN_HOME') {
                    sh 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'MAVEN_HOME') {
                    sh 'mvn test'
                }
            }
        }


        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'MAVEN_HOME') {
                    sh 'mvn deploy'
                }
            }
        }
    }
}
