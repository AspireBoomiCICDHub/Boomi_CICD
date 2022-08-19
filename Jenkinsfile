node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def scannerHome = tool 'AsBoomiCICDSonar';
    withSonarQubeEnv() {
      sh "${scannerHome}/bin/sonar-scanner
            -D sonar.login=admin \
            -D sonar.password=Aspire@123 \
            -D sonar.projectkey=Boomi_CICD \
            -D sonar.exclusions=vender/**,resources/**,**/*.java \
            -D sonar.host.url=http://172.28.113.130:9000/"
    }
  }
}
