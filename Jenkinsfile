
pipeline {
    agent any
    stages {
        stage("build") {
            steps {
                sh '''
               mvn package
               cd target
               mv LoginWebApp.war $WORKSPACE
              
               pwd
               ls
                '''
            }
        }
        stage("build-Image") {
            steps {
                sh '''
               cd $WORKSPACE
               ls
               docker build -t oumar .
               docker rm -f vamala
               docker run -d --name vamala -P 8134:8080 oumar:latest
               docker ps | grep vamala
               docker login -u oumarkenneh -p $Amara1988
               //docker tag oumar:latest oumarkenneh/oumar

               docker push oumarkenneh/oumar
              '''
            }
        }
    }
}
