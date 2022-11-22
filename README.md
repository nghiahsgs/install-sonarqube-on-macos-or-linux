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

user and password in fisrt time login
```
admin
admin
```


## Create new project locally
save the command line, the sample command
```
sonar-scanner \
  -Dsonar.projectKey=test \
  -Dsonar.sources=. \
  -Dsonar.host.url=http://localhost:9000 \
  -Dsonar.login=sqp_f424279f7766f60470083bf039a8b31a7b995e43
```


## Install SonarScanner
```
https://docs.sonarqube.org/latest/analysis/scan/sonarscanner/
click Mac Os
```

unzip, move to Applications and export to path
```
export PATH=$PATH:/Applications/SonarScanner/bin
```

## Go to directory of a project and run cmd
```
sonar-scanner \
  -Dsonar.projectKey=test \
  -Dsonar.sources=. \
  -Dsonar.host.url=http://localhost:9000 \
  -Dsonar.login=sqp_f424279f7766f60470083bf039a8b31a7b995e43
```

## Go to browser and view code smell
