pipeline {
    agent any
    tools {
        maven 'Maven 3.3.9'
        jdk 'jdk8'
    }
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                '''
            }
        }

        stage ('Build') {
            steps {
                sh '''
                    mvn package
                    java -jar target/hello-0.1.0.jar
                ''' 
            }
            /*post {
                success {
                    junit 'target/surefire-reports/**/*.xml' 
                }
            }*/
        }
    }
}
