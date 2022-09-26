// multistage
pipeline {
    agent any

        stages {
            stage('Source') {
                steps {
                    git url: 'https://github.com/SushmithaNayak23/SpringBuildDockerImage.git'
                }
            }
            
            stage('Docker bulid') {
                steps {
                    script {
                        bat 'docker build -t 1stdoc .'
                        bat 'docker images'
                    }
                }
            }
      
             stage('Build docker image') {
                steps {
                    script {
                        bat 'docker-compose up'
                    }
                }
            }
            /*stage('Build') {
                steps {
                    script {
                        def mvnHome = tool 'LocalMaven'
                        bat "${mvnHome}\\bin\\mvn -B verify"
                    }
                }
            }*/
            
            /*stage('Push image to hub') {
                steps {
                    script {
                        withCredentials([string(credentialsId: 'dockerhub_pwd', variable: 'dockerhub_pwd')]) 
                        {
                          echo "docker login -u nayaksushmitha -p ${dockerhub_pwd}"
                          echo  "docker push"
                        }
                    }
                }
            }*/
            
            
            /*stage('SonarQube Analysis') {
                steps {
                    script {
                        def mvnHome = tool 'LocalMaven'
                        withSonarQubeEnv() {
                            bat "${mvnHome}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=dockerhub_image"
                        }
                    }
                }
            }*/
            
            
            
            
           /* stage ("Artifactory Publish"){
                steps{
                    script{
                            def server = Artifactory.server 'artifactory_instanceid'
                            def rtMaven = Artifactory.newMavenBuild()
                            //rtMaven.resolver server: server, releaseRepo: 'jenkins-devops', snapshotRepo: 'jenkins-devops-snapshot'
                            rtMaven.deployer server: server, releaseRepo: 'sts_repo', snapshotRepo: 'sts_snapshot'
                            rtMaven.tool = 'LocalMaven'
                            
                            def buildInfo = rtMaven.run pom: '$workspace/pom.xml', goals: 'clean install'
                            rtMaven.deployer.deployArtifacts = true
                            rtMaven.deployer.deployArtifacts buildInfo

                            server.publishBuildInfo buildInfo
                    }
                }
        }*/
    }
}
