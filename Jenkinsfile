pipeline {
    agent { label 'mactest_work1' }  // ✅ Mac 节点标签

    triggers {
        githubPush()  // ✅ GitHub 提交时自动触发
    }

    stages {
        stage('Checkout') {
            steps {
                echo "🔍 拉取最新代码..."
                checkout([
                    $class: 'GitSCM',
                    branches: [[name: '*master']],
                    userRemoteConfigs: [[
                        url: 'https://github.com/huanmood/mactest.git',
                        credentialsId: 'first_github_token'
                    ]]
                ])
            }
        }

        stage('Build') {
            steps {
                echo "🏗️ 在 Mac 上执行构建任务..."
                sh '''
                echo "当前目录: $(pwd)"
                ls -al
                # 这里写你的构建命令，比如
                # xcodebuild -scheme YourApp -sdk iphoneos
                '''
            }
        }

        stage('Post') {
            steps {
                echo "✅ 构建完成"
            }
        }
    }
}
