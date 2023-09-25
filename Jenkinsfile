@Library('robel_shared_lib') _

pipeline {
    agent any    
    tools{
        maven "Maven-3.9.4"
    }
    stages {
        stage('Clone') {
            steps {
		git branch: 'main', url: https://github.com/mrobel/courses_web_app.git 
	}
        }
        stage('Maven Build'){
            steps{
              mavenBuild()
            }
        }
		stage('Code Review'){
			steps{
				sonarQube()
			}
		}
    }
}
