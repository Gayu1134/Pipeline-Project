pipeline {
agent any
stages {
stage('unit Tests') {
steps {
sh 'ant -f build.xml -v'
junit 'reports/results.xml'
}
}
stage('build') {
steps {
sh 'ant -f build.xml -v'
}
}
}
post {
always {
archiveArtifacts artifacts: 'dist/*.jar' , fingerprint: true
}
}
}
