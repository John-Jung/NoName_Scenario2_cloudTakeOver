# 클라우드 리소스 무단 점유

## 사용 언어 및 도구

- ![Python](https://img.shields.io/badge/python-3.8%2B-blue)



### 1. 클라우드 서버 침투 경로 확인
- Burp Suite로 인터셉트 후 http://ifconfig.io 입력

![](https://velog.velcdn.com/images/wearetheone/post/bd75d44d-38ed-4042-bad4-5f57414da2f6/image.png)

  
### 2. AWS Service 및 지역 확인
- IP 주소와 AWS EC2 서비스 인것을 확인
![](https://velog.velcdn.com/images/wearetheone/post/6fa7a1f1-cd97-43b7-a783-f32dc8c58946/image.png)



### 3. AWS 서버의 인증 정보 탐색 페이지 제작 get-mata-data-page
- 메타데이터 탈취 

![](https://velog.velcdn.com/images/wearetheone/post/dbf3e0f6-a825-43b9-812c-d45897ae78c6/image.png)

### 4. 인증정보 탐색

![](https://velog.velcdn.com/images/wearetheone/post/da0446f4-c44d-44f9-949c-48f6bc8778e0/image.png)

### 5. AWS 사용자 생성

![](https://velog.velcdn.com/images/wearetheone/post/ad7c58eb-bc47-467e-bd1e-79f5f45dc5de/image.png)

### 6. AWS 로그인 성공

![](https://velog.velcdn.com/images/wearetheone/post/f4ec373e-9786-4241-98eb-44d16302c3d8/image.png)

### 7. S3 접근

![](https://velog.velcdn.com/images/wearetheone/post/b7983386-226d-4e1d-b3c8-f8782d4a9b14/image.png)

### 8. 세션 토큰으로 AWS 권한 획득

![](https://velog.velcdn.com/images/wearetheone/post/360ab93d-138b-44a1-9dd4-e4311b971504/image.png)

### 9. 암호화폐 자동화 채굴 프로그램 실행

```bash
coin_attack.py
```

![](https://velog.velcdn.com/images/wearetheone/post/996a5e26-81a8-4ef6-b167-f685ca682507/image.png)

- VPC, Subnet, Internet Gateway, Route Table, Security Group, EC2 생성
- PhoenixMiner로 채굴시작





### 10. 암호화폐 채굴 프로그램 실행 확인 

- RDP 암호확인

![](https://velog.velcdn.com/images/wearetheone/post/4d15945d-c1dc-4cec-a16c-1852ff00b2d0/image.png)



- MobaXTerm으로 RDP 접속
![](https://velog.velcdn.com/images/wearetheone/post/2bf1cef7-6cfd-49c4-b7ae-81ee55d53ee6/image.png)

- EC2 암호화폐 채굴 중 확인
![](https://velog.velcdn.com/images/wearetheone/post/29669f5c-494b-48a3-b954-19cfa42f690b/image.png)

![](https://velog.velcdn.com/images/wearetheone/post/f02860e3-ba40-438b-b81f-5599e073844d/image.png)

- Session Manager(내부 접근)를 통해 백도어 키페어 생성

```bash
ssh -keygen -t rsa 2048 -f adminkey
```
![](https://velog.velcdn.com/images/wearetheone/post/c4b93986-c1e0-4bfd-b7fc-c43c883a9a9b/image.png)

- adminkey.pub (public key)생성 확인

```bash
cat adminkey.pub
```
![](https://velog.velcdn.com/images/wearetheone/post/cfed606d-b3eb-4572-af78-2df241ad7b4d/image.png)

- adminkey (private key) 생성 확인

```bash
cat adminkey
```
![](https://velog.velcdn.com/images/wearetheone/post/4258f01b-4b32-42f6-b6b1-46634cbc1d8d/image.png)

- ssh (외부 접근)을 통해 접속
- EC2 소스코드 위부로 유출가능

![](https://velog.velcdn.com/images/wearetheone/post/5c67c0ba-2617-4df9-a54e-109529c78ecc/image.png)

![](https://velog.velcdn.com/images/wearetheone/post/c8453306-8799-45cf-846b-88d36e53923f/image.png)

- 로그 확인 및 로그 삭제

```bash
cd /var/log
```

```bash
sudo rm -rf /var/log
```


![](https://velog.velcdn.com/images/wearetheone/post/7c7766dd-8d43-4dfc-80db-119c906e3ac6/image.png)



  
