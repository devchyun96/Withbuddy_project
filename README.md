## 프로젝트 WithBuddy 
 반려인들을 위한 함께 산책할 수 있도록 매칭하는 웹 프로젝트 
![TF41](https://github.com/devchyun96/Withbuddy_project/assets/74132326/731b9b50-9a7d-40c8-b012-a7cc9998b626)

<br/>
<br/>

## 기간
 2023.11.26~2023.12.26
<br/>

## 사용한 기술
  <img alt="Static Badge" src="https://img.shields.io/badge/Java-0769AD?logoColor=white">
  <img alt="Static Badge" src="https://img.shields.io/badge/Spring%20boot-6DB33F?logo=springboot&logoColor=white">
  <img alt="Static Badge" src="https://img.shields.io/badge/Thymeleaf-005F0F?logo=thymeleaf&logoColor=white">
  <img alt="Static Badge" src="https://img.shields.io/badge/Javascript-F7DF1E?logo=javascript&logoColor=white">
  <img alt="Static Badge" src="https://img.shields.io/badge/jquery-0769AD?logo=jquery&logoColor=white"><br/>
  <img alt="Static Badge" src="https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white">
  <img alt="Static Badge" src="https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white">
  <img alt="Static Badge" src="https://img.shields.io/badge/MySQL-4479A1?logo=mysql&logoColor=white">
  <img alt="Static Badge" src="https://img.shields.io/badge/myBatis-4479A1?logo=mybatis&logoColor=white">
  <br/>
  
## 나의 part
  + 서울시의 산책 친구들을 매칭하여 1:1 채팅까지 🐶 <br/>
  + 채팅은 webscoket과 stomp를 사용하여 외부브로커에게 <br/>메시지를 전달하면 그 메시지가 구독한 채팅방에 뿌려지도록 <br/>
  + REST API를 통해 DB에 저장된 채팅을 보내서 View에 렌더링 
  + 매칭은 지도에서 구를 선택하여 나오는 리스트에서 각 프로필에 들어가 매칭하기를 선택하면 가능 <br/> 매칭 요청까지 구현 <br/>
 

## API

|METHOD|내용|url|파라미터|
|:---:|:---:|:---:|:---:|
|POST|채팅방 생성|/chatroom/room|receiverId,senderId|
|POST|채팅방 찾기|/chatroom/find|userId,loginId|
|Message|외부브로커에게 채팅 전달|/home/chat/{roomId}|roomId|
|sendTo|외부 브로커가 /topic/chat/{roomId} 로 메시지를 전달|/topic/chat/{roomId}|roomId|
|POST|채팅방의 채팅 리스트|/api/chatList|userId,loginId|
|POST|나랑 매칭한 유저리스트|/api/dmList|loginId|
|POST|버튼을 누르면 매칭하기|/api/match|senderId,receiverId|
|PUT|서로 매칭 여부 업데이트|/api/matchUpdate|senderId,receiverId|
|GET|유저가 받은 매칭|/api/alert/{userId}|userId|
|DELETE|매칭거절|/api/matchDelete|senderId,receiverId|


## 회고

 이 프로젝트를 진행하며 통신에 대한 이해도가 엄청 늘었다. <br/>
서버 사이드로 SPA를 구현해 보겠다고 채팅과 매칭 모두 모달을 사용해서 구현하느라 데이터 전달에 상당히 애를 먹었었다. <br/>
처음에는 어떻게 값을 전달해야 하는지에 대한 이해가 부족해서 값이 넘어가지 않기도 했었다. <br/>
매칭과 채팅을 위해 한 페이지 안에 나와 매칭될 사람의 id가 남아있어야만 했기때문에 통신을 하고나서 끝이 아니라 전달받은 데이터를 다른 모달로 넘기는게 과제였다.<br/>
해결 방안은 data-**을 통해서 서버에서 가져온 데이터를 새로 렌더링 하는 버튼에 넣어서 모달과 모달로 전달하는 것 이었다<br/>
이렇게 하면 모달내의 내가 원하는 버튼이나 span, p 같은 요소에 id 값을 남길 수 있다. 서버와의 통신에 필요한 값을 남길 수 있게 된것이다.<br/>
이런 방법으로 모달과 모달사이 혹은 폴리곤 요소에서 원하는 통신을 할 수 있게 된 것이다<br/>
결국에 채팅과 매칭을 구현하는데 까지 성공했다. <br/>
<br/>

 
