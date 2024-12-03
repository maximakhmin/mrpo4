pipeline { 
    agent any 
    stages { 
        stage("Build") { 
            steps { 
                echo "Сборка приложения..."
            } 
        } 
        stage("Test") { 
            steps { 
                echo "Тестирование приложения..."
            } 
        } 
        stage("Deploy") { 
            steps { 
                echo "Развёртывание приложения..."
            } 
        }
    }
    post { 
        always { 
            deleteDir() 
        } 
        failure { 
            echo "Сборка провалилась" 
            mail to: "maximakhmin@gmail.com", 
            subject: "${env.JOB_NAME} – Сборка № ${env.BUILD_NUMBER} провалилась", 
            body: "Для получения дополнительной информации о провале пайплайна, проверьте консольный вывод по адресу ${env.BUILD_URL}" 
        } 
    } 
}