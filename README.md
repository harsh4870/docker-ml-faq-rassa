# docker-ml-faq-rassa
ML FAQ model demo with rasa &amp; Docker 

![image](https://github.com/harsh4870/docker-ml-faq-rassa/assets/15871000/0c83ad02-565d-4c3e-a172-c6e75af9101a)


#### Init Rasa

```
docker run  -p 5005:5005 -v $(pwd):/app <IMAGE>:3.5.2 init --no-prompt
```

#### Train Model 

```
docker run -v $(pwd):/app <IMAGE>:3.5.2 train --domain domain.yml --data data --out models
```

#### Run model 

```
docker run -v $(pwd):/app <IMAGE>:3.5.2 shell
```

## WebChat

```
docker run  -p 5005:5005 -v $(pwd):/app <IMAGE>:3.5.2  run -m models --enable-api --cors "*" --debug
```

#### Build the WebChat UI frontend

```
docker build -t rasa-webchat:v1 -f Dockerfile-webchat .
```

#### Run

```
docker run -p 8080:80 rasa-webchat:v1
```

Open `localhost:8080` in Browser

<img width="1439" alt="Screenshot 2023-06-19 at 12 10 51 PM" src="https://github.com/harsh4870/docker-ml-faq-rassa/assets/15871000/7184fa0c-123d-4719-ac09-b399514d4199">

