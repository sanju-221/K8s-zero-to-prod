Job & Cron-Job

 To run Jobs on a repeating schedule to perform regular actions such as backups, report generation, and so on.

Refer: https://kubernetes.io/docs/concepts/workloads/controllers/cron-jobs/

     : https://kubernetes.io/docs/concepts/workloads/controllers/job/

Job:-
```
apiVersion: batch/v1
kind: Job
metadata:
  name: demo-job
  namespace: nginx-ns
spec:
  completions: 1
  parallelism: 1
  template:
    spec:
      containers:
      - name: job-container
        image: busybox:latest
        command: ["sh", "-c", "date; echo hello world"]
      restartPolicy: Never
```

Cron-Job:-
```
apiVersion: batch/v1
kind: CronJob
metadata:
  name: demo-cronjob
  namespace: nginx-ns
spec:
  schedule: "* * * * *"
  jobTemplate:
    spec:
      template:
        spec:
          containers:
          - name: cron-container
            image: busybox:latest
            imagePullPolicy: IfNotPresent
            command:
            - /bin/sh
            - -c
            - date; echo Hello from the Kubernetes cluster && sleep 10
          restartPolicy: OnFailure

```
```
kubectl apply -f job.yml
```
```
kubectl get pods -n nginx-ns
```
```
kubectl get cronjob -n nginx-ns
```
```
kubectl logs <pod-name> <namespace>
```
<img width="1412" height="620" alt="cronjob" src="https://github.com/user-attachments/assets/d1bba1ca-956e-46ac-86f6-06574bc5edb3" />

