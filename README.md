Commands to run Jenkins from REST API.

1. Create CSRF crumb
 curl --user "admin:[Token]" '[Jenkins server host]/crumbIssuer/api/xml?xpath=concat(//crumbRequestField,":",//crumb)'

2. Run Pipeline
  curl -X POST [Jenkins server host]/job/[job name]/build --user admin:[token] --data-urlencode json='' -H "[Crumb]"
