podTemplate(containers: [
containerTemplate(name: 'docker', image: 'ninech/jnlp-slave-with-docker', ttyEnabled: true, command: 'cat')
]) {

node(POD_LABEL) {
stage('Build a Dockerfile') {
git 'https://github.com/jenkinsci/kubernetes-plugin.git'
container('docker') {
sh """
cd EmployeeDB
docker build -t demo-app-new .
"""
}
}
}
}
