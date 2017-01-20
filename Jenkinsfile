node {
	echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
	checkout scm

	CV_BRANCH = sh (
		script: 'git rev-parse --abbrev-ref HEAD',
		returnStdout: true
	).trim()

	stage('Test') {
		echo "Running on branch ${env.BRANCH_NAME}"
	}

	stage('Build') {
		sh 'pdflatex cv.tex'
	}

	if (${CV_BRANCH} == "master") {
        stage('Build Slo') {
            sh 'pdflatex cv_slo.tex'
        }
    }
}
