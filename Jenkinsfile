pipeline {
    agent any
    
    // 移除 triggers 块，在 Jenkins 项目配置中设置
    
   stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/huanmood/mactest.git'
            }
        }
   }}
