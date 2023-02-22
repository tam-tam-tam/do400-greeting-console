pipeline{
    agent{
        label "nodejs"
    }
    stages{
        stage("Install dependencies"){
            steps{
                sh "npm ci"
            }
        }

        stage("Check Style"){
            steps{
                sh "npm run lint"
            }
        }

        stage("Test"){
            steps{
                sh "npm test"
            }
        }
	stage('Releasel) {
	    steps {
		sh '''
		    oc project gnjwlp-greetings
		    oc start-build greeting-console --follow --eait
		'''
	    } 
	}
    }
}
