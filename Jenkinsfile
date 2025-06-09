pipeline { 
	agent any
	tools{
		maven 'Maven'
	}
	stages{
		stage('Checkout'){
			steps{
				git branch: 'master', url: 'https://github.com/Madhu635/MyMavenApp03.git'
			}
		}
		stage('Build'){
			steps{
				sh 'mvn clean package'
			}
		}
		stage('Test'){
			steps{
				sh 'mvn test'
			}
		}
		stage('Run application'){
			steps{
				sh 'java -jar target/MyMavenApp-1.0-SNAPSHOT.jar'
			}
		}
	}
	post{
		success{
			echo 'build and deployment success'
		}
		failure{
			echo 'build and tasks failed'
		}
}
}
