pipeline {

    agent any

        stages{
            
            stage('Build')
            {
                steps{
                    echo "Building the project"
                    bat 'mvn clean package'
                    bat "docker build . -t tomcatwebapp:${env.BUILD_ID}"
                }
                post{
                    success{
                        echo "Build Successful"
                    }
                    failure{
                        echo "Build unsuccessful. Check console output for details"
                    }
                }
            }
        }
    
}