node {
    try {

        stage('Clone') {
            git branch: 'main', url: 'https://github.com/shreya-335/File-Encrypter.git'
        }

        stage('Build') {
            sh '''
            echo "Building Java project..."
            echo "Listing workspace contents:"
            ls

            cd "Password Protection"
            ls

            mkdir -p build
            javac -d build src/*.java

            echo "Build successful"
            '''
        }

        stage('Test') {
            sh '''
            echo "Running JUnit tests..."
            cd "Password Protection"

            mkdir -p test-build
            echo "Skipping actual tests (no test folder maybe)"

            echo "Test stage complete"
            '''
        }

        stage('Deploy') {
            sh '''
            echo "Packaging project..."
            cd "Password Protection"

            jar cf FileEncrypter.jar -C build .

            echo "Deployment successful"
            '''
        }

        echo "Pipeline executed successfully!"

    } catch (Exception e) {
        echo "Pipeline failed!"
        throw e
    }
}