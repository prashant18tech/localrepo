pipeline {
    agent any
    environment {
        // Set KUBECONFIG and extend PATH
        KUBECONFIG = "/var/lib/jenkins/.kube/config"
        PATH = "/jenkin/local/bin:${env.PATH}"   // <-- Add kubectl directory to PATH
    }
    stages {
        stage('Deploy to Minikube') {
            steps {
                sh '''
                echo "PATH is: $PATH"
                echo "Using kubeconfig: $KUBECONFIG"
                kubectl version --client
                kubectl get nodes
                kubectl apply -f nginx-deployment.yaml
                '''
            }
        }
    }
}
