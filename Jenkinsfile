pipeline{
    agent any
      
    stages{
        stage('checkout scm in mohit'){
            steps{
               sh '''
               cd /home/mohit
               git clone  https://github.com/mzamre/Resumee.git
               '''
           }  
        }
         stage('creating maven project'){
            steps{
                sh '''
                cd /home/mohit
                mvn archetype:generate -DgroupId=com.resume -DartifactId=resume -Dversion=1.0-SNAPSHOT -DinteractiveMode=false -DarchetypeArtifactId=maven-archetype-webapp
                '''
            }

        }
        stage('copying code to main'){
            steps{
                sh '''
                cd /home/mohit/resume/src/main/webapp
                rm -rf index.jsp
                cd /home/mohit/Resumee
                cp Mypic.jpeg index.html input.html myContact.html new.css /home/mohit/resume/src/main/webapp
                '''
            }
        }
        stage('building maven project'){
            steps{
                sh '''
                cd /home/mohit
                mvn install
                cp /home/mohit/resume/target/resume.war /home/mohit/Downloads/apache-tomcat-9.0.89/webapps
                '''
            }
        }
           
           

    }
}
