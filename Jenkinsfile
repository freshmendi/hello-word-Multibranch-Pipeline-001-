pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                sh 'gradlew check'
            }
        }
    }
    post {
        always {
            junit 'build/reports/**/*.xml'
        }
			failure {
        mail to: '1142040298@qq.com',
             subject: "Failed Pipeline: ${currentBuild.fullDisplayName}",
             body: "Something is wrong with ${env.BUILD_URL}"
    
        }
    }

		
}