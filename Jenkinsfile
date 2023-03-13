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
               sshPublisher(publishers: [sshPublisherDesc(configName: 'Ansible_Controller', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: 'ansible-playbook /home/ansibleadmin/playbooks/download_jar_from_jenkins.yml -i /home/ansibleadmin/playbooks/hosts', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
                }            
            }
    }
    

}
