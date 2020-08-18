# 개요

2020년 6월 29일자에 미항공우주국(NASA) 산하의 교본정보시스템(NODIS)의 웹 취약점을 찾게되었다.

사용자의 세션을 탈취할 수 있는 [교차스크립팅취약점](https://namu.wiki/w/XSS)으로

NASA의 보안운영센터(SOC)에 이메일로 취약점을 리포트하였고, 취약점은 2020년 7월 4일자에 패치되었다.

취약점을 기록하고자 PoC를 만든다.
<br>

# 소개

NODIS 웹의 검색 폼에 일부 HTML 태그가 인젝션이 되는 것을 발견하였다.

POST메소드로 인자를 전달해주도록 설계되었으나 GET메소드로도 인자를 전달할 수 있었다.

GET메소드로 인자를 전달할시에는 WAF가, 검색 폼에 직접 입력시에는 블랙리스트 기반의 필터링이 이루어졌다.

간단한 PoC를 통해서 POST메소드로 스크립트문을 삽입하였고, 교차스크립팅을 시킬 수 있었다.

<br>

# PoC
[https://bugpoc.com](https://bugpoc.com/organizations/view#bp-WKLThDSU)
비밀번호: soleStoat62

![](https://images.velog.io/images/arkminchan/post/a277eeb7-610d-484e-9fac-8cc7f4502973/bug1.png)
written by arkminchan 



