
pipeline {
    agent any
    stages {
        stage('git clone'){
            steps{
               // Git Url and branch details for Code Cloning
               // git branch: 'main', url: 'https://github.com/saidaraok/Jenkins-Zero-To-Hero.git'
               
               // Webhook integration
               // Step1: Use Below SCMGIT url, where credential were also integrated.
               // Step2: Add the Webhook in github. Depending on the jenkins url, we might need to expose to internet so that github will access it
               // Step3: In Jenkins enable Build Triggers Option: GitHub hook trigger for GITScm polling
               checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'github_crd', url: 'https://github.com/saidaraok/Jenkins-Zero-To-Hero.git']])
            }
        }
        stage ('c code build') {
            steps {
                // Print message that build is about to start
				sh '''
				echo "Building InProgress"
				pwd
				cd stage1
				ls -la 
				make clean test
				echo "Build is done"
				sleep 20
				'''
            }
        }
		stage ('c code test') {
			steps {
				sh '''
				echo 'Testing InProgress'
				cd stage1
				pwd
				./test
				echo 'Testing completed'
				sleep 20
				'''
			}
		}
    }
}

