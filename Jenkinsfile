pipeline {
    environment {
        registry = "10.73.122.51:4500/karthikeyan_c01"
        registryCredential = 'docker_dtr'
    }
    agent any
    stages {
        stage('Cloning Git') {
            steps {
                git url: 'https://github.com/karthik1113bitcoin/dbs_cust.git'
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
                sh 'docker build -f release_dockerfile -t $registry/cn_release:latest -t $registry/cn_release:5.0 .'
            }
        }
    }
}
