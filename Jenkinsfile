node {
	echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
	checkout scm

	stage('Build') {
		sh 'pdflatex cv.tex'
	}

	stage('Build Slo') {
		sh 'pdflatex cv_slo.tex'
	}
}
