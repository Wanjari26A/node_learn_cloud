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

        // stage ("copy file")
        // {
        //     steps
        //     {
        //         script{
        //             cp sometestFolder/configuration_main.json configuration.json
        //         }
        //     }
        // }

        stage ("read file")
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
