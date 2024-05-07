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
		sh 'sudo apt-get update -y && sudo apt-get upgrade -y'
		sh 'sudo apt install -y wget tree unzip openjdk-11-jdk maven'
		sh 'mvn -version'
            }
        }
        stage('Third Stage'){
            steps {
                echo "Third Stage nvjdaibnirael"
            }
        }
    }
}
