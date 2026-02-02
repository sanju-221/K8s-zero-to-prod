Cron Job

 To run Jobs on a repeating schedule to perform regular actions such as backups, report generation, and so on.

Refer: https://kubernetes.io/docs/concepts/workloads/controllers/cron-jobs/
     : https://kubernetes.io/docs/concepts/workloads/controllers/job/

```
apiVersion: batch/v1
kind: Job
metadata:
  name: demo-job
  namespace: ngin-ns
spec:
  complesions: 1
  parallelism: 1
  template:
    spec:
      containers:
      - name: job-container
        image: busy-box:latest
        command: ["sh", "-c", "date; echo hello world"]
      restartPolicy: Never
```

```
kubectl apply -f job.yml
```
