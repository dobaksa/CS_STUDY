# CS 스터디 3주차 

# CHAPTER 2 네트워크 

# SECTION 2-1 네트워크 기초 
68~132
79

1. 네트워크의 기초 

네트워크 : 노드와 링크가 연결되어 있으며, 리소스를 공유하는 집합을 의미
노드 : 서버, 라우터, 스위치등 네트워크 장치
링크 : 유선 또는 무선을 의미 


2.1.1  처리량과 지연시간 

- 처리량(throughput) 
링크 내에서 성공적으로 전달된 데이터의 양 
단위: bps(bit per second), 초당 전송되는 비트수
트래픽, 대역폭, 네트워크 전송시 에러, 장치의 하드웨어의 영향 
- 대역폭(bandwidth): 주어진 시간동안 네트워크 연결을 통해 흐를 수 있는 최대 비트수 


- 지연시간(latency) 
요청이 처리되는 시간, 어떤 메세지(데이터)가 두 장치 사이를 왕복하는데 걸리는 시간 
매체타입(무선, 유선), 패킷 크기, 라우터의 패킷 처리시간에 영향 


2.1.2 네트워크 토폴로지와 병목현상 

- 네트워크 토폴로지(network topology)
노드 링크가 배치되어있는지 대한 방식이자 연결 형태 

- 트리 토폴로지(tree topology) 
계층형 토폴로지, 트리형태로 배치한 네트워크 구성 
특징: 
	노드 추가, 삭제가 쉽다
	특정 노드에 트래픽이 집중될때 하위노드에 영향이 심함 
	하나의 1차 허브에 더 많은 호스트를 연결함
	각 호스트 간의 신호의 이동거리를 증가시킴
	2차 허브로 네트워크를 분리하거나 해당 네트워크의 우선 순위를 부가함


- 버스 토폴로지(bus topology) 
중앙회선 하나에 여러개의 노드가 연결되어 공유하는 네트워크 구성 
주로 LAN에서 사용 

특징: 

[장점]
- 설치가 쉬움
- 비용이 저렴 
- 각 호스트의 고장이 네트워크 내의 다른 부분에 영향을 주지 않음
=> 한노드가 오류가 나더라도 다른 노드에게는 영향이 없다 
- 신뢰성이 우수 => 안정성
- 노드 추가, 삭제가 쉽다 

[단점]
- 스푸핑이 가능
스푸핑(Spoofing)은 다른사람의 컴퓨터 시스템에 접근할 목적으로 IP주소를 변조한 후 합법적인 사용자인 것처럼 위장하여 시스템에 접근함으로써 나중에 IP주소에 대한 추적을 피하는 해킹 기법의 일종 => 보안이 취약 
- 재구성이나 결합 분리의 어려움
- 탭에서 일어나는 신호의 반사는 신호의 질을 저하시킴
- 기저대역(Baseband) 전송 방식을 사용할 경우 거리에 민감하여 거리가 멀어지면 중계기가 필요함
- 버스 케이블에 결함이 발생하면 전체 스테이션은 모든 전송을 할 수 없음
- 호스트의 수가 증가하면 처리 능력은 급격히 감소함(CSMA/CD)
- 네트워크에 부하가 많으면 응답시간이 늦어짐
※ Baseband : 기본 신호를 그대로 전송하는 방법, 원거리 전송X
Broadband : 변조해서 전송, 원거리(장거리) 전송O

- 스타 토폴로지(star topology)=성형
중앙에 잇는 노드에 모드 연결된 네트워크 구성 
각 호스트가 허브라고 불리는 중앙 전송 제어장치와 점대점(Point-to-Point) 링크에 의해 접속되어 있는 초창기 사용 형태.

특징:
[장점]
- 노드추가 쉬움
- 패킷충돌 발생 가능성이 적다 => 각 노드, 허브의 관점에선 일대일 관계이므로 패킷 충돌 가능성이 적음 
- 에러 발견이 쉽고 유지 보수가 용이함
- 한 호스트의 고장이 전체 네트워크에 영향을 미치지 않음
- 한 링크가 제거되어도 다른 링크는 영향을 받지 않음
- 확장이 용이함

[단점]

- 중앙 전송 제어 장치가 고장이 나면 네트워크는 동작이 불가능
- 설치 시에 케이블링에 비용이 많이 듦
- 통신량이 많은 경우 전송 지연이 발생함

- 링형 토폴로지(ring topology)
각노드가 양옆의 노드와 연결되어 전체적으로 고리처럼 하나의 연속된 링 형태를 띄우며 통신을 하는 네트워크 방식 

특징: 
[장점]
- 설치와 재구성이 쉬움
- 장애가 발생한 호스트를 쉽게 찾음
- 노드 수가 늘어나도 네트워크상의 손실에는 별로 영향을 미치지 않음 
-> 노드간 일대일 연결임으로 패킷 손실 가능성이 적어서, 루트 한곳이 에러가 발생해도 반대편 루트로 전송가능 하기 때문
- Star형보다 케이블링에 드는 비용이 적음

[단점]
- 한번 네트워크 구성을 하면 네트워크 구성 변경이 어려움
- 링을 제어하기 위한 절차가 복잡하여 기본적인 지연이 존재함
- 단방향 전송이기 때문에 링에 결함이 발생하면 전체 네트워크를 사용할 수 없기 때문에 이를 해결하기 위해 이중 링(FDDI:Fiber Distributed Data Interface)을 사용함
- 새로 호스트 추가하기 위해서는 물리적으로 링을 절단하고 호스트를 추가해야 함

- 메시 토폴로지(mesh topology) 
망형 토폴로지라고도 하며, 그물망처럼 연결된 네트워크 구조 
완전 연결형(Full Mesh)과 부분 연결형(Partial Mesh)으로 나뉜다.
완전 연결형은 모든 장치들이 다른 모든 장치들과 연결되어 있는 경우 
모두가 연결되어 있기 때문에 모두 Redundancy(여분의 노드, 장애 발생 시 조치)를 제공하며 가격이 가장 비쌈 

특징: 

[장점]
메시 토폴로지는 장애에 강하고 안전하며, 
목적지까지의 여러 경로 중 가장 빠른 경로를 이용하기 때문에 가용성과 효율성이 뛰어나다
한 단말 장치에서 장애가 발생해도 여러 개의 경로가 존재하므로 네트워크를 계속 사용할 수 있고 트래픽을 분산 처리할 수 있다

[단점]
반면 가격이 비싸고 네트워크 관리가 복잡해서 힘들다
하지만 노드의 추가가 어렵고 구축 비용과 운용 비용이 고가


- 병목현상 :
전체 시스템의 성능이나 용량이 하나의 구성요소로 인해 제한을 받는 현상 
토폴로지가 중요한 이유 => 병목현상을 찾을때 유용 

병목현상으로 인해 사용자가 서비스를 이용하는데 장애가 발생하였으면, 
네트워크의 토폴로지가 어떻게 되어있나 확인하고 서버간, 게이트웨어로 이어지는 회선을 추가하여 병목현상 해결가능 


2.1.3 네트워크 분류 
LAN, MAN, WAN

- LAN(Local Area Network)
근거리 통신망
건물이나 캠퍼스같은 좁은 지역에서 운영
전송속도가 빠르고 혼잡하지 않다 

- MAN(Metropolitan Area Network)
대도시 지역 네트워크 
전송속도는 평균적 
LAN보단 혼잡 


- WAN(Wide Area Network)
광역 네트워크 국가또는 대륙같은 넓은 지역 
전송속도는 낮음 
MAN보다 혼잡 

네트워크 규모 LAN < MAN < WAN 
전송속도 LAN > MAN > WAN 


2.1.4 네트워크 성능 분석 명령어 

앱상 문제가 없는데 사용자가 서비스로부터 문제가 발생하면 네트워크 병목 현상을 의심 

네트워크의 병목 현상 의심 원인 
- 네트워크 대역폭
- 네트워크 토폴로지 
- 서버 CPU, 메모리 사용량 
- 비효율적인 네트워크 구성 


네트워크로부터 문제점이 발생하였으면 네트워크 성능 분석을 해야함, 이때 사용하는 명령어 


ping(Packet INternet Groper) 
네트워크 상태를 확인하려는 대상 노드를 향해 일정크기의 패킷을 전송하는 명령어 
노드의 패킷 수신상태, 도달시간, 해당노드까지 연결 상태 확인가능 

TCP/IP 프로토콜 중 ICMP 프로토콜로 통해 작동, ICMP를 지원하지 않는 기기를 대상으로는 실행할수 없음 

사용법
ping [ip주소 or 도메인 주소] 


- ICMP(Internet Control Message Protocol):
		IP 패킷을 처리할 때 발생하는 문제를 알려주는 프로토콜
		형식은 8bit의 헤더와 가변 길이의 데이터 영역으로 분리 
		ICMP 프로토콜을 이용해서 ping 유틸리티의 구현을 통해 오류가 발생했음을 알리는 기능을 수행 

netstat
접속되어있는 서비스들의 네트워크 상태를 표시하는데 사용 
네트워크 접속, 라우팅 테이블, 네트워크 프로토콜 리스트 보여줌 
주로 서비스의 포트가 열려있는지 확인


nslookup
DNS에 관련된 내용을 확인하기 위해 사용하는 명령어
특정 도메인에 매핑된 IP를 확인할 때 사용

- DNS(Domain Name Syetem) -> 좀 더 공부필요
웹사이트에 접속 할 때 우리는 외우기 어려운 IP 주소 대신 도메인 이름을 사용
도메인 이름을 사용했을 때 입력한 도메인을 실제 네트워크상에서 사용하는 IP 주소로 바꾸고 해당 IP 주소로 접속하는 과정이 필요하다.
이러한 과정, 전체 시스템을 DNS(도메인 네임 시스템)라고 한다.
전세계적으로 약속된 규칙을 공유한다.
상위 기관에서 인증된 기관에게 도메인을 생성하거나 IP 주소로 변경할 수 있는 ‘권한’을부여한다.
DNS는 이처럼 상위 기관과 하위 기관과 같은 ‘계층 구조’를 가지는 분산 데이터베이스 구조를 가진다.

tracert 
목적지 노드까지 네트워크 경로를 확인할 때 사용하는 명령어 
목적지 노드까지 구간들 중 어느 구간에서 응답시간이 느려지를 확인 가능 


Section 2.2 TCP/IP 4계층 모델 

인터넷 프로토콜 스위트(internet protocol suite) 
인터넷에서 컴퓨터들이 서로 정보를 주고받는데 쓰이는 프로토콜 집합 
TCP/IP 4계층 또는 OSI 7계층 모델로 설명 


2.2.1 계층구조 
TCP/IP 4계층 구조 

애플리케이션 계층(Application Layer)
전송 계층(Transport Layer)
인터넷 계층(Internet Layer)
네트워크 연결 계층(Network Access Layer) = 링크계층(Link Layer)



[https://velog.velcdn.com/images%2Fdyunge_100%2Fpost%2Fc1fdb43d-7f7e-4613-9526-a15b01fa9546%2Fimage.png]

- 애플리케이션 계층 
FTP, HTTP, SSH, SMTP, DNS등 응용 프로그램이 사용되는 프로토콜 계층 
웹서비스, 이메일등 서비스를 실질적으로 사람들에게 제공하는 계층 

- 전송 계층 

송신자와 수신자를 연결하는 통신 서비스를 제공 
연결지향 데이터 스트림 지원, 신뢰성, 흐름제어 제공
애플리케이션과 인터넷 사이의 데이터가 전달될때 중계 역할 
TCP 와 UDP

- TCP(Transmission Control Protocol)
패킷 사이 순서 보장, 연결지향 프로토콜 사용 -> 신뢰성을 구축 
가상회선 패킷 교환방식을 사용

- UDP(User Datagram Protocol)
순서 보장 X, 수신여부 확인 X, 단순히 데이터만 줌
데이터 그램 교환방식을 사용 

- 가상회선 패킷 교환방식 
각 패킷에 가상회선 식별자가 포함 -> 모든 패킷을 전송하면 가상회선 해제 -> 패킷들은 전송된 순서대로 도착 
특징: 
	연결형 서비스를 지원하기 위한 기능
	- 데이터를 패킷 단위로 나누어 전송
	- 가상 연결 설정을 통해 전송되는 모든 패킷의 경로가 동일 => 전송전 송수신 루트를 미리설정 
	- 패킷의 도착 순서가 일정 (출발/도착 순서 동일)
	- 가상 회선 방식이 회선 교환 방식과 유사하지만, 회선 교환 방식은 패킷 기능을 지원하지 않는다.


- 데이터그램 패킷 교환방식 
패킷이 독립적으로 이동하며 최적의 경로를 선택 
특징: 
	- 비연결형 서비스
	- 패킷을 독립적으로 전송(서로 다른 경로, 경로를 미리 할당하지 않음) => 전송때마다 최적의 루트를 설정 -> 경로가 패킷마다 달라질수 있음 
	- 정보의 양이 적거나 상대적으로 신뢰성이 중요하지 않은 환경에서 사용
	- 송신 호스트가 전송한 패킷은 보낸 순서와 무관한 순서로 수신(서로 다른 경로, 네트워크 혼잡도에 따라 가변적)




+ OSI 7계층(따로) 
+ DNS 공부 
+ TCP, UDP 구조랑 연결 방식, 특징 
+ 애플리케이션 프로토콜(FTP, HTTP, SSH, SMTP, DNS) 공부 
+ 회선교환, 패킷교환의 정의와 차이점 
+ 패킷교환 -> 가상회선, 데이터그램의 정의 차이점 






# 출처 
2.1.2 네트워크 토폴로지 종류
https://m.blog.naver.com/hilineisp/10169694570

- 스푸핑
https://zeromin-code.tistory.com/48

- 메시 토폴로지
https://devowen.com/332

- LAN, MAN, WAN
https://fnvlfnfl123.tistory.com/3


- 네트워크 성능 명령어 
https://m.blog.naver.com/toruin84/222826794674

- DNS 
https://hanamon.kr/dns%EB%9E%80-%EB%8F%84%EB%A9%94%EC%9D%B8-%EB%84%A4%EC%9E%84-%EC%8B%9C%EC%8A%A4%ED%85%9C-%EA%B0%9C%EB%85%90%EB%B6%80%ED%84%B0-%EC%9E%91%EB%8F%99-%EB%B0%A9%EC%8B%9D%EA%B9%8C%EC%A7%80/

- TCP/IP 4계층 
https://velog.io/@dyunge_100/Network-TCPIP-4%EA%B3%84%EC%B8%B5%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC

- 가상회선 방식, 패킷교환 방식 
https://prinha.tistory.com/entry/Network-%ED%8C%A8%ED%82%B7%EA%B5%90%ED%99%98%EB%B0%A9%EC%8B%9D-%EA%B0%80%EC%83%81%ED%9A%8C%EC%84%A0%EB%B0%A9%EC%8B%9D%EB%8D%B0%EC%9D%B4%ED%84%B0%EA%B7%B8%EB%9E%A8%EB%B0%A9%EC%8B%9D