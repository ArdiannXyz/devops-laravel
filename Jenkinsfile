node {
    checkout scm

    // Build
    stage("Build") {
        docker.image('composer:2.7').inside('-u root') {
            sh 'composer install --no-scripts --no-interaction'
        }
    }

    // Testing
    stage("Test") {
        docker.image('ubuntu').inside('-u root') {
            sh 'echo "Ini adalah test"'
        }
    }
}
