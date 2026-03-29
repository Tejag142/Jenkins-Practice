pipeline {
    agent {
        label 'JAVA-AGENT-1'
    }
    environment{

    }
    options{
        timeout(time: 30, unit: 'MINUTES')
        disableConcurrentBuilds()
    }
    parameters{
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: '', defaultValue: '', description: 'Enter the name of the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'toggle this value')
        choice(name: 'CHOICE', choices: ['one', 'two', 'three'], defaultValue: 'pick one')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter the Passsword')

    }

    stages {
        stage ( 'Build' ) {
            steps {
                script {
                    sh """

                    echo 'Hello ${params.PERSON} Building done'

                    """
                }
                
            }
        }
        stage ( 'Test' ) {
            steps {
                echo 'Testing done'
            }
        }
        stage ( 'Deploy' ) {
            steps {
                echo 'Deploy done'
            }
        }
    }
    post {
        always {
            echo 'I will always say Hello again!'
        }
        success {
            echo 'Hello Success'
        }
        failure {
            echo 'Hello Failure'
        }
    }
}