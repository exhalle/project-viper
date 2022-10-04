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

                // To run Maven on a Windows agent, use
                // bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }

            post {
                // If Maven was able to run the tests, even if some of the test
                // failed, record the test results and archive the jar file.
                success {
                    sh 'cp $WORKSPACE/target/*.war /webapp'
                }
            }
        }
        stage("Puplish artifact to git") {
            steps {
                echo "========= START PUBLISH ARTIFACT TO GIT ============"
                
            }
        }
    }
}
