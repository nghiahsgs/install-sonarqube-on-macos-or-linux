# install-sonarqube-on-macos
install sonarqube on macos

```
docker pull sonarqube:latest
```

```
docker container run -d --name sonarqube -p 9000:9000 sonarqube:latest
```

```
http://127.0.0.1:9000/maintenance?return_to=%2F
```
