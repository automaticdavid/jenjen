
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

            // echo env.VAR_NAME
            // echo env.BUILD_NUMBER
            // echo env.JOB_NAME
            // def vvv = System.getenv('VAR_NAME')
            // def ttt = binding.variables.get('VAR_NAME')
            // echo sh(returnStdout: true, script: 'env')
            
            // env.WORKSPACE = pwd()
            // def version = readFile "${env.WORKSPACE}/version.txt"

            def jh = env.JENKINS_HOME
            def (jn, jb) = env.JOB_NAME.split('/')
            def ji = env.BUILD_ID
            
            def file = jh + '/jobs/' + jn + '/branches/' + jb + '/builds/' + ji + '/injectedEnvVars.txt'  
            tower_env = load file

            echo tower_env.VAR_NAME

            // def inj = readFile file
            // echo inj

        } 
    }    