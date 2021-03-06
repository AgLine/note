# AJAX

![캡처](https://user-images.githubusercontent.com/45511964/138813567-e609efc9-fda2-4141-970c-1cc3479fd731.PNG)
<pre>
<code>

var parameters = $("#frm").serialize(); // form 태그 안에 있는것들을 key1=value1&key2=value2&key3=value3.... 의 형태로 만들어줌

$.ajax ({
  // URL은 필수 요소이므로 반드시 구현해야 하는 Property
  url : "url", // 요청이 전송될 URL 주소
  type : "GET",”POST” // http 요청 방식 (default: ‘GET’)
  async : true, false // 요청 시 동기화 여부. 기본은 비동기(asynchronous) 요청 (default: true)
  cache : true, fasle  // 캐시 여부
  timeout : 3000, // 요청 제한 시간 안에 완료되지 않으면 요청을 취소하거나 error 콜백을 호출.(단위: ms)
  data : {key : value}, parameters// 요청 시 포함되어질 데이터
  processData : true, // 데이터를 컨텐트 타입에 맞게 변환 여부
  contentType : "application/json", // 요청 컨텐트 타입 
  dataType    : "json", // 응답 데이터 형식 (명시하지 않을 경우 자동으로 추측)
  beforeSend  : function () {
    // XHR Header를 포함해서 HTTP Request를 하기전에 호출됨
  },
  success : function(data, status, xhr) {
    // 정상적으로 응답 받았을 경우에는 success 콜백이 호출되게 됨
    // 이 콜백 함수의 파라미터에서는 응답 바디, 응답 코드 그리고 XHR 헤더를 확인할 수 있음
  },
  error : function(xhr, status, error) {
        // 응답을 받지 못하였다거나 정상적인 응답이지만 데이터 형식을 확인할 수 없기 때문에 
        // error 콜백이 호출될 수 있음
        // 예를 들어, dataType을 지정해서 응답 받을 데이터 형식을 지정하였지만,
        // 서버에서는 다른 데이터형식으로 응답하면  error 콜백이 호출
  },
  complete : function(xhr, status) {
    // success와 error 콜백이 호출된 후에 반드시 호출
    // try - catch - finally의 finally 구문과 동일
  }
});
'
<form name="frm" id="frm" onsubmit="return false;" method="get">

</form>
'
</code>
</pre>

<pre>
<code>
"true".equals((String) request.getHeader("ajax")) // ajax 호출인지 확인 하는 방법
</code>
</pre>


 #### 참고 ####
* <https://devlogofchris.tistory.com/14>
* <https://velog.io/@surim014/AJAX%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80>
