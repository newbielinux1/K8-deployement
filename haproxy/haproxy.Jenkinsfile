pipeline
{
    agent
    {
        label 'worker1'
    }

    stages
    {
        stage('env-setup')
        {
            
            steps{
                   sh '''
                   mkdir -p /opt/haproxy
                   chmod 777 /opt/haproxy/
                   cp haproxy/haproxy.cfg /opt/haproxy/
                   '''
               }
        
        }
        stage('start-dockercompose')
        {
            
            steps{
                   sh '''
                   pwd
                   cd haproxy
                   docker-compose -f haproxy-compose.yml down | exit 0
                   docker-compose -f haproxy-compose.yml up -d
                   '''
               }
        
        }
    }
}