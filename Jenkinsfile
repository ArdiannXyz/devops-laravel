node {
    checkout scm

    // Build
    stage("Build") {
        docker.image('php:8.4-cli').inside('--entrypoint= -u root') {
            sh 'apt-get update && apt-get install -y git zip unzip curl'
            sh 'curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer'
            sh 'composer install --no-scripts --no-interaction'
        }
    }

    // Testing
    stage("Test") {
        docker.image('ubuntu:24.04').inside('-u root') {
            sh 'echo "Ini adalah test"'
        }
    }
}
