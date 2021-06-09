pipeline {
       agent {
                core-agent
       }
	
	stages {
	        stage('SCM'){
			steps{
		                checkout([$class: 'GitSCM', branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/LjupcoKostic/JenkinsAgents']]])
			}		       
	        }
		stage('Build'){
			steps{
			        sh 'dotnet build ConsoleApp'
			}			
		}
		stage('Test'){
			steps{
				echo 'Execute unit tests'
			}			
		}
		stage('Package'){
			steps{
				echo 'Zip it up'
			}			
		}
		stage('Deploy'){
			steps{
				echo 'Push to deployment'
			}
		}
		stage('Archive'){
			steps{
				archiveArtifacts artifacts: 'ConsoleApp/bin/Debug/netcoreapp3.1/*.*'
			}
		}	
	}
}

