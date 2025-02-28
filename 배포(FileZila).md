```java
//변경인증신청 막아놓기(로그인시)
if(userVo.getUserNo() != 39){
	    req.setAttribute("msg", "현재 신청기간이 아닙니다");
	    req.setAttribute("url", "/main/main.do");
	    return "forward:/common/msgForward.do";
}else{
	    req.setAttribute("url", "/konibp/relevance/relevanceAdd.do");
}
```

원래 신규인증 - 변경인증 로그인 경로를 다르게 했었는데,

현재 기간에는 둘 다 접속이 안되어야 정상임을 알게되었다.

따라서 각 컨트롤러에 위 로직 추가해서 test용 계정인 USERNO 39 제외 접속 불가능하도록 설정했다.

첫 배포

FILEZILA를 통해 배포를 했다. 

내가 만든 코드들이 실제 운영 서버에 반영되는 것이 신기했고, 사용자들이 이용할 생각을 하면 뭔가 이 일이 재밌고 좋다.

배포 하자마자 중복 데이터 관련 문제가 생겨서 해당 부분만 원래 상태로 돌려 놓았다. 실망이 크지만, 경험적으로 좋게 생각하려고 노력 중이다.

오늘 변경인증 신청 및 신규인증 신청 접근 권한을 막았고, 배포 이후 다시 원래 상태로 돌리면서 느낀건 뭐든지 기록하는 습관이 중요한 것 같다.
