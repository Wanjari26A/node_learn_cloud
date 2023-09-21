pipeline{
    agent any
    tools {nodejs "Node"}
    stages {
        stage('Clone Repository'){
            steps{
                git branch: 'main',
                    url: 'https://github.com/Wanjari26A/node_learn_cloud.git'
            }
        }
        
        // stage('Install Dependencies'){
        //     steps {
        //         bat 'npm install'
        //     }
        // }
        //  stage('Install pm2'){
        //     steps {
        //         bat 'npm install pm2 -g'
        //     }
        // }
        
        // stage('Deploy'){
        //     steps {
        //         bat 'pm2 startOrRestart pm2.config.json'
        //     }
        // }

        stage ("read file 1st ")
        {
            steps
            {
                script{
                    dir('learnJenkins')
                    {
                        def sourceData = readFile(file: "test-server/configure/sourceFile_${params.ENVIRONMENT}.json")
                        println(sourceData)
                    }

                    dir('originalConfig')
                    {
                        def destonationData = readFile(file: 'configuration.json')
                        println(destonationData)
                    }
                }
            }
        }

        stage ("copy file")
        {
            steps
            {
                script{
                    def data = ''
                    dir('learnJenkins')
                    {
                        data = readFile(file: "test-server/configure/sourceFile_${params.ENVIRONMENT}.json")
                    }

                    dir('originalConfig')
                    {
                        writeFile(file: 'configuration.json', text: data)
                    }
                }
            }
        }

        stage ("read file 2nd ")
        {
            steps
            {
                script{
                    dir('learnJenkins')
                    {
                        def sourceData = readFile(file: "test-server/configure/sourceFile_${params.ENVIRONMENT}.json")
                        println(sourceData)
                    }

                    dir('originalConfig')
                    {
                        def destonationData = readFile(file: 'configuration.json')
                        println(destonationData)
                    }
                }
            }
        }
    }
}
