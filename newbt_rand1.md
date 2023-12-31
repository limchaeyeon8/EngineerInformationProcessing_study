## 다음 Java 코드 중에서 밑줄에 들어갈 알맞는 코드를 작성하시오.
```java
class Car implements Runnable{
  int a;
  
  public void run(){
     system.out.println("Hello")
  }
}
  
public class Main{
  public static void main(String[] args){
    Thread t1 = new Thread(new ___());
    t1.start();
  }
}
```

답: Car

#### 객체 생성
___

## 아래 설명에 대하여 괄호 안에 들어갈 알맞는 용어를 작성하시오.
    (   괄호    )은/는 여러 개의 사이트에서 한번의 로그인으로 여러가지 다른 사이트들을 자동적으로 접속하여 이용하는 방법을 말한다.
    일반적으로 서로 다른 시스템 및 사이트에서 각각의 사용자 정보를 관리하게 되는데 이때 
    하나의 사용자 정보를 기반으로 여러 시스템을 하나의 "통합 인증"을 사용하게 하는 것을 말한다. 
    즉 하나의 시스템에서 인증을 할 경우 타 시스템에서는 인증 정보가 있는지 확인하고 있으면 로그인 처리를 하도록 하고, 
    없는 경우 다시 통합 인증을 할 수 있도록 만드는 것을 의미한다.

답: SSO / Single Sign On / 싱글 사인 온
___

## OSI 7 Layer에 대한 설명이다. 다음 각 설명에 해당되는 계층을 적으시오.
     (1) 물리계층을 통해 송수신되는 정보의 오류와 흐름을 관리하여 안전한 정보의 전달을 수행할 수 있도록 도와주는 역할
     (2) 데이터를 목적지까지 가장 안전하고 빠르게 전달하는 기능
     (3) 수신자에서 데이터의 압축을 풀수 있는 방식으로 된 데이터 압축

답:
(1) 데이터링크
(2) 네트워크
(3) 표현
```md
# OSI 7 작동원리
- OSI 7계층은 응용, 표현, 세션, 전송, 네트워크, 데이터링크, 물리계층으로 나뉨.
- 전송 시 7계층에서 1계층으로 각각의 층마다 인식할 수 있어야 하는 헤더를 붙임(캡슐화)
- 수신 시 1계층에서 7계층으로 헤더를 떼어냄(디캡슐화)
- 출발지에서 데이터가 전송될 때 헤더가 추가되는데 2계층에서만 오류제어를 위해 꼬리부분에 추가됌
- 물리계층에서 1, 0 의 신호가 되어 전송매체 (동축케이블, 광섬유 등)을 통해 전송

# 물리계층(Physical Layer)
- 7계층 중 최하위 계층.
- 주로 전기적, 기계적, 기능적인 특성을 이용해 데이터를 전송.
- 데이터는 0과 1의 비트열, 즉 On, Off의 전기적 신호 상태로 이루어져 해당 계층은 단지 데이터를 전달.
- 단지 데이터 전달의 역할을 할 뿐이라 알고리즘, 오류제어 기능이 없음
- 장비로는 케이블, 리피터, 허브가 있음
# 데이터링크 계층(Data-Link Layer)
- 물리적인 연결을 통하여 인접한 두 장치 간의 신뢰성 있는 정보 전송을 담당(Point-To-Point 전송)
- 안전한 정보의 전달이라는 것은 오류나 재전송하는 기능이 존재
- MAC 주소를 통해서 통신
- 데이터 링크 계층에서 데이터 단위는 프레임(Frame)
- 장비로는 브리지, 스위치가 있음
# 네트워크 계층(Network Layer)
- 중계 노드를 통하여 전송하는 경우 어떻게 중계할 것인가를 규정
- 라우팅 기능을 맡고 있는 계층으로 목적지까지 가장 안전하고 빠르게 데이터를 보내는 기능을 가지고 있음(최적의 경로를 설정가능)
- 컴퓨터에게 데이터를 전송할지 주소를 갖고 있어서 통신가능(=우리가 자주 듣는 IP 주소가 바로 네트워크 계층 헤더에 속함)
- 네트워크 계층에서 데이터 단위는 패킷(Packet)
- 장비로는 라우터, L3 스위치가 있음
# 전송 계층(Transport Layer)
- 종단 간 신뢰성 있고 정확한 데이터 전송을 담당
- 송신자와 수신자 간의 신뢰성있고 효율적인 데이터를 전송하기 위하여 오류검출 및 복구, 흐름제어와 중복검사 등을 수행
- 데이터 전송을 위해서 Port 번호를 사용함.(대표적인 프로토콜로 TCP와 UDP가 있음)
- 전송 계층에서 데이터 단위는 세그먼트(Segment)
# 세션 계층(Session Layer)
- 통신 장치 간 상호작용 및 동기화를 제공
- 연결 세션에서 데이터 교환과 에러 발생 시의 복구를 관리
# 표현 계층(Presentation Layer)
- 데이터를 어떻게 표현할지 정하는 역할을 하는 계층
- 표현 계층은 세가지의 기능을 갖고 있습니다.
- 송신자에서 온 데이터를 해석하기 위한 응용계층 데이터 부호화, 변화
- 수신자에서 데이터의 압축을 풀수 있는 방식으로 된 데이터 압축
- 데이터의 암호화와 복호화
(MIME 인코딩이나 암호화 등의 동작이 표현계층에서 이루어짐. EBCDIC로 인코딩된 파일을 ASCII 로 인코딩된 파일로 바꿔주는 것이 한가지 예임)
# 응용 계층(Application Layer)
- 사용자와 가장 밀접한 계층으로 인터페이스 역할
- 응용 프로세스 간의 정보 교환을 담당
- ex) 전자메일, 인터넷, 동영상 플레이어 등
```
____

## 다음에서 설명하는 개발방법론
    고객의 요구사항 변화에 유연하게 대응하기 위해 일정한 주기를 반복하면서 개발하며 
    고객에게 시제품을 지속적으로 제공하며 고객의 요구사항이 정확하게 반영되고 있는지 점검한다.
    폭포수 모형에 대비되는 유연한 방법론으로 비교적 소규모 개발 프로젝트에서 각광받고 있는 개발 방법론이다.

답: 애자일 (기법[방법론])
____

## 다음 테이블에서 πTTL(employee)에 대한 연산 결과 값을 작성하시오.
```
Index	 AGE	TTL
1	  55	부장
2	  35	대리
3	  42	과장
4	  45	차장
```
답:
TTL
부장
대리
과장
차장

#### 관계대수
```md
# 관계형 데이터베이스에서 원하는 정보와 그 정보를 검색하기 위해서 어떻게 유도하는가를 기술하는 절차적인 언어
# 절차적언어(절차중심): 원하는 정보를 ‘어떻게’ 유도하는가를 연산자와 연산규칙을 이용하여 기술
-분류
1) 순수관계 연산자
① SELECT (σ)
- 릴레이션에서 주어진 조건을 만족하는 튜플들을 검색하는 것
- 기호는 그리스 문자의 시그마(σ)를 이용 (행, 수평적 연산)
- 형식 : σ 조건 (R)
② PROJECT (π)
- 릴레이션에서 주어진 조건을 만족하는 속성들을 검색
- 기호는 그리스 문자의 파이(π)를 이용 (열, 수직적 연산)
- 형식 : π 속성 (R)
③ JOIN
- 두개의 릴레이션A와 B에서 공통된 속성을 연결하는 것
- A*B(NATURAL JOIN, 자연조인): 공통 속성값 제거
- A⋈B(EQUI JOIN,동등조인): 공통 속성값 중복
④ DIVISION (÷)
- 나누어지는 릴레이션인 A는 릴레이션 B의 모든 내용을 포함한 것이 
 결과 릴레이션이 된다

2) 일반집합 연산자
① 합집합(U): 릴레이션 A 또는 B에 속하는 튜플들로 구성된 릴레이션 (UNION)
② 교집합(∩): 릴레이션 A 와 B에 공통적으로 속하는 튜플들로 구성된 릴레이션 (INTERSECTION)
③ 차집합(-): : 릴레이션 A에만 있고 B에는 없는 튜플들로 구성된 릴레이션 (DIFFERENCE)
④ 카티션 프로덕트(cartesian product) (X): A에 속한 각 튜플 a에 대하여 B에 속한 튜플 b
```
___

##
