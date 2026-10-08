pipeline {
    
    agent {
        label 'light'
    }
    
    options {
        timestamps() // Poner timestamp
        timeout(time: 10, unit: 'MINUTES') //Timeout máximo de ejecución
        buildDiscarder(logRotator(numToKeepStr: '5')) // Nos quedamos 5 builds
        disableConcurrentBuilds() // No aceptamos builds concurrentes
        disableRestartFromStage() // Solo aceptamos construcciones des del inicio
    }
    
    stages{
        
        stage('Checkout') { //Bajamos el código 
                steps {
                    git branch: 'master', url: 'https://github.com/Gromenaware/InitialBattleShipMaven'
                }
        }
        
        stage('Maven Execution') { //Construimos y validamos aplicación
                steps {
                    sh 'mvn install'
                }
        }
    }
    
    post {
        
        always { // Guardamos resultados de tests siempre
            junit 'target/surefire-reports/*.xml'
        }
        
        success { // Solo guardamos artefacto si es satisfactorio
            archiveArtifacts artifacts: 'target/*.jar', fingerprint: true, followSymlinks: false
        }
    }
}
