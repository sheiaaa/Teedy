pipeline {
    agent any
    tools {
        maven 'M3'
    }
    stages {
        stage('Maven 构建') {
            steps {
                bat 'mvn clean package -DskipTests'
            }
        }
        stage('PMD 代码检查') {
            steps {
                bat 'mvn pmd:pmd'
            }
        }
        stage('运行测试') {
            steps {
                bat 'mvn test'
            }
        }
        stage('生成测试报告') {
            steps {
                bat 'mvn surefire-report:report'
            }
        }
        stage('生成JavaDoc') {
            steps {
                bat 'mvn javadoc:jar'
            }
        }
    }
}