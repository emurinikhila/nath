pipeline {
    agent any

    stages {
        stage('continuous download') {
            steps {
                git 'https://github.com/boxfuse/boxfuse-sample-java-war-hello.git'
            }
        }
        stage('continuous build') {
            steps {
                sh 'mvn install'
            }
        }
        stage('continuous deployment') {
            steps {
              sh 'sshpass -p "nikhila" scp target/hello-1.0.war root@172.17.0.3:/var/lib/apache-tomcat-9.0.56/webapps'
            }
        }
    }
}

