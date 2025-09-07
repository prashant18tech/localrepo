pipeline {
    agent any
    stages {
        stage('Deploy to Minikube') {
            steps {
                echo "Deploying Nginx to Minikube..."
                sh '''
                kubectl apply -f nginx-deployment.yaml
                echo "Pods after deployment:"
                kubectl get pods -l app=nginx
                '''
            }
        }
    }
}
