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
Digital Ocean
ip: 134.209.241.242
App: http://134.209.241.242:5000/


Βήμα 5

Το test και το build δουλεύουν κανονικά
Το deploy με ταλαιπώρησε (δεν μπορούσα να εγγραφώ στο digitalocean αρχικά και ξεκίνησα με google cloud και μετά δεν δεχόταν το ssh).
Μετά από μεγάλη ταλαιπωρία και μετά από την τελευταία παράταση που μας δώσατε κατάφερα να ολοκληρώσω την εργασία και να πετύχω και το deploy.
Για να καταφέρω την επικοινωνία ακολούθησα τις παρακάτω οδηγίες
https://docs.gitlab.com/ee/ci/ssh_keys/

Αναλυτικό Log από το deploy

$ which ssh-agent || ( apt-get update -y && apt-get install openssh-client git -y )
/usr/bin/ssh-agent
$ eval $(ssh-agent -s)
Agent pid 13
$ echo "$SSH_KEY" | tr -d '\r' | ssh-add -
Identity added: (stdin) (ale.black161+nopass@gmail.com)
$ mkdir -p ~/.ssh
$ chmod 700 ~/.ssh
$ ssh-keyscan 134.209.241.242 >> ~/.ssh/known_hosts
# 134.209.241.242:22 SSH-2.0-OpenSSH_8.9p1 Ubuntu-3ubuntu0.3
# 134.209.241.242:22 SSH-2.0-OpenSSH_8.9p1 Ubuntu-3ubuntu0.3
# 134.209.241.242:22 SSH-2.0-OpenSSH_8.9p1 Ubuntu-3ubuntu0.3
# 134.209.241.242:22 SSH-2.0-OpenSSH_8.9p1 Ubuntu-3ubuntu0.3
# 134.209.241.242:22 SSH-2.0-OpenSSH_8.9p1 Ubuntu-3ubuntu0.3
$ chmod 644 ~/.ssh/known_hosts
$ echo "Logging in to the remote server..."
Logging in to the remote server...
$ ssh -v -o StrictHostKeyChecking=no -i ~/.ssh/id_rsa root@134.209.241.242 "docker login -u $REGISTRY_USER -p $REGISTRY_PASS"
Warning: Identity file /root/.ssh/id_rsa not accessible: No such file or directory.
OpenSSH_9.2p1 Debian-2, OpenSSL 3.0.9 30 May 2023
debug1: Reading configuration data /etc/ssh/ssh_config
debug1: /etc/ssh/ssh_config line 19: include /etc/ssh/ssh_config.d/*.conf matched no files
debug1: /etc/ssh/ssh_config line 21: Applying options for *
debug1: Connecting to 134.209.241.242 [134.209.241.242] port 22.
debug1: Connection established.
debug1: identity file /root/.ssh/id_rsa type -1
debug1: identity file /root/.ssh/id_rsa-cert type -1
debug1: identity file /root/.ssh/id_ecdsa type -1
debug1: identity file /root/.ssh/id_ecdsa-cert type -1
debug1: identity file /root/.ssh/id_ecdsa_sk type -1
debug1: identity file /root/.ssh/id_ecdsa_sk-cert type -1
debug1: identity file /root/.ssh/id_ed25519 type -1
debug1: identity file /root/.ssh/id_ed25519-cert type -1
debug1: identity file /root/.ssh/id_ed25519_sk type -1
debug1: identity file /root/.ssh/id_ed25519_sk-cert type -1
debug1: identity file /root/.ssh/id_xmss type -1
debug1: identity file /root/.ssh/id_xmss-cert type -1
debug1: identity file /root/.ssh/id_dsa type -1
debug1: identity file /root/.ssh/id_dsa-cert type -1
debug1: Local version string SSH-2.0-OpenSSH_9.2p1 Debian-2
debug1: Remote protocol version 2.0, remote software version OpenSSH_8.9p1 Ubuntu-3ubuntu0.3
debug1: compat_banner: match: OpenSSH_8.9p1 Ubuntu-3ubuntu0.3 pat OpenSSH* compat 0x04000000
debug1: Authenticating to 134.209.241.242:22 as 'root'
debug1: load_hostkeys: fopen /root/.ssh/known_hosts2: No such file or directory
debug1: load_hostkeys: fopen /etc/ssh/ssh_known_hosts: No such file or directory
debug1: load_hostkeys: fopen /etc/ssh/ssh_known_hosts2: No such file or directory
debug1: SSH2_MSG_KEXINIT sent
debug1: SSH2_MSG_KEXINIT received
debug1: kex: algorithm: sntrup761x25519-sha512@openssh.com
debug1: kex: host key algorithm: ssh-ed25519
debug1: kex: server->client cipher: chacha20-poly1305@openssh.com MAC: <implicit> compression: none
debug1: kex: client->server cipher: chacha20-poly1305@openssh.com MAC: <implicit> compression: none
debug1: expecting SSH2_MSG_KEX_ECDH_REPLY
debug1: SSH2_MSG_KEX_ECDH_REPLY received
debug1: Server host key: ssh-ed25519 SHA256:ogCmVplh6b/KT7343bbA2lWxIdYy4GjLskLPWU/6AjM
debug1: load_hostkeys: fopen /root/.ssh/known_hosts2: No such file or directory
debug1: load_hostkeys: fopen /etc/ssh/ssh_known_hosts: No such file or directory
debug1: load_hostkeys: fopen /etc/ssh/ssh_known_hosts2: No such file or directory
debug1: Host '134.209.241.242' is known and matches the ED25519 host key.
debug1: Found key in /root/.ssh/known_hosts:3
debug1: rekey out after 134217728 blocks
debug1: SSH2_MSG_NEWKEYS sent
debug1: expecting SSH2_MSG_NEWKEYS
debug1: SSH2_MSG_NEWKEYS received
debug1: rekey in after 134217728 blocks
debug1: get_agent_identities: bound agent to hostkey
debug1: get_agent_identities: agent returned 1 keys
debug1: Will attempt key: ale.black161+nopass@gmail.com ED25519 SHA256:DCqfPbSLiL6NJ8qzoeTToiqkoRJ/J1fAt5CnOMB30cQ agent
debug1: Will attempt key: /root/.ssh/id_rsa 
debug1: Will attempt key: /root/.ssh/id_ecdsa 
debug1: Will attempt key: /root/.ssh/id_ecdsa_sk 
debug1: Will attempt key: /root/.ssh/id_ed25519 
debug1: Will attempt key: /root/.ssh/id_ed25519_sk 
debug1: Will attempt key: /root/.ssh/id_xmss 
debug1: Will attempt key: /root/.ssh/id_dsa 
debug1: SSH2_MSG_EXT_INFO received
debug1: kex_input_ext_info: server-sig-algs=<ssh-ed25519,sk-ssh-ed25519@openssh.com,ssh-rsa,rsa-sha2-256,rsa-sha2-512,ssh-dss,ecdsa-sha2-nistp256,ecdsa-sha2-nistp384,ecdsa-sha2-nistp521,sk-ecdsa-sha2-nistp256@openssh.com,webauthn-sk-ecdsa-sha2-nistp256@openssh.com>
debug1: kex_input_ext_info: publickey-hostbound@openssh.com=<0>
debug1: SSH2_MSG_SERVICE_ACCEPT received
debug1: Authentications that can continue: publickey
debug1: Next authentication method: publickey
debug1: Offering public key: ale.black161+nopass@gmail.com ED25519 SHA256:DCqfPbSLiL6NJ8qzoeTToiqkoRJ/J1fAt5CnOMB30cQ agent
debug1: Server accepts key: ale.black161+nopass@gmail.com ED25519 SHA256:DCqfPbSLiL6NJ8qzoeTToiqkoRJ/J1fAt5CnOMB30cQ agent
Authenticated to 134.209.241.242 ([134.209.241.242]:22) using "publickey".
debug1: channel 0: new session [client-session] (inactive timeout: 0)
debug1: Requesting no-more-sessions@openssh.com
debug1: Entering interactive session.
debug1: pledge: filesystem
debug1: client_input_global_request: rtype hostkeys-00@openssh.com want_reply 0
debug1: client_input_hostkeys: searching /root/.ssh/known_hosts for 134.209.241.242 / (none)
debug1: client_input_hostkeys: searching /root/.ssh/known_hosts2 for 134.209.241.242 / (none)
debug1: client_input_hostkeys: hostkeys file /root/.ssh/known_hosts2 does not exist
debug1: client_input_hostkeys: no new or deprecated keys from server
debug1: Remote: /root/.ssh/authorized_keys:4: key options: agent-forwarding port-forwarding pty user-rc x11-forwarding
debug1: Remote: /root/.ssh/authorized_keys:4: key options: agent-forwarding port-forwarding pty user-rc x11-forwarding
debug1: Sending environment.
debug1: channel 0: setting env LANG = "C.UTF-8"
debug1: Sending command: docker login -u ale161 -p [MASKED]
debug1: pledge: fork
WARNING! Using --password via the CLI is insecure. Use --password-stdin.
WARNING! Your password will be stored unencrypted in /root/.docker/config.json.
Configure a credential helper to remove this warning. See
https://docs.docker.com/engine/reference/commandline/login/#credentials-store
Login Succeeded
debug1: client_input_channel_req: channel 0 rtype exit-status reply 0
debug1: channel 0: free: client-session, nchannels 1
Transferred: sent 3516, received 4164 bytes, in 2.0 seconds
Bytes per second: sent 1787.9, received 2117.4
debug1: Exit status 0
$ echo "Stopping and removing existing containers..."
Stopping and removing existing containers...
$ ssh -v -o StrictHostKeyChecking=no -i ~/.ssh/id_rsa root@134.209.241.242 "docker ps -aq | xargs -r docker stop | xargs -r docker rm"
Warning: Identity file /root/.ssh/id_rsa not accessible: No such file or directory.
OpenSSH_9.2p1 Debian-2, OpenSSL 3.0.9 30 May 2023
debug1: Reading configuration data /etc/ssh/ssh_config
debug1: /etc/ssh/ssh_config line 19: include /etc/ssh/ssh_config.d/*.conf matched no files
debug1: /etc/ssh/ssh_config line 21: Applying options for *
debug1: Connecting to 134.209.241.242 [134.209.241.242] port 22.
debug1: Connection established.
debug1: identity file /root/.ssh/id_rsa type -1
debug1: identity file /root/.ssh/id_rsa-cert type -1
debug1: identity file /root/.ssh/id_ecdsa type -1
debug1: identity file /root/.ssh/id_ecdsa-cert type -1
debug1: identity file /root/.ssh/id_ecdsa_sk type -1
debug1: identity file /root/.ssh/id_ecdsa_sk-cert type -1
debug1: identity file /root/.ssh/id_ed25519 type -1
debug1: identity file /root/.ssh/id_ed25519-cert type -1
debug1: identity file /root/.ssh/id_ed25519_sk type -1
debug1: identity file /root/.ssh/id_ed25519_sk-cert type -1
debug1: identity file /root/.ssh/id_xmss type -1
debug1: identity file /root/.ssh/id_xmss-cert type -1
debug1: identity file /root/.ssh/id_dsa type -1
debug1: identity file /root/.ssh/id_dsa-cert type -1
debug1: Local version string SSH-2.0-OpenSSH_9.2p1 Debian-2
debug1: Remote protocol version 2.0, remote software version OpenSSH_8.9p1 Ubuntu-3ubuntu0.3
debug1: compat_banner: match: OpenSSH_8.9p1 Ubuntu-3ubuntu0.3 pat OpenSSH* compat 0x04000000
debug1: Authenticating to 134.209.241.242:22 as 'root'
debug1: load_hostkeys: fopen /root/.ssh/known_hosts2: No such file or directory
debug1: load_hostkeys: fopen /etc/ssh/ssh_known_hosts: No such file or directory
debug1: load_hostkeys: fopen /etc/ssh/ssh_known_hosts2: No such file or directory
debug1: SSH2_MSG_KEXINIT sent
debug1: SSH2_MSG_KEXINIT received
debug1: kex: algorithm: sntrup761x25519-sha512@openssh.com
debug1: kex: host key algorithm: ssh-ed25519
debug1: kex: server->client cipher: chacha20-poly1305@openssh.com MAC: <implicit> compression: none
debug1: kex: client->server cipher: chacha20-poly1305@openssh.com MAC: <implicit> compression: none
debug1: expecting SSH2_MSG_KEX_ECDH_REPLY
debug1: SSH2_MSG_KEX_ECDH_REPLY received
debug1: Server host key: ssh-ed25519 SHA256:ogCmVplh6b/KT7343bbA2lWxIdYy4GjLskLPWU/6AjM
debug1: load_hostkeys: fopen /root/.ssh/known_hosts2: No such file or directory
debug1: load_hostkeys: fopen /etc/ssh/ssh_known_hosts: No such file or directory
debug1: load_hostkeys: fopen /etc/ssh/ssh_known_hosts2: No such file or directory
debug1: Host '134.209.241.242' is known and matches the ED25519 host key.
debug1: Found key in /root/.ssh/known_hosts:3
debug1: rekey out after 134217728 blocks
debug1: SSH2_MSG_NEWKEYS sent
debug1: expecting SSH2_MSG_NEWKEYS
debug1: SSH2_MSG_NEWKEYS received
debug1: rekey in after 134217728 blocks
debug1: get_agent_identities: bound agent to hostkey
debug1: get_agent_identities: agent returned 1 keys
debug1: Will attempt key: ale.black161+nopass@gmail.com ED25519 SHA256:DCqfPbSLiL6NJ8qzoeTToiqkoRJ/J1fAt5CnOMB30cQ agent
debug1: Will attempt key: /root/.ssh/id_rsa 
debug1: Will attempt key: /root/.ssh/id_ecdsa 
debug1: Will attempt key: /root/.ssh/id_ecdsa_sk 
debug1: Will attempt key: /root/.ssh/id_ed25519 
debug1: Will attempt key: /root/.ssh/id_ed25519_sk 
debug1: Will attempt key: /root/.ssh/id_xmss 
debug1: Will attempt key: /root/.ssh/id_dsa 
debug1: SSH2_MSG_EXT_INFO received
debug1: kex_input_ext_info: server-sig-algs=<ssh-ed25519,sk-ssh-ed25519@openssh.com,ssh-rsa,rsa-sha2-256,rsa-sha2-512,ssh-dss,ecdsa-sha2-nistp256,ecdsa-sha2-nistp384,ecdsa-sha2-nistp521,sk-ecdsa-sha2-nistp256@openssh.com,webauthn-sk-ecdsa-sha2-nistp256@openssh.com>
debug1: kex_input_ext_info: publickey-hostbound@openssh.com=<0>
debug1: SSH2_MSG_SERVICE_ACCEPT received
debug1: Authentications that can continue: publickey
debug1: Next authentication method: publickey
debug1: Offering public key: ale.black161+nopass@gmail.com ED25519 SHA256:DCqfPbSLiL6NJ8qzoeTToiqkoRJ/J1fAt5CnOMB30cQ agent
debug1: Server accepts key: ale.black161+nopass@gmail.com ED25519 SHA256:DCqfPbSLiL6NJ8qzoeTToiqkoRJ/J1fAt5CnOMB30cQ agent
Authenticated to 134.209.241.242 ([134.209.241.242]:22) using "publickey".
debug1: channel 0: new session [client-session] (inactive timeout: 0)
debug1: Requesting no-more-sessions@openssh.com
debug1: Entering interactive session.
debug1: pledge: filesystem
debug1: client_input_global_request: rtype hostkeys-00@openssh.com want_reply 0
debug1: client_input_hostkeys: searching /root/.ssh/known_hosts for 134.209.241.242 / (none)
debug1: client_input_hostkeys: searching /root/.ssh/known_hosts2 for 134.209.241.242 / (none)
debug1: client_input_hostkeys: hostkeys file /root/.ssh/known_hosts2 does not exist
debug1: client_input_hostkeys: no new or deprecated keys from server
debug1: Remote: /root/.ssh/authorized_keys:4: key options: agent-forwarding port-forwarding pty user-rc x11-forwarding
debug1: Remote: /root/.ssh/authorized_keys:4: key options: agent-forwarding port-forwarding pty user-rc x11-forwarding
debug1: Sending environment.
debug1: channel 0: setting env LANG = "C.UTF-8"
debug1: Sending command: docker ps -aq | xargs -r docker stop | xargs -r docker rm
debug1: pledge: fork
5166f87d12d3
debug1: client_input_channel_req: channel 0 rtype exit-status reply 0
debug1: client_input_channel_req: channel 0 rtype eow@openssh.com reply 0
debug1: channel 0: free: client-session, nchannels 1
Transferred: sent 3508, received 3856 bytes, in 0.4 seconds
Bytes per second: sent 8049.3, received 8847.8
debug1: Exit status 0
$ echo "Pulling and running the new Docker image..."
Pulling and running the new Docker image...
$ ssh -v -o StrictHostKeyChecking=no -i ~/.ssh/id_rsa root@134.209.241.242 "docker run -d -p 5000:5000 $IMAGE_NAME:$IMAGE_TAG"
Warning: Identity file /root/.ssh/id_rsa not accessible: No such file or directory.
OpenSSH_9.2p1 Debian-2, OpenSSL 3.0.9 30 May 2023
debug1: Reading configuration data /etc/ssh/ssh_config
debug1: /etc/ssh/ssh_config line 19: include /etc/ssh/ssh_config.d/*.conf matched no files
debug1: /etc/ssh/ssh_config line 21: Applying options for *
debug1: Connecting to 134.209.241.242 [134.209.241.242] port 22.
debug1: Connection established.
debug1: identity file /root/.ssh/id_rsa type -1
debug1: identity file /root/.ssh/id_rsa-cert type -1
debug1: identity file /root/.ssh/id_ecdsa type -1
debug1: identity file /root/.ssh/id_ecdsa-cert type -1
debug1: identity file /root/.ssh/id_ecdsa_sk type -1
debug1: identity file /root/.ssh/id_ecdsa_sk-cert type -1
debug1: identity file /root/.ssh/id_ed25519 type -1
debug1: identity file /root/.ssh/id_ed25519-cert type -1
debug1: identity file /root/.ssh/id_ed25519_sk type -1
debug1: identity file /root/.ssh/id_ed25519_sk-cert type -1
debug1: identity file /root/.ssh/id_xmss type -1
debug1: identity file /root/.ssh/id_xmss-cert type -1
debug1: identity file /root/.ssh/id_dsa type -1
debug1: identity file /root/.ssh/id_dsa-cert type -1
debug1: Local version string SSH-2.0-OpenSSH_9.2p1 Debian-2
debug1: Remote protocol version 2.0, remote software version OpenSSH_8.9p1 Ubuntu-3ubuntu0.3
debug1: compat_banner: match: OpenSSH_8.9p1 Ubuntu-3ubuntu0.3 pat OpenSSH* compat 0x04000000
debug1: Authenticating to 134.209.241.242:22 as 'root'
debug1: load_hostkeys: fopen /root/.ssh/known_hosts2: No such file or directory
debug1: load_hostkeys: fopen /etc/ssh/ssh_known_hosts: No such file or directory
debug1: load_hostkeys: fopen /etc/ssh/ssh_known_hosts2: No such file or directory
debug1: SSH2_MSG_KEXINIT sent
debug1: SSH2_MSG_KEXINIT received
debug1: kex: algorithm: sntrup761x25519-sha512@openssh.com
debug1: kex: host key algorithm: ssh-ed25519
debug1: kex: server->client cipher: chacha20-poly1305@openssh.com MAC: <implicit> compression: none
debug1: kex: client->server cipher: chacha20-poly1305@openssh.com MAC: <implicit> compression: none
debug1: expecting SSH2_MSG_KEX_ECDH_REPLY
debug1: SSH2_MSG_KEX_ECDH_REPLY received
debug1: Server host key: ssh-ed25519 SHA256:ogCmVplh6b/KT7343bbA2lWxIdYy4GjLskLPWU/6AjM
debug1: load_hostkeys: fopen /root/.ssh/known_hosts2: No such file or directory
debug1: load_hostkeys: fopen /etc/ssh/ssh_known_hosts: No such file or directory
debug1: load_hostkeys: fopen /etc/ssh/ssh_known_hosts2: No such file or directory
debug1: Host '134.209.241.242' is known and matches the ED25519 host key.
debug1: Found key in /root/.ssh/known_hosts:3
debug1: rekey out after 134217728 blocks
debug1: SSH2_MSG_NEWKEYS sent
debug1: expecting SSH2_MSG_NEWKEYS
debug1: SSH2_MSG_NEWKEYS received
debug1: rekey in after 134217728 blocks
debug1: get_agent_identities: bound agent to hostkey
debug1: get_agent_identities: agent returned 1 keys
debug1: Will attempt key: ale.black161+nopass@gmail.com ED25519 SHA256:DCqfPbSLiL6NJ8qzoeTToiqkoRJ/J1fAt5CnOMB30cQ agent
debug1: Will attempt key: /root/.ssh/id_rsa 
debug1: Will attempt key: /root/.ssh/id_ecdsa 
debug1: Will attempt key: /root/.ssh/id_ecdsa_sk 
debug1: Will attempt key: /root/.ssh/id_ed25519 
debug1: Will attempt key: /root/.ssh/id_ed25519_sk 
debug1: Will attempt key: /root/.ssh/id_xmss 
debug1: Will attempt key: /root/.ssh/id_dsa 
debug1: SSH2_MSG_EXT_INFO received
debug1: kex_input_ext_info: server-sig-algs=<ssh-ed25519,sk-ssh-ed25519@openssh.com,ssh-rsa,rsa-sha2-256,rsa-sha2-512,ssh-dss,ecdsa-sha2-nistp256,ecdsa-sha2-nistp384,ecdsa-sha2-nistp521,sk-ecdsa-sha2-nistp256@openssh.com,webauthn-sk-ecdsa-sha2-nistp256@openssh.com>
debug1: kex_input_ext_info: publickey-hostbound@openssh.com=<0>
debug1: SSH2_MSG_SERVICE_ACCEPT received
debug1: Authentications that can continue: publickey
debug1: Next authentication method: publickey
debug1: Offering public key: ale.black161+nopass@gmail.com ED25519 SHA256:DCqfPbSLiL6NJ8qzoeTToiqkoRJ/J1fAt5CnOMB30cQ agent
debug1: Server accepts key: ale.black161+nopass@gmail.com ED25519 SHA256:DCqfPbSLiL6NJ8qzoeTToiqkoRJ/J1fAt5CnOMB30cQ agent
Authenticated to 134.209.241.242 ([134.209.241.242]:22) using "publickey".
debug1: channel 0: new session [client-session] (inactive timeout: 0)
debug1: Requesting no-more-sessions@openssh.com
debug1: Entering interactive session.
debug1: pledge: filesystem
debug1: client_input_global_request: rtype hostkeys-00@openssh.com want_reply 0
debug1: client_input_hostkeys: searching /root/.ssh/known_hosts for 134.209.241.242 / (none)
debug1: client_input_hostkeys: searching /root/.ssh/known_hosts2 for 134.209.241.242 / (none)
debug1: client_input_hostkeys: hostkeys file /root/.ssh/known_hosts2 does not exist
debug1: client_input_hostkeys: no new or deprecated keys from server
debug1: Remote: /root/.ssh/authorized_keys:4: key options: agent-forwarding port-forwarding pty user-rc x11-forwarding
debug1: Remote: /root/.ssh/authorized_keys:4: key options: agent-forwarding port-forwarding pty user-rc x11-forwarding
debug1: Sending environment.
debug1: channel 0: setting env LANG = "C.UTF-8"
debug1: Sending command: docker run -d -p 5000:5000 ale161/karantzoulis-final-project:python-app-1.0
debug1: pledge: fork
Unable to find image 'ale161/karantzoulis-final-project:python-app-1.0' locally
python-app-1.0: Pulling from ale161/karantzoulis-final-project
8b91b88d5577: Pulling fs layer
824416e23423: Pulling fs layer
8d53da260408: Pulling fs layer
84c8c79126f6: Pulling fs layer
2e1c130fa3ec: Pulling fs layer
93eb42c1aa55: Pulling fs layer
4ca05ee58976: Pulling fs layer
d7431213c6cc: Pulling fs layer
98047b7f8e31: Pulling fs layer
2ea297adbca2: Pulling fs layer
84c8c79126f6: Waiting
2e1c130fa3ec: Waiting
93eb42c1aa55: Waiting
4ca05ee58976: Waiting
d7431213c6cc: Waiting
98047b7f8e31: Waiting
2ea297adbca2: Waiting
824416e23423: Verifying Checksum
824416e23423: Download complete
8d53da260408: Verifying Checksum
8d53da260408: Download complete
84c8c79126f6: Verifying Checksum
84c8c79126f6: Download complete
93eb42c1aa55: Verifying Checksum
93eb42c1aa55: Download complete
2e1c130fa3ec: Verifying Checksum
2e1c130fa3ec: Download complete
4ca05ee58976: Verifying Checksum
4ca05ee58976: Download complete
8b91b88d5577: Verifying Checksum
8b91b88d5577: Download complete
2ea297adbca2: Verifying Checksum
2ea297adbca2: Download complete
98047b7f8e31: Verifying Checksum
98047b7f8e31: Download complete
d7431213c6cc: Verifying Checksum
d7431213c6cc: Download complete
8b91b88d5577: Pull complete
824416e23423: Pull complete
8d53da260408: Pull complete
84c8c79126f6: Pull complete
2e1c130fa3ec: Pull complete
93eb42c1aa55: Pull complete
4ca05ee58976: Pull complete
d7431213c6cc: Pull complete
98047b7f8e31: Pull complete
2ea297adbca2: Pull complete
Digest: sha256:390ca23bf6988af92ab100350d291c16c85e710b623bc1ed963e088916991f60
Status: Downloaded newer image for ale161/karantzoulis-final-project:python-app-1.0
c3d7cb704441f0062d518de752df45abc82d2148dae8731fc2e1a67c85af93af
debug1: client_input_channel_req: channel 0 rtype exit-status reply 0
debug1: channel 0: free: client-session, nchannels 1
Transferred: sent 3532, received 7936 bytes, in 10.6 seconds
Bytes per second: sent 331.9, received 745.8
debug1: Exit status 0
Cleaning up project directory and file based variables
00:01
Job succeeded

