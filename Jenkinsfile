pipeline {
    agent any

    environment {
        BRANCH_NAME = 'main'
        GIT_URL = 'https://github.com/Fii55/awscicd.git'
        IMAGE_TAG = 'Fii55/awscicd'
        IMAGE_VERSION = "${BUILD_NUMBER}"
    }

    stages{
        stage('git checkout'){
            steps{
                git branch: "${BRANCH_NAME}", url: "${GIT_URL}"
            }
        }
        stage('docker build'){
            steps{
                sh 'docker build -t "${IMAGE_TAG}:${IMAGE_VERSION}" .'
                sh 'docker images'
            }
        }
    }
}