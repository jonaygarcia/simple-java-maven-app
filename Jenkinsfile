pipeline {
    agent {
        docker {
            image 'centos7_java8u20_mvn350_ant192' 
            args '-v /root/.m2:/root/.m2 -v /etc/timezone:/etc/timezone:ro -v /etc/localtime:/etc/localtime:ro' 
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
