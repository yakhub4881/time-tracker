pipeline{
    agent any
    stages
    {
        stage('checkout from SCM')
        {
            steps
            {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/yakhub4881/time-tracker.git']]])
            }
        }

        stage('compile')
        {
            steps{
                sh 'mvn compile'
            }
        }

        stage('test')
        {
            steps{
                sh 'mvn test'
            }
        }

        stage('package')
        {
            steps{
                sh 'mvn package'
            }
        }
    }
}
