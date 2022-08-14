<<<<<<< HEAD
node('built-in') 
=======
node('built-in') 
>>>>>>> 6925f12a62f7be71a42a77761cda6a894fed4456
{
    stage('CDow') 
    {
    git 'https://github.com/intelliqittrainings/maven.git'    
    //git 'https://github.com/devopsakhil5/turbo-train.git'
    }
    
    stage('CBui') 
    {
    sh 'mvn package'
    }   
    
    stage('CDep') 
    {
    deploy adapters: [tomcat9(credentialsId: '5a7a31c9-b554-42d7-963d-ee18bb1fb633', path: '', url: 'http://172.31.91.188:8080')], contextPath: 'testapps', war: '**/*.war'

    }
    
    stage('CTes') 
    {
    git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
    sh 'java -jar /home/ubuntu/.jenkins/workspace/sciptedpipeline4/testing.jar'
    
    }
    
    stage('CDel') 
    {
    deploy adapters: [tomcat9(credentialsId: '16e24626-f24b-4f75-935a-5855bf2517f1', path: '', url: 'http://172.31.29.147:8080')], contextPath: 'prods', war: '**/*.war'
    }
    
}

