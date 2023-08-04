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
