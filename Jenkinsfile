pipeline {
agent any
stages {
stage('build') {
steps {
sh 'ant -f build.xml -v'
}
}
stage('unit Tests') {
steps {
sh 'ant -f test.xml -v'
junit 'reports/result.xml'
}
}
}
post {
always {
archiveArtifacts artifacts: 'dist/*.jar', fingerprint: true
}
}
}
