pipeline {
    agent { label 'agent-kube' }

    stages {
        stage('kubectl') {
            steps {
                script {
                    sh '/usr/bin/kubectl version'
                    sh '/usr/bin/kubectl apply -f secret.yaml'
                    sh '/usr/bin/kubectl apply -f configmap.yaml'
                    sh '/usr/bin/kubectl apply -f deployment.yaml'
                    sh '/usr/bin/kubectl apply -f service.yaml'
                }
            }
        }
    }
}