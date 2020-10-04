pipeline{
    /* A Declarative Pipeline/
    agent any

    stages{
        stage('Build'){
            steps{
                sh 'mvn clean package'
            }
            post{
                success {
                    echo 'Now Archiving'
                    archiveArtifacts artifacts '**/targeet/*.war'
                }
            }
        }
        stage('Deploy to staging'){
            steps{
                build job:deploy-to-staging
            }
        } 

        stage('Deploy to Production'){
            steps{
                timeout(time:5, unit: 'DAYS'){
                    input message : "Approve PROD Deployment?"
                }
                build job:deploy-to-staging
            }
            post{
                success {
                    echo "Code deployed to production"
                }
                failure{
                    echo "Deployment failed"
                }
            }
        }               
    }
}