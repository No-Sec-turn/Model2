# Model2
<b>2020.11.02 수업내용 정리</b><br>
  Model2 개발을 위한 WorkBench 환경 설정 <br>
   
  1. file - switch workspace<br>
    ->새로운 워크스페이스 설정 후 launch<br>

2. general - Editor - Text Editor - Spelling<br>
   -> Enable spell checking 체크 해제<br>

3. general - Web Browser <br>
   -> chrome 설정<br>

4. general - Workspace<br>
   -> Text file encoding : UTF-8 로 설정<br>

5. Server - Server Runtime Environments<br>
  -> Add  -> Apach Tomcat 8.0 next -> Tomcat installation directory : C드라이버 Appach Tomcat 폴더 설정 -> Finish<br>

6. server 탭에서 apach tomcat 8.0 Finish<br>

7. new - Dynamic project - Test이름으로 프로젝트 만들기 - Finish<br>

8. Java Resources에서 class 파일생성 - Supperclass에 HttpServlet 설정 <br>


※ Model2 수업때 cntl F11(개발자 입장) 눌리지 않는다!!
   -> 주소로만 확인 
   
   

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
3) 유저의 웹브라우저가 HTML 태그 해석해서 실행 <br>

<pre>
POJO : Plain Old Java Object(순수 자바 객체) -> Web 관련 처리 포함  
</pre>

<b>2020.11.04</b>

<pre>path 경로 설정 이유 : 실행파일들을 어능 위치에서나 실행이 가능하게 하기 위해 실행파일들이 있는 경로를 환경 변수에서 path경로로 설정 </pre>

