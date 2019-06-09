pipeline {
    environment {
        registryURL = 'https://10.73.122.51:4500'
        registry = "10.73.122.51:4500/karthikeyan_c01"
        registryCredential = 'docker_dtr'
        dockerReleaseFile = 'release_dockerfile'
        dockerSITFile = 'sit_dockerfile'
        release_image = 'cn_release'
        SIT_BASE_IMAGE = 'cn_fincore_cust_ucp'
        SIT_BASE_TAG = 'latest'
    }
    agent any
    stages {
        stage('Preprocessing Source conversion') {

            steps {
                sh 'echo preprocessing step...'
            }
        }
        stage('Build Release Image with changes') {
            steps {
                sh 'rm -rf cust'
                sh 'rm -f cust.tgz'
                sh 'mkdir cust'
                sh 'mv COMMON_CNTRY DFBANK1 ./cust/'
                sh 'tar -cvf cust.tgz cust'
                sh 'ls -lrt cust.tgz'
               // sh 'docker build -f release_dockerfile -t $registry/cn_release:latest -t $registry/cn_release:5.0 .'
            }
        }
    }
}
