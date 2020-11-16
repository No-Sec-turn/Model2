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

<pre>path 경로 설정 이유 : 실행파일들을 어느 위치에서나 실행이 가능하게 하기 위해 
실행파일들이 있는 경로를 환경 변수에서 path경로로 설정 </pre>


<pre>
GET 방식 : 파라미터를 URL 뒤에 붙여서 전송
POST 방식 : 파라미터를 본문(body)안에 담아서 전송 -> 보안이 우수
</pre>


<pre>
서블릿에서 특정페이지로 포워딩(페이지넘어가는것) 하는 두 가지 방법


<b>2020.11.06 수업내용 정리</b><br>

1. Dispatcher 방식
  1) 주소 표시줄 URL이 변경되지 않음
  2) 같은 request영역을 공유 => request 객체가 사라지지않고 유지됨 => 페이지가 넘어가도 아이디 등의 값들이 살아있음
2. Redirect 방식
  1) 포워딩 될때 URL이 바뀌면서 포워딩 됨 => 기존 모델1방식 포워딩 
  2) 객체가 유지 되지 않음   



</pre>
<b>2020.11.10 핵심 </b>

<pre>

</pre>
![MVC 패턴 흐름](https://user-images.githubusercontent.com/70615344/98668314-0d958700-2393-11eb-9e39-755b0d8182c8.png) <br><br>


<pre>
  ※ MVC 패턴 - 게시판 동작 흐름
   1. 웹 브라우저 요청 URL - /BoardWriteForm.bo 발생
   2. *.bo 서블릿 주소가 요청되면 BoardFrontController 실행
      => @WebServlet("*.bo") Annotation에 의해 Servlet 주소 식별
   3. BoardFrontController 에서 Servlet 주소 매핑을 통해 Board 폴더 내의 qna_board_write.jsp 페이지로 포워딩
      => Dispatcher 방식 포워딩을 통해 URL 주소 변경없이 view 페이지(.jsp)로 이동 
          (즉, 주소창에 BoardWriteForm.bo 서블릿 주소가 그대로 유지)
   4. qna_board_write.jsp 페이지에서 글쓰기 버튼 클릭시(from 태그에서 Action="BoardWritePro.bo" Post방식으로 넘김)
       => /BoardWritePro.bo 서블릿 주소 요청
   5. BoardFrontController 에서 BoardWriteProAction 클래스 인스턴스 생성 후 인스턴스 내의 execute() 메서드 호출
      => 새로운 서블릿 주소(BoardWritePro.bo)로 변경하기 위해 Redirect 방식으로 포워딩
   6. BoardWriteProAction 클래스에서 글쓰기 요청에 대한 작업을 요청하기 위해 
       BoardWriteProService 클래스의 registArticle()메서드(글등록) 호출
   7. registArticle() 메서드에서 글쓰기 작업 요청을 위해 BoardDAO 클래스의 insertArticle() 메서드 호출
   8. insertArticle() 메서드에서 글쓰기 작업 수행 후 글쓰기 결과값을 리턴
       (글 쓰기 성공시 1, 실패시 0리턴 됨)
   9. BoardDAO 로부터 리턴값을 전달 받은 BOardWriteProService 클래스에서 글쓰기 성공 여부 판별
      => 글 쓰기 성공 시 boolean 값 isWriteSuccess 를 true 로 변경하고, commit 작업 수행
   10. boolean 값을 리턴 받은 BoardWriteProACtion 클래스에서 
       1) 리턴값이 false 일 경우 자바 스크립트를 사용하여 실패 메시지 출력 후  이전 페이지로 돌아가기 수행
       2) 리턴값이 true 일 경우 ActionForward 객체를 생성하여 BoardList.bo 서블릿 주소를 Redirect 방식으로 포워딩 설정
          => ActionList.bo 서블릿 주소를 Redirect 방식으로 포워딩 설정
   11. ActionForward 객체를 리턴받은 BoardFrontController 클래스에서 ACtionForward 객체의 포워딩 방식에 따라
       Redirect 또는 Dispatcher 방식으로 포워딩 수행

</pre>
