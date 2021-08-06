To trigger workflow from Argo Workflow API

`curl -k https://195.201.32.94:30981/api/v1/workflows/argo/submit -d '{"resourceKind": "WorkflowTemplate", "resourceName": "basic-workflow", "submitOptions": [{"labels": "workflows.argoproj.io/workflow-template=basic-workflow"},{"arguments": { "parameters": [ { "name": "cloudtoken", "value": "ZZB7iOmvCzHEeSPqorxnmsoQV89K7sAP0XAvEH8FKlvH0pq9rvfiVCa3abhgLQ4M" }]}}]}'`

`curl -k https://195.201.32.94:30981/api/v1/workflows/argo/submit -d '{ "metadata": { "generateName": "basic-workflow-", "namespace": "argo", "labels": { "workflows.argoproj.io/workflow-template": "basic-workflow", "submit-from-ui": "true" } }, "spec": { "arguments": { "parameters": [ { "name": "cloudtoken", "value": "ZZB7iOmvCzHEeSPqorxnmsoQV89K7sAP0XAvEH8FKlvH0pq9rvfiVCa3abhgLQ4M" }, { "name": "mastercount", "value": "3" }, { "name": "workercount", "value": "3" }, { "name": "clustername", "value": "my-cluster" }, { "name": "storage-size", "value": "150" } ] }, "workflowTemplateRef": { "name": "basic-workflow" } } }'`

curl -k -k https://195.201.32.94:30981/api/v1/workflows/argo/submit -d ' {
"namespace": "argo",
"resourceKind": "WorkflowTemplate",
"resourceName": "basic-workflow",
"submitOptions": {
"generateName": "basic-workflow",
"labels": "workflows.argoproj.io/workflow-template=basic-workflow",
"parameters": [
{ "name": "cloudtoken", "value": "ZZB7iOmvCzHEeSPqorxnmsoQV89K7sAP0XAvEH8FKlvH0pq9rvfiVCa3abhgLQ4M" },
{ "name": "mastercount", "value": "1" },
{ "name": "workercount", "value": "1" }
{ "name": "clustername", "value": "my-cluster" },
{ "name": "storage-size", "value": "150" }
],
}
}'
