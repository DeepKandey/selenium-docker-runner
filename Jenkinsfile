pipeline{
	agent any
	stages{
		stage("Pull Latest Image"){
			steps{
			    //sh
				//bat "docker pull deepkandey/selenium-docker"
				sh "docker pull deepkandey/selenium-docker"
			}
		}
		stage("Start Grid"){
			steps{
			    //sh
				//bat "docker-compose up -d hub chrome firefox"
				sh "docker-compose up -d hub chrome firefox"
			}
		}
		stage("Run Test"){
			steps{
			    //sh
				//bat "docker-compose up search-module book-flight-module"
				sh "docker-compose up search-module book-flight-module"
			}
		}
	}
	post{
		always{
			archiveArtifacts artifacts: 'output/**'
			//bat "docker-compose down"
			sh "docker-compose down"
		    sh "sudo rm -rf output/"
		    //bat "rmdir /S /Q output"
		}
	}
}
