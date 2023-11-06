pipeline {
    agent any
  stages {
     stage('Getting project from Git') {
            steps{
      			checkout([$class: 'GitSCM', branches: [[name: '*/main']],
			extensions: [],
			userRemoteConfigs: [[url: 'https://github.com/marwenesprit/marwen.git']]])
            }
        }
        stage('Cleaning the project') {
            steps {
                sh "mvn -B -DskipTests clean"
            }
        }

        stage('Artifact Construction') {
            steps {
                sh "mvn -B -DskipTests package"
            }
        }
  }
}
