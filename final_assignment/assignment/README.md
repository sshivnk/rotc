Contributor - Shivank Sharma

```bash
k get all -n crud-app
NAME                           READY   STATUS    RESTARTS   AGE
pod/backend-57669d99c7-mzv4r   1/1     Running   0          11s
pod/db-86df7749bf-nbxrm        1/1     Running   0          43s

NAME              TYPE        CLUSTER-IP     EXTERNAL-IP   PORT(S)    AGE
service/backend   ClusterIP   10.96.39.85    <none>        443/TCP    43s
service/db        ClusterIP   10.96.154.47   <none>        5432/TCP   43s

NAME                      READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/backend   1/1     1            1           43s
deployment.apps/db        1/1     1            1           43s

NAME                                 DESIRED   CURRENT   READY   AGE
replicaset.apps/backend-57669d99c7   1         1         1       43s
replicaset.apps/db-86df7749bf        1         1         1       43s
shivank.sharma@Shivanks-MacBook-Pro rotc % k get pvc -n crud-app
NAME           STATUS   VOLUME                                     CAPACITY   ACCESS MODES   STORAGECLASS   VOLUMEATTRIBUTESCLASS   AGE
crud-app-pvc   Bound    pvc-73fce33a-61b1-401d-9325-c4f9dc90b4a3   1Gi        RWO            standard       <unset>                 52s


curl -X POST http://localhost:8000/users -d '{"name":"Shivank Sharma", "email":"sshivnk@example.com"}' -H "Content-Type: application/json"
{"id":2,"name":"Shivank Sharma","email":"sshivnk@example.com"}

% curl -X GET http://localhost:8000/users
[{"id":1,"name":"John Doe","email":"jdoe@example.com"},
{"id":2,"name":"Shivank Sharma","email":"sshivnk@example.com"}]

```
