pipeline{
    agent {label "agentfarm"}
    stages {
        stage('Delete the workspace'){
            steps{
                cleanWs()
            }
        }
        stage('installing java and maven'){
            steps {
                script {
                    def maven_exists = fileExists '/usr/share/maven'
                    if (maven_exists == true) {
                        echo "Skipping Maven install - already installed"
                    } else {
                        sh 'sudo apt-get update -y && sudo apt-get upgrade -y'
                        sh 'sudo apt install -y wget tree unzip openjdk-11-jdk maven'
                        sh 'mvn -version'
                    }
                }
            }
        }
        stage('clone git repo'){
            steps {
                git branch: 'main', credentialsId: 'git-repo-creds', url: 'git@github.com:carocarolineline/java-springboot-sample-app.git'
            }
        }
    }
}
