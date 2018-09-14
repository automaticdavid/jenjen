
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

            def jh = env.JENKINS_HOME
            def (jn, jb) = env.JOB_NAME.split('/')
            def ji = env.BUILD_ID
            def file = jh + '/jobs/' + jn + '/branches/' + jb + '/builds/' + ji + '/injectedEnvVars.txt'  
            
            towervars=[:]
            readFile(file).split('\n').each { line ->
                l=line.split("=",2)
                k=l[0]
                v=l[1]
                towervars[k]=v
            }

            echo towervars["VAR_NAME"]

        } 
    }    

            // readFile("input.csv").split('\n').each { line -> ... }

            // def varMap = [:]
            // def binding = new Binding(varMap)
            // def shell = new GroovyShell(binding)
            // shell.(inj)
            // echo varMap

            // def inj = readFile file
            // echo inj


            // echo env.VAR_NAME
            // echo env.BUILD_NUMBER
            // echo env.JOB_NAME
            // def vvv = System.getenv('VAR_NAME')
            // def ttt = binding.variables.get('VAR_NAME')
            // echo sh(returnStdout: true, script: 'env')
            
            // env.WORKSPACE = pwd()

            // def inj = readFile file
            // def inj2 = inj.replaceFirst(/=/, "='")
            // def inj3 = inj2.replaceFirst(/$/, "'")
