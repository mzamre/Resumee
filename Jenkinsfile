pipeline{
    agent any
      
    stages{
        stage('building maven project'){
            steps{
                sh '''
                cd /home/mohit/resume
                mvn install
                cp /home/mohit/resume/target/resume.war /home/mohit/Downloads/apache-tomcat-9.0.89/webapps
                '''
            }
        }
           
           

    }
}
