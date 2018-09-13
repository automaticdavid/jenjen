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
            echo vvv 
            env.WORKSPACE = pwd()
            def version = readFile "${env.WORKSPACE}/version.txt"
            echo version
        } 
    }    