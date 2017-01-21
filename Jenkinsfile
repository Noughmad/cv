node {
	echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
	checkout scm

	stage('Test') {
		echo "Running on branch [${env.BRANCH_NAME}] => [${GIT_BRANCH}]"
	}

	stage('Build') {
		sh 'pdflatex cv.tex'
	}

	if ("${GIT_BRANCH}" == "master") {
        stage('Build Slo') {
            sh 'pdflatex cv_slo.tex'
        }
    } else {
        stage('Echo non-master') {
            echo "Running on non-master branch [${GIT_BRANCH}]"
        }
    }
}
