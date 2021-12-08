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
                docker cp "/root/workspace/CV_Folder/Crystal pipeline/target/sparkjava-hello-world-1.0.war" interesting_mclaren:"/usr/local/tomcat/webapps"
                '''
            }
        }
    }
}
