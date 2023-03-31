# MongoDB Single Node Replica Set for dev environment

## Run the mongodb single node replicaset with docker-compose

```bash
docker-compose up -d
```

mongodb://username:password@localhost:27017/?authSource=admin&readPreference=primary&ssl=false&replicaSet=rs0 


# Generate keyfile

## Mac

```bash
openssl rand -base64 741 > mongoKeyFileMac
chmod 600 mongoKeyFileMac
```

## Linux

```bash
openssl rand -base64 756 > mongoKeyFileLinux
chmod 600 mongoKeyFileLinux
sudo chown 999 mongoKeyFileLinux
sudo chgrp 999 mongoKeyFileLinux
```