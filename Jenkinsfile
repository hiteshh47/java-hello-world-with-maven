pipeline {
    agent any

    tools {
         maven 'maven'
         jdk 'java'
    }

    stages{
        stage('build'){
            steps{
             sh 'mvn package'
            }
        }
        stage('deploy'){
            steps{
               sshPublisher(publishers: [sshPublisherDesc(configName: 'Ansible_Controller', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '/home/ansibleadmin/java-app', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '/var/lib/jenkins/workspace/counter-app@2/target/jb-hello-world-maven-0.2.0.jar')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
                }            
            }
    }
    

}
