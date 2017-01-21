node {
	echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
	checkout scm

	stage('Test') {
		echo "Running on branch [${env.BRANCH_NAME}]"
	}

	stage('Build') {
		sh 'pdflatex cv.tex'
	}

	if ("${env.BRANCH_NAME}" == "master") {
        stage('Build Slo') {
            sh 'pdflatex cv_slo.tex'
        }
    } else {
        stage('Echo non-master') {
            echo "Running on non-master branch [${env.BRANCH_NAME}]"
        }
    }
}
