pipeline {
    agent any 
        environment {
            AWS_ACCOUNT_ID="243250302162"
            AWS_DEFAULT_REGION="us-east-1" 
            IMAGE_REPO_NAME="aecr_jenkinspipeline"
            IMAGE_TAG=     "latest"
            REPOSITORY_URI = "${AWS_ACCOUNT_ID}.dkr.ecr.${AWS_DEFAULT_REGION}.amazonaws.com/${IMAGE_REPO_NAME}"
            // #243250302162.dkr.ecr.us-east-1.amazonaws.com/aecr_jenkinspipeline
        }
        stages {
            stage("build mvn") {
                steps{
                    sh "mvn clean package"
                }
            }
        }
    
}