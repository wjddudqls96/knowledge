## DNS 
모든 통신은 IP를 기반으로 연결된다. 하지만 사용자에게 일일히 IP 주소를 입력하기란 UX적으로 좋지 않다
때문에 DNS 가 등장 했으며 DNS 는 IP 주소와 도메인 주소를 매핑하는 역할을 수행한다.

* 각 도메인들마다 DNS와 연결해주는 서버 역하을 하는 DNS 서버, 다른 말로 네임서버가 있다.

## 도메인(Domain) 이란?
* 원래 지정된 인터넷 접속 주소를 다른 이름으로 바꾸어 준 주소
* 예 ) htpp://192.168.1.1/ 이렇게 생긴 주소를 www.이름.com 이런 식으로 바꾸어 주는 것
* www : 호스팅 주소 
* 이름.com : 도메인



## DNS 작동 방식
<img src="https://velog.velcdn.com/images%2Fgoban%2Fpost%2F5717ceb7-79f2-41d3-86e5-7e48bfd6ac58%2FDNSLogic.png"/>

1. 디바이스는 hosts 파일을 열어본다.
    
    - hosts 파일은 로컬에서 직접 설정한 호스트와 IP주소를 맵핑하고 있다.   

2. DNS는 캐시를 확인한다.
    
    - 기존에 접속했던 사이트인 경우 캐시에 남아있을 수 있다.
    
    - **DNS는 브라우저 캐시 -> 로컬 캐시 -> 라우터 캐시 -> ISP(Internet Service Provider)캐시 순으로 확인한다.**

3. DNS는 Root DNS에 요청을 보낸다. -> www.naver.com
    
    - 모든 DNS에는 Root DNS의 주소가 포함 되어 있다.

    - 이를 통해 Root DNS에게 질의를 보내게 된다.
    
    -  Root DNS는 도메인 주소의 최상위 계층을 확인하여 TLD(Top Level DNS)의 주소를 반환 한다.
        
        - TLD는 .com을 관리하는 서버를 말한다.

4. DNS는 TLD에 요청을 보낸다.
    
    - Root DNS로 부터 반환받은 주소를 통해 요청을 보낸다.

    - TLD는 도메인에 권한이 있는 Authoritative DNS의 주소를 반환 한다.

        - 여기서 Authoritative DNS는 www.naver.com을 관리하는 DNS를 말한다.

5. DNS는 Authoritative DNS에 요청을 보낸다.

    - 도메인 이름에 대한 IP 주소를 반환 한다.

이때 요청을 보내는 DNS의 경우 재귀적으로 요청을 보내기 때문에 `DNS 리쿼서라` 지칭 하고 요청을 받는 DNS를 `네임서버`라 지칭 한다.

## TLD의 구조

<img src="https://velog.velcdn.com/images%2Fgoban%2Fpost%2F679d8a2b-1933-4850-95b9-c13765b9ff6c%2FTLD.jpg" />

