def templatePath = 'https://raw.githubusercontent.com/karthik1113bitcoin/dbs_cust/master/dbs_template.json'
def templateName = 'dbs-cust-template'
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
                sh 'pwd'
               // sh 'docker build -f release_dockerfile -t $registry/cn_release:latest -t $registry/cn_release:5.0 .'
            }
        }
        stage('cleanup') {
            steps {
                script {
                    openshift.withCluster() {
                        openshift.withProject() {
                            // delete everything with this template label
                            openshift.selector("all", [ template : templateName ]).delete()
                            // delete any secrets with this template label
                            if (openshift.selector("secrets", templateName).exists()) {
                                openshift.selector("secrets", templateName).delete()
                            }
                        }
                    }
                } // script
            } // steps
        } // stage
       stage('create') {
            steps {
                script {
                    openshift.withCluster() {
                        openshift.withProject() {
                            // create a new application from the templatePath
                            openshift.newApp(templatePath)
                        }
                    }
                } // script
            } // steps
        } // stage
        stage('Build1') {
            steps {
                script {
                    openshift.withCluster() {
                        openshift.withProject() {
                            // create a new application from the templatePath
                            //openshiftBuild(buildConfig: 'release-build', showBuildLogs: 'true')
                            openshift.selector("bc", "release-build").startBuild("--from-file=./cust.tgz","--wait=true","--follow")
                        }
                    }
                } // script
            } // steps
        } // stage 
        /*stage('build') {
            steps {
              script {
                 openshift.withCluster() {
                    openshift.withProject() {
                      def builds = openshift.selector("bc", templateName).related('builds')
                      timeout(1) { 
                        builds.untilEach(1) {
                          return (it.object().status.phase == "Complete")
                        }
                      }
                    }
                  }
               }
            }
        }*/
    } //stages
}
