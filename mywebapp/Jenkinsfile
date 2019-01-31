pipeline
{
    agent any
    stages
    {
        stage('code checkout')
        {
            steps
               {
                    git 'https://github.com/Karthikcse1212/webapp.git'
                }
        }
        stage('build')
        {
            steps
            {
                dir('C:\\Users\\KM00601119\\.jenkins\\workspace\\JavaPipeLine1\\mywebapp')
                {
                    bat label: '', script: 'mvn verify'
                }
            }
        }
        stage('deploy')
        {
            steps
            {
               bat 'copy mywebapp\\target\\mywebapp-0.0.1-SNAPSHOT.war "D:\\Software Backups\\Tomcat\\New folder\\apache-tomcat-8.5.37\\webapps"'
            }
        }
        stage('selenium test integration')
        {
            steps
            {
                git 'https://github.com/Karthikcse1212/JavaTestPass2.git'
                dir('C:\\Users\\KM00601119\\.jenkins\\workspace\\JavaPipeLine1\\JavaTestPassFail')
                {
                    bat label: '', script: 'mvn verify'
                }
            }
        }
    }
}
