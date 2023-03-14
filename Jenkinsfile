pipeline {
    agent {label ('dotnetagent')}
    triggers { pollSCM('* * * * *') }
    stages {
        stage('vcs') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/ravikiran2596/MusicStore.git'
            }
        }
        stage('build') {
            steps {
                sh 'dotnet restore ./MusicStore/MusicStore.csproj && dotnet build ./MusicStore/MusicStore.csproj'
            }
        }
        stage('test') {
            steps {
                sh 'dotnet test ./MusicStoreTest/MusicStoreTest.csproj'
            }
        }
    }
}