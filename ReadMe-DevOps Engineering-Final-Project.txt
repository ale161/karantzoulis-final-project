Καραντζούλης Αλέξανδρος
DevOps Engineering: Πρακτικές ανάπτυξης λογισμικού και λειτουργίες πληροφορικής
Τελική Εργασία

Ερωτήματα – Βήματα
Βήμα 1
Εφαρμογή: Python & Flask Demo App
Πηγή: https://github.com/benc-uk/python-demoapp
Εκκίνηση εφαρμογής (τοπικά)
• Εκτέλεση με: make run
• Εκκίνηση στην πόρτα 5000

Βήμα 2
https://github.com/ale161/karantzoulis-final-project
https://gitlab.com/devops-test8805629/karantzoulis-final-project

Βήμα 3
Log απο εκτέλεση
git clone https://github.com/ale161/karantzoulis-final-project
Cloning into 'karantzoulis-final-project'...
remote: Enumerating objects: 652, done.
remote: Counting objects: 100% (652/652), done.
remote: Compressing objects: 100% (302/302), done.
remote: Total 652 (delta 302), reused 652 (delta 302), pack-reused 0
Receiving objects: 100% (652/652), 16.46 MiB | 7.66 MiB/s, done.
Resolving deltas: 100% (302/302), done.

ale161@NubisVM:~/NubisPlace$ cd karantzoulis-final-project

ale161@NubisVM:~/NubisPlace/karantzoulis-final-project$ sudo docker build -f Dockerfile -t python-demo .
[sudo] password for ale161: 
Sorry, try again.
[sudo] password for ale161: 
[+] Building 57.4s (11/11) FINISHED                                             
 => [internal] load build definition from Dockerfile                       0.8s
 => => transferring dockerfile: 437B                                       0.0s
 => [internal] load .dockerignore                                          0.9s
 => => transferring context: 66B                                           0.0s
 => [internal] load metadata for docker.io/library/python:3.9-slim-buster  3.0s
 => [1/6] FROM docker.io/library/python:3.9-slim-buster@sha256:320a7a425  14.8s
 => => resolve docker.io/library/python:3.9-slim-buster@sha256:320a7a4250  0.6s
 => => sha256:320a7a4250aba4249f458872adecf92eea88dc6abd2d76d 988B / 988B  0.0s
 => => sha256:d5cca64dca485c37ccf06721e36a93bf4331b0404bf 1.37kB / 1.37kB  0.0s
 => => sha256:c84dbfe3b8deeb39e17d121220107f8354a9083b468 6.82kB / 6.82kB  0.0s
 => => sha256:8b91b88d557765cd8c6802668755a3f6dc4337b6c 27.14MB / 27.14MB  4.2s
 => => sha256:824416e234237961c9c5d4f41dfe5b295a3c35a671e 2.78MB / 2.78MB  1.3s
 => => sha256:8d53da26040835f622504d7762fad14d226ac414e 11.04MB / 11.04MB  3.8s
 => => sha256:84c8c79126f669beec1dcf6f34cd88094471745570c19c2 243B / 243B  1.7s
 => => sha256:2e1c130fa3ec1777a82123374b4c500623959f903c1 3.14MB / 3.14MB  2.9s
 => => extracting sha256:8b91b88d557765cd8c6802668755a3f6dc4337b6ce15a17e  2.7s
 => => extracting sha256:824416e234237961c9c5d4f41dfe5b295a3c35a671ee5288  0.4s
 => => extracting sha256:8d53da26040835f622504d7762fad14d226ac414efeb5363  1.2s
 => => extracting sha256:84c8c79126f669beec1dcf6f34cd88094471745570c19c29  0.0s
 => => extracting sha256:2e1c130fa3ec1777a82123374b4c500623959f903c1dd731  0.7s
 => [internal] load build context                                          0.6s
 => => transferring context: 216.51kB                                      0.0s
 => [2/6] WORKDIR /app                                                     1.4s
 => [3/6] COPY src/requirements.txt .                                      0.5s
 => [4/6] RUN pip install --no-cache-dir -r requirements.txt              33.7s
 => [5/6] COPY src/run.py .                                                0.5s
 => [6/6] COPY src/app ./app                                               0.5s
 => exporting to image                                                     1.6s
 => => exporting layers                                                    1.4s
 => => writing image sha256:6b8c782b1bcfe222819c9a2f0b9c52e0f8e7f91b9fc3c  0.1s
 => => naming to docker.io/library/python-demo                             0.1s

ale161@NubisVM:~/NubisPlace/karantzoulis-final-project$ sudo docker images
REPOSITORY                                    TAG                  IMAGE ID       CREATED         SIZE
python-demo                                   latest               6b8c782b1bcf   5 minutes ago   144MB

ale161@NubisVM:~/NubisPlace/karantzoulis-final-project$ sudo docker run -p 5000:5000 python-demo
[2023-07-21 18:25:32 +0000] [1] [INFO] Starting gunicorn 20.1.0
[2023-07-21 18:25:32 +0000] [1] [INFO] Listening at: http://0.0.0.0:5000 (1)
[2023-07-21 18:25:32 +0000] [1] [INFO] Using worker: sync
[2023-07-21 18:25:32 +0000] [6] [INFO] Booting worker with pid: 6


ale161@NubisVM:~/NubisPlace/karantzoulis-final-project$ sudo docker tag python-demo:latest ale161/karantzoulis-final-project:latest
[sudo] password for ale161: 
ale161@NubisVM:~/NubisPlace/karantzoulis-final-project$ sudo docker push ale161/karantzoulis-final-project:latest
The push refers to repository [docker.io/ale161/karantzoulis-final-project]
6e4b740761f8: Preparing 
848e5d9a500f: Preparing 
d93ac100f065: Preparing 
2bb5301557b3: Preparing 
39bad110c05f: Preparing 
067ea27560c1: Waiting 
7fb1037e08b3: Waiting 
14cbeede8d6e: Waiting 
ae2d55769c5e: Waiting 
e2ef8a51359d: Waiting 
denied: requested access to the resource is denied

ale161@NubisVM:~/NubisPlace/karantzoulis-final-project$ sudo docker login -u ale161
Password: 
WARNING! Your password will be stored unencrypted in /root/.docker/config.json.
Configure a credential helper to remove this warning. See
https://docs.docker.com/engine/reference/commandline/login/#credentials-store

Login Succeeded

ale161@NubisVM:~/NubisPlace/karantzoulis-final-project$ sudo docker push ale161/karantzoulis-final-project:latest
The push refers to repository [docker.io/ale161/karantzoulis-final-project]
6e4b740761f8: Pushed 
848e5d9a500f: Pushed 
d93ac100f065: Pushed 
2bb5301557b3: Pushed 
39bad110c05f: Pushed 
067ea27560c1: Mounted from library/python 
7fb1037e08b3: Mounted from library/python 
14cbeede8d6e: Mounted from library/python 
ae2d55769c5e: Mounted from library/python 
e2ef8a51359d: Mounted from library/python 
latest: digest: sha256:65c51f0b05c381959531270919ad6dd9581ae692e074a6787e9ca8d90329baa0 size: 2410


Βήμα 4
Google Cloud γτ το Digital Ocean δεν με ενεκτρινε
ip: 34.116.214.152




Βήμα 5

