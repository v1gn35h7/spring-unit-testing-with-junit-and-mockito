pipeline {
    agent any
    stages {
       stage('Registering build artifact') {
            steps {
                echo 'Registering the metadata'
                echo 'Another echo to make the pipeline a bit more complex'
                registerBuildArtifactMetadata(
                    name: "build-artifacts-testing-AK-01-VPC-0002",
                    version: "1.0.02",
                    type: "docker",
                    url: "http://localhost-test-preprod:0002",
                    digest: "6f637064707039346163663237383938",
                    label: "vpc-ninja"
                )
            }
        }

    }
}
