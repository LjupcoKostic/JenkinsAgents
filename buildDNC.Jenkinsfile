def dockerImage;

node('image-agent'){
	stage('SCM'){
		checkout([$class: 'GitSCM', branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/LjupcoKostic/JenkinsAgents']]]);
	}
	stage('build'){
		dockerImage = docker.build('ljupchokostic/core-agent:v$BUILD_NUMBER','./dotnetcore');
	}
	stage('push'){
		docker.withRegistry('', ''){dockerImage.push();}
	}
}
