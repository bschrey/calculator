pipeline {
	agent any
	stages {
		stage("Compile") {
			steps {
				sh "./mvnw compile"
			}
		}
		stage("Unit test") {
			steps {
				sh "./mvnw test"
			}
		}
		stage("Code Coverage") {
			steps {
				sh "./mvnw verify"
				publishHTML (target: [
					reportDir: 'target/site/jacoco',
					reportFiles: 'index.html',
					reportName: "JaCoCo Report"
				])
			}
		}
	}
}