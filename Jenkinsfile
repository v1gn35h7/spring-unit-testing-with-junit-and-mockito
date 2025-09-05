pipeline {
    agent any
    stages {
        stage('Stage 0') {
    steps {
        withEnv(["MY_ENV=VALUE"]) {
            registerBuildArtifactMetadata(
                name: "my-artifact-stage-preprod-test-0023",
                version: "0.0.23",
                type: "docker",
                url: "http://your-url-here.com",
                digest: "6u637064707039346163663930",
                label: "pre-prod"
            )
        }
    }
    }
    }
}
