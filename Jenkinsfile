pipeline {  
    agent any  
    stages {  
            stage ('Git-Checkout') {  
                steps{
                    git credentialsId: '48888eb7a93ffceeaada4d2c9cc4170916b3fd41', url: 'https://github.com/AshokHule/CICD-Development.git'
                    echo "Checkout successful";
                } 
            }
            stage ('Compile') {  
                  steps{
                    bat label: '', script: 'mvn compile'
                    echo "test successful";
                    
                } 
            }
            stage ('Build') {  
                  steps{
                    bat label: '', script: 'mvn clean'
                    bat label: '', script: 'mvn package'
                    echo "build successful";
                    
                } 
            }
             stage ('Test') {  
                  steps{
                    bat label: '', script: 'mvn test'
                    echo "test successful";
                } 
            }
            
        stage ('Deploy') {
            steps{
            //deploy adapters: [tomcat9(credentialsId: '0ec60cd3-c147-467b-bc23-ceabd7954e28', path: '', url: 'http://localhost:8080/')], contextPath: 'jenkins_calci', onFailure: false, war: '**/*.war'
             echo "Deploy successful";
            }
        }
        stage ('Monitor') { 
           steps{ 
             echo "Now you can monitor!";
           }
        }
    }
}
