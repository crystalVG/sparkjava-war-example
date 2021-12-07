pipeline {
    agent { node { label "CrystalVasquez" }}
    stages {
        stage('primeros pasos') {
            steps {
                sh '''
                echo "hola"
                '''
            }
        }
        stage('build') {
            steps {
                sh '''
                mvn clean install
                '''
            }
        }
         stage('deploy') {
            steps {
                sh '''
                docker cp "/root/workspace/Pipeline_Crystal/target/sparkjava-hello-world-1.0.war" elegant_morse:"/usr/local/tomcat/webapps"
                '''
            }
        }
    }
}
