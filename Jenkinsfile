node {

    stage('Clone repository') {
        git branch: "master", url: "git@github.com:thirupathi-chintu/AWS_ECR_JENKINS.git", credentialsId: "devops"
    }

    stage('Build image') {
        sh "docker build -t 534***385.dkr.ecr.us-east-2.amazonaws.com/bttrm-receipt-consumer:latest ."
    }

    stage('Push image') {
        docker.withRegistry('https://534***385.dkr.ecr.us-east-2.amazonaws.com', 'ecr:us-east-2:bttrm-backend-ecr') {
            sh "docker push 534***385.dkr.ecr.us-east-2.amazonaws.com/bttrm-receipt-consumer:latest"
        }
    }
}
