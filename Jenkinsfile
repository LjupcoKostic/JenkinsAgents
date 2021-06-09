pipeline {
    agent core-agent
	
	stages {
	        stage('SCM'){
		        checkout([$class: 'GitSCM', branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/LjupcoKostic/JenkinsAgents']]])
	        }
		stage('Build'){
			sh 'dotnet build ConsoleApp'
		}
		stage('Test'){
			echo 'Execute unit tests'
		}
		stage('Package'){
			echo 'Zip it up'
		}
		stage('Deploy'){
			echo 'Push to deployment'
		}
		stage('Archive'){
			archiveArtifacts artifacts: 'ConsoleApp/bin/Debug/netcoreapp3.1/*.*'
		}	
	}
}

