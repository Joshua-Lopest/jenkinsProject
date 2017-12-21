node {
   def mvnHome
   stage('Preparation') {
      // Get github repo
      git 'https://github.com/Joshua-Lopest/jenkinsProject.git'
      // 'M3' Maven tool must be configured Jenkins' global configuration.           
      mvnHome = tool 'M3'
   }
   stage('Build') {
      // Run the maven build
      // Running JaCoCo by default inside build
      if (isUnix()) {
         sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean package checkstyle:checkstyle pmd:pmd findbugs:findbugs"
      } else {
         bat(/"${mvnHome}\bin\mvn" -Dmaven.test.failure.ignore clean package checkstyle:checkstyle pmd:pmd findbugs:findbugs/)
      }
   }
   stage('Results') {
      junit '**/target/surefire-reports/TEST-*.xml'
      archive 'target/*.jar'
   }
   stage('Health Check'){
       //Jenkins health config based on metrics. Code generated by using Jenkins pipeline syntax generator of each plugin
      jacoco changeBuildStatus: true, maximumBranchCoverage: '50', maximumClassCoverage: '50', maximumComplexityCoverage: '50', maximumInstructionCoverage: '50', maximumLineCoverage: '50', maximumMethodCoverage: '50', minimumBranchCoverage: '25', minimumClassCoverage: '25', minimumComplexityCoverage: '25', minimumInstructionCoverage: '25', minimumLineCoverage: '25', minimumMethodCoverage: '25'
      checkstyle canComputeNew: false, canRunOnFailed: true, defaultEncoding: '', healthy: '25', pattern: ' **/checkstyle-result.xml', unHealthy: '50'
      pmd canComputeNew: false, canRunOnFailed: true, defaultEncoding: '', healthy: '25', pattern: ' **/pmd.xml', unHealthy: '50'
      findbugs canComputeNew: false, canRunOnFailed: true, defaultEncoding: '', excludePattern: '', healthy: '25', includePattern: '', pattern: '**/findbugsXml.xml', unHealthy: '50'
   }
   
   
}