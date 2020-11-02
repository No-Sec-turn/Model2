# Model2
Model2 수업내용 정리

![WebActivation](https://user-images.githubusercontent.com/70615344/97847940-b90b5f80-1d33-11eb-927e-794780b70cc6.png)

①②  유저가 URL 주소 입력 <br>
③ URL 주소 중에서 도메인 네임(Domain name) 부분 DNS 서버 검색 <br>
④  DNS서버에서 해당 도메인 네임에 해당하는 IP 주소를 찾아 사용자가 입력한  URL 정보와함께 전달 <br>
⑤⑥ http프로토콜을 사용하여 HTTP 요청(Request)메시지 생성 <br>
   이렇게 생성된 HTTP 요청 (Request) a메시지는 TCP 프로토콜을 사용하여 인터넷을 거쳐 해당 IP 주소의 컴퓨터로 전송<br>
⑦ HTTP 요청(Request) 메시지는 HTTP 프로토콜로 웹페이지 URL정보로 변환<br>
⑧ 웹 서버는 도착한 웹페이지 URL 정보에 해당하는 데이터 검색<br>
⑨⑩ 검색된 웹페이지 데이터는 HTTP프로토콜을 사용하여 HTTP 응답(Response) 메시지 생성 이렇게 생성된 HTTP 응답(Response) 메시지는 TCP 프로토콜을 사용하여 컴퓨터로 전송됨<br>

원문:http://tcpschool.com/webbasic/works


<b>※ 유저에게 웹페이지 보여지는 과정</b><br>
1) 유저가 주소창 입력<br>
2) 웹서버가 요청에 대한 응답 <br>
3) 유저의 웹브라우저가 HTML 태그 해석해서 실행 
