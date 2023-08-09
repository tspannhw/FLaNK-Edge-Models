# FLaNK-Edge-Models
Cloudera Edge Flow Manager, MiNiFi, Models


####  References

* https://docs.cloudera.com/cem/1.6.0/using-asset-push-command/topics/cem-updating-agent-capability-asset-push.html


#### Scenario


````

http://nifi1:10090/efm/swagger/#/Commands/createUpdateAssetOperation

curl -X 'POST' \
  'http://nifi1:10090/efm/api/commands/rpi4thermal/update-asset' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -H 'X-XSRF-TOKEN: b3b8a185-3f95-4d1a-ba25-1192b1e08b98' \
  -d '{"assetFileName": "a.jpg","assetUri":"/Users/tspann/Downloads/a.jpg","forceDownload": false}'

{
  "bulkOperation": {
    "id": "60d3d647-4240-46eb-a3d8-a09fe0d6f3a8",
    "agentClass": "rpi4thermal",
    "state": "NEW"
  }
}



````

### CEM Outputs

````
{
  "identifier": "d6065b20-e5fb-47c6-b736-c5a98b4cb58a",
  "operation": "UPDATE",
  "operand": "asset",
  "args": {
    "file": "a.jpg",
    "relativeUrl": "/c2-protocol/asset/e670241f-ed98-4f4a-9443-77913a8f4215",
    "forceDownload": "false",
    "url": "/c2-protocol/asset/e670241f-ed98-4f4a-9443-77913a8f4215"
  },
  "targetAgentId": "e8892cfd-8580-4f5b-8324-3bb292407dfd",
  "state": "DONE",
  "details": "Successfully update asset",
  "bulkOperationId": "60d3d647-4240-46eb-a3d8-a09fe0d6f3a8",
  "createdBy": "unknown",
  "created": 1691160676723,
  "updated": 1691160690898
}



````

### Dynamically Deploy an agent

````
curl -L \
 -d agentClass=jetson1 \
 -d agentIdentifier=793ebeaa-e1ad-45ba-86a8-266958ba4ecc \
 -d agentType=java \
 -d agentVersion=1.23.04 \
 -d autoConfigureSecurity=false \
 -d baseUrl=http%3A%2F%2Fnifi1%3A10090%2Fefm%2Fapi \
 -d hbPeriod=5000 \
 -d osArch=linux \
 -d serviceName=minifi \
 -d serviceUser=minifi \
 -d trustSelfSignedCertificates=false \
 http://nifi1:10090/efm/api/agent-deployer/script | bash -

 ````
