pipeline {
    agent {
        docker {
            image 'jenkins/centos7_java8u20_ant192_mvn350' 
            args '-v /home/docker/.m2:/home/jenkins/.m2 -v /etc/timezone:/etc/timezone:ro -v /etc/localtime:/etc/localtime:ro' 
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package' 
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
}
