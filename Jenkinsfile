pipeline {
    agent { label "ProjectA"}

    stages {
        stage('1st stage -git clone') {
            steps {
                git branch: 'main', url: 'https://github.com/rajugunaki/html-fashion.git'
            }
        }
        stage('2nd stage -install httpd') {
            steps {
                sh 'yum install httpd -y'
                sh 'systemctl start httpd && systemctl enable httpd'
            }
        }
        stage('3rd stage - copy the index.html file to the path') {
            steps {
                sh 'cd /var/jenkins/workspace/pipeline-html'
                sh 'ls'
                sh ' cp -r /var/jenkins/workspace/pipeline-html/* /var/www/html'
            }
        }
    }
}
