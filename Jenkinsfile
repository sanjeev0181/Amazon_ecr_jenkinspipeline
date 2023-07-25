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
            stage("Logging into AWS ECR") {
                steps {
                    sh "aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 243250302162.dkr.ecr.us-east-1.amazonaws.com"
                }
            }
        }
    
}