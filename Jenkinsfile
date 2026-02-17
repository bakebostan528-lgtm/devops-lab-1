pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                echo 'GitHub-тан кодты аламыз...'
                checkout scm
            }
        }

        stage('Check Files') {
            steps {
                echo '📄 Файлдарды тексеру...'
                sh '''
                    echo "=== РЕПОЗИТОРИЙДЕГІ ФАЙЛДАР ==="
                    ls -la
                    
                    if [ -f Dockerfile ]; then echo "✅ Dockerfile табылды"; else echo "❌ Dockerfile жоқ"; fi
                    if [ -d srs ]; then echo "✅ srs папкасы табылды"; else echo "❌ srs папкасы жоқ"; fi
                '''
            }
        }

        stage('Docker Theory') {
            steps {
                echo 'ТЕОРИЯ DOCKER: Егер Jenkins Docker ішінде болса, келесі жолы контейнерлерді баптаймыз.'
            }
        }
    }

    post {
        always {
            echo '=== ЖҰМЫС АЯҚТАЛДЫ ==='
        }
    }
}