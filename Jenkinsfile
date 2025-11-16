pipeline {
    agent { label 'mactest_work1' }
     triggers {
        // GitHub Webhook 触发
        githubPush()
    }

    stages {
        stage('Checkout') {
            steps {
                checkout([
                    $class: 'GitSCM',
                    branches: [[name: '*/master']],
                    userRemoteConfigs: [[url: 'https://github.com/huanmood/mactest.git']],
                    gitTool: 'MacGit'  // ✅ 在这里指定你刚刚配置的 Git 工具名
                ])
            }
        }

        stage('Test') {
            steps {
                sh '''
                which git
                git --version
                echo "✅ Git clone and agent working on Mac!"
                '''
            }
        }
    }
}
