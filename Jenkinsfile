pipeline{
    agent any
    stages{
        stage ('checkout the code from SCM'){
            steps{
                echo 'checkout the code'
            }
        }
        stage ('Build the project'){
            steps{
                echo 'building the project'
                sh 'mvn clean install -DskipTests'
                
            }
        }
        stage('Sonarqube'){
            steps{
                echo 'Sonar Codequality'
                sh '''     
                mvn clean verify sonar:sonar \
                      -Dsonar.projectKey=Mobilestore \
                      -Dsonar.host.url=http://51.120.76.63:9000 \
                       -Dsonar.login=sqp_42b09ab7ef5e085a6e9f1eb9b722b847334ea352
                
                   '''
            }
        }

    }
}