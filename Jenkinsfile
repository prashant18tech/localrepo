pipeline {
    agent any
    environment {
        KUBECONFIG = "/var/lib/jenkins/.kube/config"
    }
    stages {
        stage('Deploy to Minikube') {
            steps {
                sh '''
                echo "Using KUBECONFIG=$KUBECONFIG"
                kubectl get nodes
                kubectl apply -f nginx-deployment.yaml
                kubectl get pods -l app=nginx
                '''
            }
        }
    }
}

