node {
    // This step should not normally be used in your script. Consult the inline help for details.
    withDockerContainer('python:3.12.1-alpine3.19') {
        // some block
        stage('Build'){
            sh 'python -m py_compile sources/add2vals.py sources/calc.py'
            stash(name: 'compiled-results', includes: 'sources/*.py*')
        }
    }
    
}