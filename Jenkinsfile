pipeline{
    agent any
    stages{
        stage("git clone"){
            steps{
                git url: "https://github.com/StarAgileDevOpsTraining/star-agile-insurance-project"
                echo "git checkout"
            }
        }
        stage("compile the code"){
            steps{
                sh 'mvn compile'
            }
        }
        stage("test the code"){
            steps{
                sh 'mvn test'
            }
        }
        stage("QA check"){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage("package the code"){
            steps{
                sh 'mvn package'
            }
        }
        stage("run docker file"){
            steps{
                sh 'docker build -t myimg .'
            }
        }
        stage("expose the container"){
            steps{
                sh 'docker run -dt -p 8084:8081 --name co1 myimg'
            }
        }
    }
}





