
def do_make = {
    sh 'id'
    sh 'cat index.html.in > index.html'
    sh 'date >> index.html'
}
pipeline {
    agent none
    stages {
        stage("doit") {
            agent {
                docker "python:3.5"
            }
            steps {
                script {install_dependencies()}
                script {build_docs()}
                deleteDir()
            }
        }
    }
}
