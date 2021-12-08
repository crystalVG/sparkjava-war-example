pipeline {
    agent { node { label "CrystalVasquez" }}
    stages {
        stage('primeros pasos') {
            steps {
                sh '''
                echo "hola"
                echo $CV_Parameter
                '''
            }
        }
        stage('build') {
            steps {
                sh '''
                docker run -t --rm --name my-maven-project -v "$(pwd)":/usr/src/mymaven -w /usr/src/mymaven maven:3.3-jdk-8 mvn clean install
                '''
            }
        }
         stage('deploy') {
            steps {
                sh '''
                docker cp "/root/workspace/CV_Folder/Crystal_pipeline/target/sparkjava-hello-world-1.0.war" interesting_mclaren:"/usr/local/tomcat/webapps"
                '''
            }
        }
    }
}
