node(label) {
   def mvnHome
   def workspace = pwd()

   stage('Clone') {
       echo "1.Clone Stage"
//        checkout scm
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
}
