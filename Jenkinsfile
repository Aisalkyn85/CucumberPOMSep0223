agent: any
stages:
  - stage: Build
    steps:
      - script:
          name: Run Maven to build the project using Windows batch command
          code: |
            bat "mvn -Dmaven.test.failure.ignore=true clean package"

  - stage: Generate Cucumber HTML Reports
    steps:
      - script:
          name: Generate Cucumber HTML Reports
          code: |
            cucumber 'reports/json-reports/reports.json'

post:
  always:
    - archiveArtifacts:
        artifacts: 'test-output/Html/ExtentHtml.html'
