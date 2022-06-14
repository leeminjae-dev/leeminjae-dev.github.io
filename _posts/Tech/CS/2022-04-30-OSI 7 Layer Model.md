---
title: "OSI 7 Layer Model"
categories: CS
toc: true
toc_label: "On this page"
toc_sticky: true
---
## OSI 7 계층이란?
OSI 7 계층은 네트워크에서 통신이 일어나느 과정을 7단계로 나누어 표현한 모델입니다. 우리가 데이터를 보내는것이 정확히 어떻게 진행되는지 알도록 할 수 있게 나눈 것이죠.

이러한 계층 모델을 표준으로 사용하고 있기 때문에, 제조사가 다른 장비끼리도 이러한 표준화된 규약하에 통신이 가능한 것입니다.

또, 이렇게 계층으로 나눠놓으면 통신이 일어나는 과정을 단계별로 파악할 수 있어 편리 합니다. 문제가 생기면 해당 문제가 어느 계층에서 일어난 것인지 판별하여 해당 계층만 고치면 되니까요.

물론 지금의 실제적인 통신들은 대부분 TCP/IP 프로토콜로 동작하고 있지만, 장비개발과 통신 자체를 어떻게 표준으 로 잡을지 사용하는 것은 OSI 7 Layer이기 때문에 중요합니다. 또, 어차피 둘은 비슷한 방식이기 때문에 OSI 7을 이해하면 TCP/IP를 이해하는 것도 어렵지 않습니다.

OSI 7 레이어는 이름에 맞게  아래와 같은 7개의 계층을 가집니다.

* Application
* Presentation
* Session
* Transport
* Network
* Data Link
* Physical

그럼 아까 현재는 대부분이 TCP/IP 모델을 사용하고 있다고 했죠? 그럼 TCP/IP은 어떤 계층을 갖고 있을까요? 아래와 같습니다.

* Application
* Transport
* Internet
* Network Access

OSI 7 모델과 비슷한데, 밑의 Network 부분과 Application 부분으로 통합되어 있는 것이 다른걸 알 수 있죠.

그림으로 살펴 보겠습니다.

![image1](/assets/images/tech/cs/2022-04-30-OSI/image1.PNG)

같은 모습인데, Presentation과 Session 레이어가 Application 레이어 하나로 통합되었고, Network Layer가 Internet Layer로 바뀌었으며, Data Link Layer와 Physical Layer가 통합되었습니다.

둘의 차이점은 **OSI 7 레이어는 개념적이고 이론적인 표준**이라면, **TCP/IP는 실무적 표준**이라는 것입니다. **OSI는 개념적인 모델로 우리가 데이터를 보낼때는 이러한 과정들을 거쳐서 통신을 하자! 라고 이론적으로 설명하기위한 모델**이고, **TCP/IP는 실제적으로 우리가 사용하는 클라이언트-서버 모델**인 것입니다.

이게 사실 무슨말인지 이해가 어렵습니다. 저도 이 내용을 공부하며 든 생각이, **아니  OSI 7 레이어가 표준이라면서 왜 TCP/IP를 대부분 쓰고 있는것이며, 그렇다면 우리가 OSI 7레이어를 공부해야할 필요가 뭐가 있는거지? 그냥 TCP/IP만을 알면 되잖아?**

그래서 이 둘이 무슨 차이가 있는지 찾아보았습니다.

## OSI 7 과 TCP/IP의 차이점
OSI 7과 TCP/IP 중에서 먼저나온 것은 TCP/IP 입니다. OSI 7을 표준으로 정하기 전에 이미 TCP/IP를 적용한 여러 통신 제품들이 나오고 있었죠. 그러다 보니 모두 TCP/IP라는 기술은 사용하지만 디테일한 부분이 달라서 회사가 다른 제품끼리는 호환이 안되는 문제들이 하나 둘 생기기 시작합니다.

이에 ISO(국제 표준화 기구)는 이를 통일하기 위해 국제 표준인 OSI 7을 발표하게 됩니다. 하지만 이미 대부분의 장비들은 TCP/IP를 기준으로 만들어졌기 때문에, 이를 갑자기 OSI 7 모델로 바꾸는 것은 너무나 복잡하고 어려운 일이기도 하고, 이미 어느정도 실제로 사용되며 신뢰성 있는 TCP/IP 모델을 하루아침에 OSI 7 모델로 바꾸는것도 너무 리스크가 컸습니다.

그래서 기업들은 그대로 TCP/IP 모델을 사용하되, 국제 표준인 OSI 7 모델을 참고하며 조금씩 TCP/IP 모델을 수정하여 표준에는 호환 될 수 있도록 수정하기 시작합니다. 이것이 현재의 TCP/IP가 되어 널리 사용되고 있는 것이죠.

따라서 실제로는 TCP/IP를 사용하고 있지만, 국제적인 표준은 OSI 7 모델이기 때문에 OSI 7 모델에 대해서도 알아야 하는 것입니다. 결국 TCP/IP도 OSI 7 모델을 참고하여 수정한 모델이니까요.

그럼 이제 왜 OSI 7 모델을 공부해야하는지 알았으니, OSI 7 모델의 계층을 하나하나 알아보도록 합시다.

영어로 되어있어서 어렵지만 내용은 단순합니다. 우리가 어떤 데이터를 우리 컴퓨터에서 다른 컴퓨터로 보내면, 위의 7계층을 위에서부터 데이터를 보내고, 다른 컴퓨터에서는 아래에서부터 위로 데이터를 받는 것이죠.

그러면 이 계층에 대해서 하나씩 위에서부터 설명 해보겠습니다..

## Application 
이 계층은 통신을 위해 실행하는 응용프로그램의 계층입니다. 우리가 메시지를 보내려면, 어떤 프로그램을 통해서 보내야겠죠? 예를 들어 보통은 카카오톡이나 라인 등의 메신저 프로글매을 사용할것입니다.

만약 카카오톡에서 우리가 "안녕"이라는 메시지를 보내면, 카카오톡 프로그램이 HTTP, FTP, DHCP, POP3등의 프로토콜을 사용해서 사용해서 네트워크에 접근을 시작할 것입니다.

이 부분에서는 사용자를 위한 인터페이스를 지원합니다. 카카오톡을 키면 우리가 사용할 수 있도록 예쁘게 대화창과 보내기 버튼이 있죠? 이처럼 이 부분에서는 사용자가 눈으로 볼 수 있는 부분으로, 직접 우리가 원하는 작업을 수행하기 위한 부분입니다.

이 상태에서의 메시지는 이러한 모양일 것입니다.

![image1](/assets/images/tech/cs/2022-04-30-OSI/image2.PNG)


## Presentation
이 계층에서는 데이터의 변환, 압축, 암호화가 이루어집니다. 기기 간에 다른 표현 방식을 모두가 이해할 수 있는 하나의 통일된 방식으로 변경하는것이죠. 

응용프로그램에서 보낸 메시지를 네트워크를 위해 변환하거나, 반대로 네트워크에서 받아 어플리케이션이 이해할 수 있도록 우리가 자주 사용하는 JPEG, TIFF, GIF등등으로 형식을 맞춰주는 것입니다.

그렇다면 이 부분에서는 메시지가 이렇게 송신에 유리하도록 변환될 것입니다.

또, 데이터 유형과 전송길이등 작업 정보가 담긴 헤더가 메시지에 추가됩니다.

![image1](/assets/images/tech/cs/2022-04-30-OSI/image3.PNG)

## Session
세션 게층은 네트워크상에서의 양쪽 연결을 관리하고 연결을 지속시켜주는 계층입니다. 

응용 프로그램 간 연결을 해주고 연결이 안정될 수 있도록 유지하고, 혹시나 데이터 교환에 에러가 발생한다면 다시 재연결 및 복구를 담당합니다. 변환한 메시지에 동기점을 삽입하여, 만약 누락된 정보가 있다면 동기점을 통해 판별하여 해당 부분부터 다시 전송할 수 있는 것이죠.

이 부분에서도 마찬가지로 작업에 대한 정보가 담긴 헤더가 추가됩니다.

![image1](/assets/images/tech/cs/2022-04-30-OSI/image4.PNG)

## Transport
여기서는 **Port 번호**를 사용하여 도착지 컴퓨터의 어떤 포트로 해당 데이터를 보내야 할지 포트정보를 추가합니다. 

컴퓨터가 데이터를 받으면 이 데이터를 어떤 프로세스 (프로그램)에 전달해야할지 모르는 상태입니다. 데이터가 들어왔지만, 이걸 컴퓨터 안에있는 어느 어플리케이션에 보낼지 모르는 상태입니다. 따라서 프로세스들마다 하나씩 고유의 포트번호를 겹치지 않도록 컴퓨터는 갖고있죠.

보통 우리가 웹페이지에 접속한다고 하면, 웹페이지의 웰노운 포트인 80포트로 접속하게 됩니다. 그래서 만약 웹으로 우리의 데이터를 보내는거라면, 80이라는 번호가 여기서 포함되는 것이죠. 서버 컴퓨터의 80 번호로 온 데이터는, 해당 웹페이지 프로세스의 데이터가 되는 것입니다.

![image1](/assets/images/tech/cs/2022-04-30-OSI/image5.PNG)

마찬가지로 헤더가 하나 붙고, 이 헤더에는 포트의 정보가 담기게 될 것 입니다.

여기서부터의 전송 단위를 "**세그먼트**"라고 합니다.

## Network
네트워크 계층에서는 컴퓨터의 주소인 IP를 데이터에 붙이게 됩니다. 출발 IP와 도착 IP가 헤더에 포함되어 전송 되는 것이죠.

이러한 IP를 기반으로 복잡한 인터넷 망에서 데이터 전송을 위한 최적의 경로를 선택합니다. 이를 찾기 위해서 보통 **라우터**가 이 계층에 자리잡습니다. 라우터는 라우팅 프로토콜을 통해 가장 빠른 경로를 찾아 안전하게 전달하는 기능을 수행합니다.

하지만 보통 우리는 해당 도착 컴퓨터의 IP를 알고있지 않습니다. 대신 **도메인**을 알고있는데요, www.naver.com과 같은 도메인을 입력하게 되면 컴퓨터는 연결된 DNS 서버에 도메인에 해당하는 IP를 찾아서 보내려는 데이터에 적용합니다. 숫자는 외우기 힘드니, 이러한 방식으로 주소를 정하게 된것이죠.

그렇게 DNS 서버에서 우리가 입력한 도메인의 해당하는 IP를 도착지 IP로, 우리의 컴퓨터 IP를 출발지 IP로 헤더에 담습니다.

![image1](/assets/images/tech/cs/2022-04-30-OSI/image6.PNG)

이렇게 네트워크 단에서 포장된 데이터를 "패킷"이라고 합니다.

## DataLink
데이터 링크에서는 장치간 신호를 전달하는 물리 계층을 이용하여 연결된 네트워크 노드간에 데이터를 전송합니다. 

여기서는 **프레이밍**을 하는데요, 프레임이라는 1111과 0000으로 이루어진 프레임으로 감쌉니다. 이렇게 감싸주게 되면 1111이 데이터의 시작, 0000이 끝인걸 나타내게됨으로, 여러개의 컴퓨터에서 한번에 데이터가 들어와도 이 데이터들이 섞이지 않고 구분될 수 있을 것입니다.

이렇게 데이터의 시작을 **트레일러** 에 담아서 데이터가 시작되는 부분을 구분합니다.

또한 헤더에는 전송되는 다음 노드의 물리적 주소(MAC) 주소를 담게 됩니다. 랜선 안에 있는 컴퓨터끼리는 IP대신 이러한 MAC 주소로 통신이 가능하기 때문에, 이러한 MAC 주소를 통해서  가장 가까운 라우터로 

![image1](/assets/images/tech/cs/2022-04-30-OSI/image7.PNG)

여기서부터의 계층 단위를 **프레임**이라고 합니다

## Physical 
이제 여기서부터는 데이터를 포장하고 오류를 확인하는 것이 아닌, 실제로 물리적으로 데이터를 전송하는 과정입니다. 앞에서 여러 정보를 담고 보내기 위해서 암호화 및 인코딩한 데이터를 아날로그 신호로 바꾸어 전선을 통해서 전송하는 것이죠.

프레임에 담긴 101010101010... 등의 디지털 신호를 아날로그 신호로 바꾸어 보내는 것입니다.

아날로그 신호로 인코딩한 정보를 전선을 통해서 보낸 뒤, 이를 받은 컴퓨터는 다시 Pysical로 받아 이를 다시 디지털 신호로 디코딩 하는 것이죠.

## 정리
따라서 위의 과정을 통해서 Application 단에서 Physical로 우리가 데이터를 보내면, 이 아날로그 신호가 전선을 타고 이동하여 다시 Physical 에서 Application 단으로 아까의 데이터 패키징을 역순으로 진행하면서 데이터를 다시 Application 단에서 확인할 수 있게 되는 것입니다.


## 마무리
이렇게 OSI 7 Layer에 대해 알아보았는데요. 실제로는 TCP/IP를 대부분 사용하기 때문에 조금 다를 수 있지만, 기본적으로 네트워크를 통한 데이터 교환은 위에서 설명한 OSI 7 Layer를 지향합니다. 실제로도 TCP/IP도 대부분의 과정을 위와 같이 진행하고 있기도 하구요. 

이렇게 계층을 나누어 놓음으로써, 만약 네트워크에 장애가 생긴다면 1번의 Physical 레이어 부터 해당하는 기기들이 제대로 작동하는지 하나씩 확인하면 어디가 문제여서 장애가 발생하고 있는지 확인하기 편할 것입니다.







