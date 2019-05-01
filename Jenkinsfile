pipeline {
    environment {
        registryURL = 'https://10.73.122.51:4500'
        registry = "10.73.122.51:4500/karthikeyan_c01"
        registryCredential = 'docker_dtr'
        dockerReleaseFile = 'release_dockerfile'
    }
    agent any
    stages {
        stage('Cloning Git') {
            steps {
                git url: 'https://github.com/karthik1113bitcoin/dbs_cust.git'
            }
        }
        stage('Preprocessing sources') {
            steps {
                sh 'echo preprocessing step'
            }
        }
        stage('Build Release Image') {
            steps { 
                sh 'docker --version'
                sh 'echo $BUILD_NUMBER'
                sh 'rm -rf cust'
                sh 'rm -f cust.tgz'
                sh 'mkdir cust'
                sh 'mv COMMON_CNTRY DFBANK1 ./cust/'
                sh 'tar -cvf cust.tgz cust'           
                script {
                    dockerReleaseImage = docker.build("$registry/cn_release:$BUILD_NUMBER","-f $dockerReleaseFile .")
                }
               // sh 'docker build -f release_dockerfile -t $registry/cn_release:latest -t $registry/cn_release:5.0 .'
            }
        }
        stage('Deploy Release Image') {
            steps { 
                sh 'echo Deploy release image'
                script {
                    docker.withRegistry( registryURL, registryCredential ) {
                        dockerReleaseImage.push()
                    }
                }
            }
        }
    }
}
