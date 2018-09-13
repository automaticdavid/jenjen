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
            
            // env.WORKSPACE = pwd()
            // def version = readFile "${env.WORKSPACE}/version.txt"

            def jenhome = env.JENKINS_HOME
            def (jobname, jobbranch) = env.JOB_NAME.split('/')
            def jobbuild = env.BUILD_ID
            
            def file = jenhome + '/jobs/'  + jobname + '/branches/' + jobbranch + '/builds/' + jobbuild + '/injectedEnvVars.txt'  

            echo file

            def inj = readFile file
            echo inj

            echo currentBuild.buildVariables


        } 
    }    