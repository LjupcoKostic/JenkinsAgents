anode('core-agent'){
	stage('SCM'){
		checkout([$class: 'GitSCM', branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/LjupcoKostic/JenkinsAgents']]])
	}
	stage('Build'){
		try{
		sh 'dotnet build ConsoleApp'
		}finally{
		archiveArtifacts artifacts: 'ConsoleApp/*.*'
		}
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
		archiveArtifacts artifacts: 'ConsoleApp/*.*'
	}
}
