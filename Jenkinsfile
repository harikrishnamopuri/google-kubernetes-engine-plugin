pipeline {
    agent any
    environment {
        PROJECT_ID = '$PROJECT_ID'
        CLUSTER_NAME = '$CLUSTER_NAME'
        LOCATION = '$CLUSTER_LOCATION'
        CREDENTIALS_ID = "$CREDENTIALS_ID"
    }
    stages {
        stage('Deploy to GKE') {
            steps{
                step([
                $class: 'KubernetesEngineBuilder',
                projectId: env.PROJECT_ID,
                clusterName: env.CLUSTER_NAME,
                location: env.LOCATION,
                manifestPattern: 'manifest.yaml',
                credentialsId: env.CREDENTIALS_ID,
                verifyDeployments: true])
            }
        }
    }
}
