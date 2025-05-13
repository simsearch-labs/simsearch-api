# upload data

### uploading csv on our servers
```
curl -X POST \
  https://m18px3fd0m.execute-api.eu-west-1.amazonaws.com/beta/data/upload/add \
  -H 'Content-Type: application/json' \
  -H 'x-api-key: <API_key>' \
  -d '{"client_id": "<client_id>", "project_name": "<project_name>", "batch_format": "csv", "csv_batch": "<base64_string>", "batch_id": "0", "algorithm": "simtag"}'
```

### process data
```
curl -X POST \
  https://m18px3fd0m.execute-api.eu-west-1.amazonaws.com/beta/data/process/start \
  -H 'Content-Type: application/json' \
  -H 'x-api-key: <API_key>' \
  -d '{"client_id": "<client_id>", "project_name": "<project_name>", "algorithm": "simtag", "max_tag_frequency": 0.12, "generate_tag_list": true, "store_metadata": false}'
```

### check processing status
```
curl -X POST \
  https://m18px3fd0m.execute-api.eu-west-1.amazonaws.com/beta/data/process/status \
  -H 'Content-Type: application/json' \
  -H 'x-api-key: <API_key>' \
  -d '{"client_id": "<client_id>", "project_name": "<project_name>", "algorithm": "simtag"}'
```

### export all data
```
curl -X POST \
  https://m18px3fd0m.execute-api.eu-west-1.amazonaws.com/beta/data/retrieve/export \
  -H 'Content-Type: application/json' \
  -H 'x-api-key: <API_key>' \
  -d '{"client_id": "<client_id>", "project_name": "<project_name>", "algorithm": "covariate"}'
```

# tag new files

### send new file to process
```
curl -X POST \
  https://m18px3fd0m.execute-api.eu-west-1.amazonaws.com/beta/tag/covariate_tagging \
  -H 'Content-Type: application/json' \
  -H 'x-api-key: <API_key>' \
  -d '{"client_id": "<client_id>", "project_name": "<project_name>", "text": "King of the east are preparing"}'
```