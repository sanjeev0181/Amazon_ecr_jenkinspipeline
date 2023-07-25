pipeline {
    agent any 
        environment {
            AWS_ACCOUNT_ID="243250302162"
            AWS_DEFAULT_REGION="us-east-1" 
            IMAGE_REPO_NAME="aecr_jenkinspipeline"
            IMAGE_TAG=     "Latest"
            REPOSITORY_URI = "${AWS_ACCOUNT_ID}.dkr.ecr.${AWS_DEFAULT_REGION}.amazonaws.com/${IMAGE_REPO_NAME}"        }
        stages {
            stage("build mvn") {
                steps{
                    sh "mvn clean package"
                }
            }
            stage("Building the docker images") {
                steps {
                    dockerImage = docker.build "${IMAGE_REPO_NAME}:${IMAGE_TAG}"
                    sh "docker tag ${IMAGE_REPO_NAME}:${IMAGE_TAG} ${REPOSITORY_URI}:$IMAGE_TAG"
                }
            }
        }
    
}