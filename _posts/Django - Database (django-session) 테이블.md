Django - Database (django-session) 테이블

django-login view 실행

실행하는순간 django-session테이블에 user의 키값을 생성

로그인이 끝난 후 키값을 httpresponse를 이용 set-cookie로 클라이언트에게 보냄

다시 로그인 요청이 오면 cookie value를 이용해

request- view로 보내서 django-sessions db에 있는지 확인

존재하면 request.user1로 view에서 쓸수있게 해줌



API에서는

client - request (Token을 보내줌, Http Header에) - DRF에 authtoken_token테이블에서 찾음

매칭후 user가 발견되면 APIVIEW에 있는 request에 유저 할당

