---
title: TIME_WAIT State
tags:
  - tcp/ip
  - network
  - tcp close
  - TIME_WAIT
  - 4 Way Hand Shake
categories:
  - CSE
  - NETWORK
thumbnail: /images/TCP_close.png
date: 2016-07-13 16:47:10
---

_TIME&#95;WAIT_ 상태가 늘어나면 소켓이 고갈되어 커넥션 타임아웃이 발생한다는 얘기가 있다. _TIME&#95;WAIT_ 은 어떠한 경우에 발생하고 어떤 특징이 있는지 살펴보고 소켓 고갈과의 연관성을 알아본다.

---

- <div id="index">목차</div>
	- [TCP Connecion Close : 4 way hand-shake](#sec1)
	- [TIME_WAIT](#sec2)
	- [Linger 옵션](#sec3)
	
---


## <div id="sec1">TCP Close : 4 way hand-shake</div>
먼저 TCP의 Connection Close에 살펴본다.
TCP는 Connection 연결을 3 Way Hand-Shake의 방식을 사용했다면 
Connection 종료는 **4 Way Hand-Shake**의 방식으로 한다. 
![TCP 4 Way Hand Shake](/images/TCP_close.png)

---
## <div id="sec2">TIME_WAIT</div>
**Active Close**, 즉 먼저 `close()`를 요청한 곳에서 _TIME&#95;WAIT_ state가 발생하며 2MSL동안 기다렸다가 Close 한다.
>MSL(Maximum Segment Lifetime)
RFC793 specifies the MSL as 2 minutes. 
Common implementation values, however, are 30 seconds, 1 minute, or 2 minutes. 

### TIME_WAIT 이 필요한 이유

### TIME_WAIT 특징


---
## <div id="sec3">Linger 옵션</div>

``` c
struct  linger {
  int l_onoff;    /* option on/off */
  int l_linger;   /* linger time */
};
```
소켓에는 데이타가 아직 남아 있을때 종료 방식을 결정하는 링거 옵션이 있다. 아래 3가지 경우로 나뉜다.

1. `l_onoff = 1`, `l_linger = 0`
즉시 종료하고 Buffer에 남아 있는 데이타는 버린다. 비정상 종료로 `RST`를 보내고 즉시 연결을 끊는다. 
2. `l_onoff = 1`, `l_linger = non-zero` 
명시된 시간(초)동안 정상적으로 진행하며 그 이후에는 비정상 종료(RST) 처리한다. 
만일 Buffer에 전송되지 못한 메시지가 남아 있다면 명시된 시간 동안은 어플리케이션이 `close()`를 진행하지 못하고 최종적으로 `RST`를 보내기 위해 `sleep` 상태에서 대기하기 때문에 어플리케이션 지연 현상이 발생하므로 유의해야 한다. non-blocking 으로 동작하는 것도 가능은 하다.
3. `l_onoff = 0` 
정상적인 4-way handshake 종료 과정을 진행하며 소켓의 기본값이다.

`RST`는 비정상 종료시 보내는 패킷이다. 수신한 상대방은 Connection reset by peer 오류가 나게 된다.
양쪽 모두 바로 연결이 끊어지며, 양쪽 모두 _TIME&#95;WAIT_ 상태가 남지 않는다는 점에서 가장 빠르고 깔끔해 유용해보이지만 문제는 **비정상 종료**라는 점이다. 
`RST`는 부작용를 야기할 수 있다. 또한 양쪽 모두에 _TIME&#95;WAIT_ 을 남기지 않기 때문에 패킷의 오동작을 막아줄 장치가 없다.

어떠한 _TIME&#95;WAIT_ 도 남아 있지 않아야 할 특수한 목적이 아니라면, 일반적으로는 링거 옵션을 사용하지 않아야 하고 `RST` 비정상 종료 패킷을 보내는 일이 없어야 한다.

---
## 정리
잦은 연결과 종료는 _TIME&#95;WAIT_ 상태로 소켓 고갈이 일어날 수 있다. 
대부분의 문서를 찾아보면 `Linger` 옵션을 통해 _TIME&#95;WAIT_ 을 없애려고 한다. 하지만 TCP Protocol은 오랜 역사를 가지고 변해왔지만 _TIME&#95;WAIT_ 기능은 여전히 남아있다. 이는 _TIME&#95;WAIT_ 상태가 필요한 존재이기 때문이지 않을까.

