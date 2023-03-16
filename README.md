# install-sonarqube-on-macos-linux
## Step 1: install sonarqube on macos or linux

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


OR simply use docker compose: docker-composer.yaml
```yaml
version: '3'

services:
  sonarqube:
    image: sonarqube:latest
    ports:
      - "9000:9000"

```
```
docker compose -f docker-composer.yaml up
```

## Step2: Create new project locally
From admin web, click new project, click step by step and get the code below in admin
```
sonar-scanner \
  -Dsonar.projectKey=test \
  -Dsonar.sources=. \
  -Dsonar.host.url=http://localhost:9000 \
  -Dsonar.login=sqp_f424279f7766f60470083bf039a8b31a7b995e43
```


## Step3: Install SonarScanner
```
https://docs.sonarqube.org/latest/analysis/scan/sonarscanner/
click Mac Os
```

unzip, rename to `SonarScanner` and move to Applications and export to path
```
export PATH=$PATH:/Applications/SonarScanner/bin
```

For linux, download the zip file and export bin to path

## Go to directory of a project and run cmd
```
sonar-scanner \
  -Dsonar.projectKey=test \
  -Dsonar.sources=. \
  -Dsonar.host.url=http://localhost:9000 \
  -Dsonar.login=sqp_f424279f7766f60470083bf039a8b31a7b995e43
```

* Can use this file auto_scan.bash for easy to run
```bash
export PATH=$PATH:/Applications/SonarScanner/bin
sonar-scanner \
  -Dsonar.projectKey=test \
  -Dsonar.sources=. \
  -Dsonar.host.url=http://localhost:9000 \
  -Dsonar.login=sqp_f424279f7766f60470083bf039a8b31a7b995e43

```
## Go to browser and view code smell
