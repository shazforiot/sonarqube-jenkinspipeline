node {
  stage('Clone the Git') {
    git 'https://github.com/shazforiot/GOL.git'
  }
  stage('SonarQube analysis') {
    def scannerHome = tool 'sq1';
    withSonarQubeEnv('sonarqube') {
      sh "${scannerHome}/bin/sonar-scanner \
      -D sonar.login=admin \
      -D sonar.password=admin \
      -D sonar.projectKey=sonarqubetest \
      -D sonar.exclusions=vendor/**,resources/**,**/*.java \
      -D sonar.host.url=http://192.168.1XX.XX:9000/"
    }
  }
}
