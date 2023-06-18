# docker-ml-faq-rassa
ML FAQ model demo with rasa &amp; Docker 

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
