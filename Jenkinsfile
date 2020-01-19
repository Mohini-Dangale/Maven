node {
   stage 'checkout'
   
   git url: 'https://github.com/bogo-devops/game-of-life.git'
   
   ef mvnHome = tool 'M3'

   // Mark the code build 'stage'....
   stage 'Build'
   // Run the maven build
   sh "${mvnHome}/bin/mvn clean install"
   step([$class: 'JUnitResultArchiver', testResults: '**/target/surefire-reports/TEST-*.xml'])
   
   }
