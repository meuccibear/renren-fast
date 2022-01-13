podTemplate(label: label, containers: [
  containerTemplate(name: 'maven', image: 'maven:3.6-alpine', command: 'cat', ttyEnabled: true),
  containerTemplate(name: 'docker', image: 'docker', command: 'cat', ttyEnabled: true),
  containerTemplate(name: 'kubectl', image: 'cnych/kubectl', command: 'cat', ttyEnabled: true),
  containerTemplate(name: 'helm', image: 'cnych/helm', command: 'cat', ttyEnabled: true)
], volumes: [
  hostPathVolume(mountPath: '/root/.m2', hostPath: '/var/run/m2'),
  hostPathVolume(mountPath: '/home/jenkins/.kube', hostPath: '/root/.kube'),
  hostPathVolume(mountPath: '/var/run/docker.sock', hostPath: '/var/run/docker.sock')
]) {
node(label) {
   def mvnHome
   def workspace = pwd()

   stage('Prepare') {
       echo "1.Prepare Stage"
       checkout scm
//        updateGitlabCommitStatus name: 'build', state: 'pending'

       project_module = '.'
       sh "pwd"
       pom = readMavenPom file: "${project_module}/pom.xml"
       echo "group: ${pom.groupId}, artifactId: ${pom.artifactId}, version: ${pom.version}"
//        script {
// //            build_tag = sh(returnStdout: true, script: 'git rev-parse --short HEAD').trim()
// //            build_tag = "${env.BRANCH_NAME}-${build_tag}"
// //            if (env.BRANCH_NAME != 'master' && env.BRANCH_NAME != null) {
// //                build_tag = "${env.BRANCH_NAME}-${build_tag}"
// //            }
//            currentBuild.displayName = BUILD_NUMBER + "_" +build_tag
//        }
   }


//    stage('Preparation') { // for display purposes
//       // Get some code from a GitHub repository
// //       git 'http://192.168.161.118:8080/git/demo.git'
//       // Get the Maven tool.
//       // ** NOTE: This 'M3' Maven tool must be configured
//       // ** in the global configuration.
//       mvnHome = tool 'M3'
//    }
//    stage('Build') {
//       // Run the maven build
//       if (isUnix()) {
//          sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean package"
//
//       } else {
//          bat(/"${mvnHome}\bin\mvn" -Dmaven.test.failure.ignore clean package/)
//       }
//    }
//    stage('Deploy') {
//       sh "'/scripts/deploy.sh' ${workspace} deploy"
//    }
}
}
