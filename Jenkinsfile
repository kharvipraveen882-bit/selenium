pipeline{
	agent any
	
	tools{
		maven 'maven'
	}
	
	stages{
		stage('Checkout'){
			steps{
				git branch: 'main', url: 'https://github.com/kharvipraveen882-bit/selenium.git'
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
		stage('Run Application'){
			steps{
				sh 'mvn exec:java -Dexec.mainClass="com.example.App"
'
			}
		}
	}
	post{
		success{
			echo 'Build and deployment successfull'
		}
		failure{
			echo 'Build Failed'
		}
	}
}
