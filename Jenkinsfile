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
                    def data = readFile(file: 'sometestFolder/configuration_main.json')
                    println(data)

                    def data_1 = readFile(file: 'configuration.json')
                    println(data_1)
                }
            }
        }

        stage ("copy file")
        {
            steps
            {
                script{
                    def data = readFile(file: 'configuration.json')

                    def data_1 = readFile(file: 'sometestFolder/configuration_main.json')

                    writeFile(file: 'sometestFolder/configuration_main.json', text: data)
                    sh "ls -l"
                }
            }
        }

        stage ("read file 2nd ")
        {
            steps
            {
                script{
                    def data = readFile(file: 'sometestFolder/configuration_main.json')
                    println(data)

                    def data_1 = readFile(file: 'configuration.json')
                    println(data_1)
                }
            }
        }
    }
}
