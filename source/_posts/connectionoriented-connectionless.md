---
title: "Tip 1 : 연결지향(Connection Oriented) 프로토콜과 비연결(Connectionless) 프로토콜의 차이점을 이해하라!"
date: 2016-07-04 21:33:09
categories: 
	- CSE
	- NETWORK
tags:
	- tcp/ip
	- network
	- connection oriented
	- connectionless
thumbnail: /images/connection_thumbnail.png
---

### Tip 1 : Understand the Difference between Connected and Connectionless Protocols
네트워크를 공부하다보면 `연결지향(Connection-Oriented)`와 `비연결(Connectionless)`라는 말을 들어보셨을 것입니다. 
이번 포스트는 Connection-Oriented과 Connectionless에 대해 포스트하겠습니다.

---
### Summary
TCP는 Connection-Oriented 프로토콜 입니다. 1:1로 연결 상태를 유지하여 통신하는 것을 말합니다. 
IP와 UDP 는 Connectionless 프로토콜 입니다. 연결 상태를 유지하는 것이 아니라 주소를 가지고 다음 라우터나 목적지로 전달만 하여 데이타그램에 대해 관여 하지 않습니다. 

---

#### Connection Oriented 와 Connectionless 비교

| Connection Oriented | Connectionless |
| :-----------------: | :------------: |
| TCP | IP, UDP |
| Segment | Datagram |
| 프로토콜에 의해 연속적으로<br>패킷의 상태 정보 유지<sup>[1](#maintain_state)</sup> | 각각의 패킷들이 독립적<sup>[2](#independence)</sup> |
| reliable | unreliable |
| 1:1 | 1:N<br>N:M | 

#### Connection Oriented Protocol의 3단계
1. 연결 (Connection Establish)
2. 데이타 전송 단계(Data Transfer)
3. 연결 종료 (Connection Colose)


#### ✩Connectionless Protocol은 Connection Oriented Protocol의 기반이다.✩
TCP/IP은 4계층의 프로토콜 스택으로 이루어져있습니다.

||
| :---------: |
| Application | 
| TCP/UDP | 
| IP | 
| Interface |
**TCP**와 **UDP**는 **IP** 프로토콜 위에 존재합니다. 즉, **IP**는 TCP/IP 스택이 만들어지는 기초가 됩니다.
**IP**는 성능 중심(Best Effort)의 unreliable, Connecionless 서비스를 제공합니다. 상위 계층에서 패킷을 받아 IP 패킷으로 캡슐화하고 이를 하드웨어 인터페이스에 전송합니다. **IP**는 한번 전송하면 그 패킷에 관여하지 않습니다.

##### TCP가 Connectionless IP위에서 어떻게 연결형 서비스를 하는지 알아 보겠습니다.                                             
TCP는 `세그먼트(Segment)`라 불리는 패킷을 unreliable한 IP 데이타그램(Datagram)을 통해서 손상시키지않고 순서대로 목적지에 도달하도록 합니다.
신뢰성을 제공하기위해 TCP는 기본 IP 서비스에서 3가지 추가했습니다. 
1. TCP 세그먼트 내의 **Cheksum**을 제공한다. 데이터가 전송 도중에 손상되지 않았음을 증명합니다. 
2. 각 바이트 마다 일정한 **Sequence Number**할당합니다. 데이터가 순서대로 도착하지 않을경우 바로 잡을 수 있습니다.
3. TCP는 모든 세그먼트가 잘 도착하였는지 알기 위해 **Acknowledgment & Retransmission** 메커니즘을 제공합니다.

UDP는 신뢰성 없는 비연결 서비스를 제공합니다. IP 프로토콜에 2가지 기능을 추가했습니다.
UDP = 기본 IP 서비스 + (**선택적 CheckSum** + **Port**)
TCP/UDP는 자신의 고유 헤더와 데이터를 보호하기 위해 체크섬 제공.
포트는 데이터를 올바른 목적지 애플리케이션에 역다중화하는 방법을 제공.

---
<div id ="maintain_state">1.패킷의 상태 정보 유지 </div> : 전화와 같다. 전화로 대화하는 동안 누구와 통화를 하는지 이미 알고 있다. 또한 전화가 열결되어 있는 동안 상대방의 전화번호를 다시 누를 필요도 없다. [⤿]()
<div id ="independence">2. 각가의 패킷들이 독립적 </div> : 편지와 같다. 편지들은 서로 간의 정보를 유지하지 않는다. 또한, 우체국은 편지가 분실되거나 지연되거나 배달 순서가 바뀌어 전달되지 않아도 보증하지 않는다.


> **Effective TCP/IP Programming**
> &#45; 44 Tips to Improve Your Network Programs<pre>					_by C. Snader_</pre>

---
#### [#CSE](https://simhyejin.github.io/categories/CSE/) [#Network](https://simhyejin.github.io/tags/network/)
다음 포스트 > []()


