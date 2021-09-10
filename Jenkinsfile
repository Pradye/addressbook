pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "Maven-Latest"
    }

    stages {
        stage('Compile') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/Pradye/addressbook.git'

                // Run Maven on a Unix agent.
                sh "mvn compile"

                  }

            
        }
         stage('CodeReview') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/Pradye/addressbook.git'

                // Run Maven on a Unix agent.
                sh "mvn pmd:pmd"

                  }

            
        }
         stage('UnitTest') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/Pradye/addressbook.git'

                // Run Maven on a Unix agent.
                sh "mvn test"

                  }

            
        }
         stage('Package') {
             agent {label 'linux_slave'}
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/Pradye/addressbook.git'

                // Run Maven on a Unix agent.
                sh "mvn package"

                  }

            
        }
    }
}
