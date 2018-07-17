node("android") {
  stage("Checkout") {
    checkout scm
  }

  stage("Prepare") {
    sh 'chmod +x ./gradlew'
  }

  stage("Build") {
    sh './gradlew clean assembleDebug' //comment for debug builds
  }

  uncomment the following stage if running a release build
  stage("Sign") {

  }

 stage("Archive") {
    archiveArtifacts artifacts: 'app/build/outputs/apk/**/app-debug.apk', excludes: 'app/build/outputs/apk/*-unaligned.apk'
  }
}
