node{
    stage("SCM Checkout"){
        checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'Github-Username-Password', url: 'https://github.com/MaulikZalavadiya/FlaskDockerJenkins.git']])    
	}
    stage("docker build"){
		script{
			sh "docker build -t flask-app:1.1 -f Dockerfiles/Dockerfile.flask ."
		}
    }
	stage("docker run"){
		script{
			sh "docker run -it -d -p 5000:5000 --name flask-app-singlestage flask-app:1.1"
		}
	}
}
