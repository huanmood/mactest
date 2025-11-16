pipeline {
    agent { label 'mactest_work1' }
    
    // 移除 triggers 块，在 Jenkins 项目配置中设置
    
    stages {
        stage('Checkout') {
            steps {
                checkout([
                    $class: 'GitSCM',
                    branches: [[name: '*/master']],
                    userRemoteConfigs: [[
                        url: 'https://github.com/huanmood/mactest.git',
                        // 如果需要认证，添加 credentialsId
                        // credentialsId: 'your-github-credential'
                    ]],
                    gitTool: 'MacGit'
                ])
            }
        }
        // ... 其他 stages
    }
}
