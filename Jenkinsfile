pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                script {
                    catchError(buildResult: 'FAILURE', stageResult: 'FAILURE') {
                        bat("clang main.c -o main.exe")
                        archiveArtifacts artifacts: "main.exe", allowEmptyArchive: false, onlyIfSuccessful: false
                    }
                }
            }
        }
    }
}
