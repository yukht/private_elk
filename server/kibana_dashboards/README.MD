## Kibana v8.7.0 ##

## Export Kibana dashboard example ##
curl -X POST http://127.0.0.1:5601/api/saved_objects/_export -H 'kbn-xsrf: true' -H 'Content-Type: application/json' -k -u elastic -d ' { "objects": [ { "type": "dashboard", "id": "c1a78930-d8a1-11ed-878f-49982eaf858e" } ], "includeReferencesDeep": true }' >> ./export_kibana_log.ndjson

## Import Kibana dashboard example ##
curl -X POST http://127.0.0.1:5601/api/saved_objects/_import?createNewCopies=true -H "kbn-xsrf: true" -k -u elastic --form file=@./export_kibana_log.ndjson


