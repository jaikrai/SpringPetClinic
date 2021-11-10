pipeline{
    agent{label 'master'}
    tools{ mavan 'M3'}
    stages{
        steps{
            git branch: 'min', url: 'https://github.com/jaikrai/SpringPetClinic.git'
        }
        stage('Build'){
            steps{
                sh 'mvn compile'
            }
        }
        stage('Test'){
            steps{
                sh 'mvn test'
            }
        }
        stage('Package'){
            steps{
                sh 'mvn package'
            }
        }
        stage('Deploy'){
            steps{
                sh 'java -jar /var/lib/jenkins/workspace/PetClinceDeclarativePipeline'
            }
        }

    }
}
