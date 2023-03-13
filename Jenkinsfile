pipeline{
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
        stage('deploy'){
            steps{
               sshPublisher(publishers: [sshPublisherDesc(configName: 'Ansible_Controller', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '/home/ec2-user/java-app/bin', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '/var/lib/jenkins/workspace/counter-app@2/target/*.jar')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
            }            
        }
    }
}
