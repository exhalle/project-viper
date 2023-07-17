pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "mvn"
    }

    stages {
        stage('Build') {
            steps {
                // Get some code from a GitHub repository
                git credentialsId: '2', url: 'https://github.com/GitAlleks/MVCAndHibernate'

                // Run Maven on a Unix agent.
                sh "mvn -Dmaven.test.failure.ignore=true clean package"

                
            }

            post {
                // If Maven was able to run the tests, even if some of the test
                // failed, record the test results and archive the jar file.
                success {
                    echo " TEST APP IN TOMCAT "
                    sh 'cp $WORKSPACE/target/*.war /webapp/ROOT.war'
                    echo " COPY to APP DIR for prod"
                    sh 'cp $WORKSPACE/target/*.war /$WORKSPACE/artifacts/ROOT.war'
                }
            }
        }
        stage("Publish artifact") {
            steps {
                echo "========= START PUBLISH ARTIFACT  ============"
                
            }
        stage(" START Docker compose file ")
            steps{
                echo " START Docker compose "
                echo " need add jenkins user to docker"
                echo "$pwd"
                sh 'docker-compose up -d --build'
            }
        }
    }
}
