# docker-ml-faq-rassa
ML FAQ model demo with rasa &amp; Docker 

![Untitled-2022-12-29-1222](https://github.com/harsh4870/docker-ml-faq-rassa/assets/15871000/e2d4064c-3ef9-4640-a488-60c7d48a1608)

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

