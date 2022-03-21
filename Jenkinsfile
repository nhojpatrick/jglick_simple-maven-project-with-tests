podTemplate(containers: [containerTemplate(name: 'maven', image: 'maven', command: 'sleep', args: 'infinity')]) {
  node(POD_LABEL) {
    checkout scm
    container('maven') {
      sh './mvnw -B -ntp -Dmaven.test.failure.ignore verify'
    }
    junit '**/target/surefire-reports/TEST-*.xml'
  }
}
