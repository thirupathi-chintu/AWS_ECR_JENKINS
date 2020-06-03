node {
    def app

    stage('Clone repository') {
        git branch: "master", url: "git@github.com:example-dev/go-queue-consumer.git", credentialsId: "jenkins-example-github"
    }

    stage('Build image') {
        sh "docker build --build-arg APP_NAME=receipts -t 534***385.dkr.ecr.us-east-2.amazonaws.com/bttrm-receipt-consumer:latest -f docker/prod/Dockerfile ."
    }

    stage('Push image') {
        docker.withRegistry('https://534***385.dkr.ecr.us-east-2.amazonaws.com', 'ecr:us-east-2:bttrm-backend-ecr') {
            sh "docker push 534***385.dkr.ecr.us-east-2.amazonaws.com/bttrm-receipt-consumer:latest"
        }
    }
}
