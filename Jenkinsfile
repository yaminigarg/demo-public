podTemplate(containers: [
containerTemplate(name: 'docker', image: 'ninech/jnlp-slave-with-dockere', ttyEnabled: true, command: 'cat')
]) {

node('docker_agent') {
stage('Build a Dockerfile') {
git 'https://github.com/yaminigarg/demo-public'
container('docker') {
sh '
cd EmployeeDB
docker build -t demo-app-new .'
}
}
}
}
