# 개요
2016년 1월 XX일자에 미항공우주국(NASA)와 유럽우주국(ESA) 산하의 태양관측위성(SOHO)의 서버의 취약점을 찾게되었다.

서버 FTP의 모든 '읽기권한'을 얻을 수 있는 인증우회 취약점으로

NASA의 보안운영센터(SOC)에 이메일로 취약점을 리포트하였고, 2주 이내로 취약점이 패치가 완료되었다.
<br>

# 소개
태양관측위성 서버는 웹 브라우져를 통해서 FTP 스키마에 접근할 수 있는 것을 발견하였다.

서버의 인증관련 디자인 오류를 발견하였고, 앞서 [c2f](https://bugpoc.com/organizations/view) 기법을 사용하여 인증우회를 시킬 수 있었고, 서버의 모든 디렉토리와 파일에 대한 읽기 권한을 얻을 수 있었다.

아울러 인증우회 후에 디렉토리와 파일에 접근을 하게되면 경고창만 켜지는데,

php로 웹 브라우져에서 표면적으로만 경고창이 보이게 하였을 것이라고 판단하였다.

소스보기를 통하여 서버내의 파일 데이터에 접근할 수 있었다.
<br>

# PoC
[https://bugpoc.com](https://bugpoc.com/poc#bp-2JTFJDIa)
비밀번호: cOYpUFfiN09
![](https://images.velog.io/images/arkminchan/post/71a51f56-f56f-40f7-bb7c-d3960a945439/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7%202020-07-31%20%EC%98%A4%ED%9B%84%2011.56.48.png)
![](https://images.velog.io/images/arkminchan/post/4cd00b43-e24e-42a4-9c46-bd4bcaf85561/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7%202020-07-31%20%EC%98%A4%ED%9B%84%2011.55.59.png)
![](https://images.velog.io/images/arkminchan/post/37ddc5d0-b7b0-4c69-a21b-1354dfa8cb77/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7%202020-07-31%20%EC%98%A4%ED%9B%84%2011.56.13.png)

written by arkminchan 

