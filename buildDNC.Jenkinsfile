def dockerImage;

node('image-agent'){
	stage('SCM'){
		checkout([$class: 'GitSCM', branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/LjupcoKostic/JenkinsAgents']]]);
	}
	stage('build'){
		sh 'docker image build - < buildCoreAgent.Dockerfile'
	}	
}
