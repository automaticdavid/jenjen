node {
    stage('Tower') {
        
            ansibleTower(
                towerServer: 'tower-cluster01',
                templateType: 'job',
                jobTemplate: 'dcl-ec2-create',
                importTowerLogs: true,
                removeColor: false,
                verbose: true,
                credential: '',
                extraVars: '''---
                    my_var:  "Jenkins Test"'''
            )
        
            echo env.BUILD_NUMBER
            echo env.JOB_NAME
            def vvv = System.getenv('VAR_NAME')
            def ttt = binding.variables.get('VAR_NAME')
            echo sh(returnStdout: true, script: 'env')
            echo sh(returnStdout: true, script: 'vvv')
            # env.WORKSPACE = pwd()
            # def version = readFile "${env.WORKSPACE}/version.txt"
            dev inj = readfile "/home/bitnami/apps/jenkins/jenkins_home/jobs/tower-multibranch/branches/jenjen/builds/8/injectedEnvVars.txt"
            echo inj
        } 
    }    