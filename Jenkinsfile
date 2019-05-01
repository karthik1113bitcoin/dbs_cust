pipeline {
    environment {
        registryURL = 'https://10.73.122.51:4500'
        registry = "10.73.122.51:4500/karthikeyan_c01"
        registryCredential = 'docker_dtr'
        dockerReleaseFile = 'release_dockerfile'
        dockerSITFile = 'sit_dockerfile'
        SIT_BASE_IMAGE = "10.73.122.51:4500/karthikeyan_c01/cn_fincore_cust_ucp"
        SIT_BASE_TAG = 'latest'
    }
    agent any
    stages {
        stage('Checking out Sources') {
            steps {
                sh 'echo Checking out sources...'
                git url: 'https://github.com/karthik1113bitcoin/dbs_cust.git'
            }
        }
        stage('Preprocessing sources') {
            steps {
                sh 'echo preprocessing step...'
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
        stage('Run static code analyzer') {
            steps { 
                sh 'echo Running stating code analyser...'
            }
        }
        stage('Deploy Release Image') {
            steps { 
                sh 'echo Deploy release image...'
                script {
                    docker.withRegistry( registryURL, registryCredential ) {
                        dockerReleaseImage.push()
                    }
                }
                sh 'docker rmi $registry/cn_release:$BUILD_NUMBER'
            }
        }
        stage('Build SIT image') {
            steps { 
                sh 'echo Build SIT image...'
                script {
                    dockerSITImage = docker.build("$registry/cn_fincore_cust_ucp:latest",
                                                  "-f $dockerSITFile --build-arg RELEASE_TAG=$BUILD_NUMBER,BASE_IMAGE=$SIT_BASE_IMAGE,BASE_TAG=$SIT_BASE_TAG .")
                } 
            }
        }
        stage('Deploy SIT Image') {
            steps { 
                sh 'echo Deploy SIT image...'
                script {
                    docker.withRegistry( registryURL, registryCredential ) {
                        dockerSITImage.push()
                    }
                }
                sh 'docker rmi $registry/cn_fincore_cust_ucp:$BUILD_NUMBER'
            }
        }
    }
}
