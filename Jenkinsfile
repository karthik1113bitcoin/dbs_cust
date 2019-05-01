pipeline {
    agent any
    stages {
        stage('Example') {
            steps {
                git url: 'https://github.com/karthik1113bitcoin/dbs_cust.git'
                sh 'docker --version'
                sh 'rm -rf cust'
                sh 'rm -f cust.tgz'
                sh 'mkdir cust'
                sh 'mv COMMON_CNTRY DFBANK1 ./cust/'
                sh 'tar -cvf cust.tgz cust'
                sh 'docker build -f release_dockerfile -t cn_release:latest -t cn_release:5.0 .'
            }
        }
    }
}
