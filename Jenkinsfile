pipeline
{
    agent any
    stages
    {
        stage('ContinuousDownload')
        {
            try
            {
                https://github.com/IMRAN5377/maven537.git
            }
            catch(exception e1)
            {
                mail bcc: '', body: 'jenkins is download fail', cc: '', from: '', replyTo: '', subject: 'download fail1', to: 'hunkimran@gmail.com'
                    exit(1)
            }
        }
        stage('ContinuousBuild')
        {
            try
            {
                sh 'mvn package'
            }
            catch (exception e2)
            {
                mail bcc: '', body: 'jenkins is download failllllllllllllllllllll', cc: '', from: '', replyTo: '', subject: 'download fail2', to: 'hunk@gmail.com'
                exit(2)
            }
        }
        stage('ContinuousDeployment')
        {
            try
            {
               deploy adapters: [tomcat9(credentialsId: 'bfb67f1d-2f4e-430c-bb8d-30584116bd00', path: '', url: 'http://172.31.51.212:9090')], contextPath: 'test1', war: '**/*.war'
            }
            catch(exception e3)
            {
               mail bcc: '', body: 'jenkins is download faill33333', cc: '', from: '', replyTo: '', subject: 'download fail3', to: 'hunkiiii@gmail.com'
                exit(3)
            }
        }
        stage('ContinuousTesting')
        {
            try
            {
               git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
               sh 'java -jar /home/ubuntu/.jenkins/workspace/DeclarativePipeline1/testing.jar'
            }
            catch(exceptione e3)
            {
                mail bcc: '', body: 'jenkins is download fail4444', cc: '', from: '', replyTo: '', subject: 'download fail4', to: 'hunkkkkk@gmail.com'
                exit(e4)
            }
        }
       
    }
    
    post
    {
        success
        {
            input message: 'Need approval from the DM!', submitter: 'srinivas'
               deploy adapters: [tomcat9(credentialsId: 'bfb67f1d-2f4e-430c-bb8d-30584116bd00', path: '', url: 'http://172.31.50.204:9090')], contextPath: 'prod1', war: '**/*.war'
        }
        failure
        {
            mail bcc: '', body: 'Continuous Integration has failed', cc: '', from: '', replyTo: '', subject: 'CI Failed', to: 'selenium.saikrishna@gmail.com'
        }
       
    }

    
    
    
    
    
    
}
