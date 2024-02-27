## 프로젝트 WithBuddy 
 반려인들을 위한 함께 산책할 수 있도록 매칭하는 웹 프로젝트 
![TF41](https://github.com/devchyun96/Withbuddy_project/assets/74132326/731b9b50-9a7d-40c8-b012-a7cc9998b626)

<br/>
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
