pipeline {
     agent any
         stages {
             stage('Build') {
                 steps {
                     echo 'Application is in Building Phase'
                     bat 'mvn clean install'
                     }
                 }
             stage('Test') {
                 steps {
                     echo 'Application is in Testing Phase'
                     bat 'mvn test'
                       }
                 }
                 stage('Deploy to Cloudhub') { 
                   environment {
                                 ANYPOINT_CREDENTIALS = credentials('saikarru4')
                               }
                   steps {
                            bat 'mvn package deploy -DmuleDeploy -DmuleVersion=4.3.0 -Dusername=saikarru4 -Dpassword=Sai12345 -DworkerType=Micro -Dworkers=1 -Dregion=us-west-2'
                         }
                    }
         }
     }
