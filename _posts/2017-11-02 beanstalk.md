Docker build

Docker exec



디렉토리가 없으면 순차적으로 생성해줌 (-p)

```
 mkdir -p
```



ps -ax | grep nginx



```
# supervisor
RUN         cp /srv/app/.config/supervisor/* \
                /etc/supervisor/conf.d
CMD         supervisord -n
```

supervisor 생성

자동으로 nginx와 uwsgi실행시킴



nginx.conf 에서 

```
user root;
worker_processes auto;
pid /run/nginx.pid;
daemon off; (자동으로 실행되는 것을 멈춤)
```





## Elastic Beanstalk

eb app 생성

```
eb init —-profile eb-user
```

eb 환경 생성

```
eb create --profile eb-user
```



dockerhub 에 repository 생성

docker repository 와 이미지파일이 같아야 push가능

docker tag base yabi1007/base

docker push yabi1007/base

  

eb deploy (최신 환경에 따라 배포)



> Output: No EXPOSE directive found in Dockerfile, abort deployment. 

Server (80port request)

 -  Nginx 에서 docker로 연결해줌

    ​	-docker	

    ​		c1 	- nginx를 80port로 다시 연결시켜주어야함

    ​			(내부에서 컨테이너가 몇번 포트를 열어줄지 지정해야함EXPOSE 80)



ep open - url 연결되기

[Errno 2] No such file or directory: '/srv/app/.config_secret/settings_common.json'

git에 올라가지 않은 파일 때문에 error가 생김



.ebignore 생성

```
!.config_secret
```

gitignore 에서 ! .config_secret을 무시함