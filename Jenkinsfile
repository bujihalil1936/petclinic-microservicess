pipeline {
    agent any

    environment {
        // Ortam değişkenlerini burada tanımlayabilirsiniz.
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'GitHub reposundan kod çekiliyor'
                git branch: 'main', url: 'https://github.com/bujihalil1936/petclinic-microservicess.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Uygulama derleniyor'
                // Build adımlarını buraya ekleyin, örneğin npm, mvn, gradle, vb.
                sh 'npm install'  // Node.js projesi için örnek
            }
        }

        stage('Run Tests') {
            steps {
                echo 'Testler çalıştırılıyor'
                // Test komutlarını buraya ekleyin
                sh 'npm test'  // Node.js test komutu
            }
        }

        stage('Deploy to Test Environment') {
            steps {
                echo 'Test ortamına dağıtım yapılıyor'
                // Burada deploy komutlarını yazabilirsiniz
                // Örneğin: 
                // sh 'scp -r dist/* user@server:/path/to/deploy'
                echo 'Deploy işleminden önce yapılacak adımlar'
            }
        }
    }

    post {
        always {
            echo 'Temizlik işlemi yapılıyor'
            // Cleanup işlemleri yapılabilir
        }
        success {
            echo 'Pipeline başarıyla tamamlandı!'
        }
        failure {
            echo 'Pipeline başarısız oldu!'
        }
    }
}


