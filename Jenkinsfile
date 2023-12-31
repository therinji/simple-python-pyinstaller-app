node {
    
    withDockerContainer('python:3.12.1-alpine3.19') {
    // some block
        stage('Build'){
            sh 'python -m py_compile sources/add2vals.py sources/calc.py'
            stash(name: 'compiled-results', includes: 'sources/*.py*')
        }
    }

    withDockerContainer('qnib/pytest') {
    // some block
        stage('Test'){
            sh 'py.test --junit-xml test-reports/results.xml sources/test_calc.py' 
        }
    }

    stage('Manual approval') {
        input message: 'Lanjutkan ke tahap Deploy?'
    }
}