node() {
   def mvnHome
   def workspace = pwd()

   stage('Clone') {
       echo "1.Clone Stage"
//        checkout scm
       project_module = '.'
       sh "pwd"
       pom = readMavenPom file: "${project_module}/pom.xml"
       echo "group: ${pom.groupId}, artifactId: ${pom.artifactId}, version: ${pom.version}"
       stage('mvn install') {
                   sh 'pwd'
                   docker.image('maven:3.6.0-jdk-8-alpine').inside('-v /volume1/docker/.m2:/root/.m2') {
                       sh 'mvn --version'
                       sh 'mvn clean install'
                   }
               }
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
