pipeline {
     agent { label 'agent-kube' }

     tools {
         git 'Default'
     }

     stages {
     stage('Check env') {
                 steps {
                     sh 'echo $PATH'
                     sh 'whoami'
                     sh 'which kubectl || echo "kubectl not found"'
                     sh 'kubectl version --client || echo "kubectl failed"'
                 }
             }
         stage('kubectl') {
             steps {
                 script {
                     sh 'kubectl version'
                     sh 'kubectl apply -f secret.yaml'
                     sh 'kubectl apply -f configmap.yaml'
                     sh 'kubectl apply -f deployment.yaml'
                     sh 'kubectl apply -f service.yaml'
                 }
             }
         }
     }
 }