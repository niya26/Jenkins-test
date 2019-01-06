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
