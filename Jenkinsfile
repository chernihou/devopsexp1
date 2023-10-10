pipeline {
    agent any
tools{
    maven 'maven'
}
    stages {
        stage("clean up") {
            steps {
                echo deleteDir()
            }
        }
    
    
        stage("clone repo") {
            steps {
                sh "git clone https://github.com/chernihou/devopsexp1"
            }
        }
    

        stage("Generate backend image") {
            steps {
                dir ("devopsexp1"){
                    sh "mvn clean install"
                    sh "docker build -t devopsexp1 ."
                }
            }
        }
    
    
        stage("Run docker compose") {
            steps {
                dir("devopsexp1"){
                sh "docker compose up -d"
            }
        }
    }  
}
}
