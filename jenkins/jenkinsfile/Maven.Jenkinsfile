pipeline {
    agent any
    environment {
        JDK_HOME = tool 'JDK21'
        MAVEN_HOME = tool 'M3'

        PATH = "${JDK_HOME}/bin:${MAVEN_HOME}/bin:${env.PATH}"
    }
    stages {
        stage('GIT Checkout') {
            steps {
                git '%STUDENT_GIT_URL%'
            }
        }
        stage('Build & Test') {
            steps {
                script {
                    sh "java -version"
                    sh "mvn -version"
                    sh "mvn clean install"
                    sh "mvn test"
                }
            }
        }
    }
}