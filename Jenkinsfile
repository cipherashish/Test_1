pipeline{
    agent any
    stages{        
        
        
         
        stage ('Build and Test')
        {
            steps{
                    sh "mvn clean install"
            }
        }
         
        stage('Code Quality')
        {
             environment {
                scannerHome=tool 'sonar scanner'
            }
             steps{
                withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId:'Hemant_Sonar_Cred', usernameVariable: 'USER', passwordVariable: 'PASS']])
                 {
                     sh "mvn $USER:$PASS -Dsonar.host.url=http://18.224.155.110:9000"
                 }
             }
         }
         
   
   
}
}
