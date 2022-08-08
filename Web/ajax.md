# ajax

웹 상에서 비동기 통신에 사용하는 기술입니다.

예시를 들면,

```
				$.ajax({
					url : "ajax_change_pw_by_user.php",
					type : "post",
					dataType : "json",
					data : 
					{
						password : p1,
					},
					error:function(request,status,error){
						alert("code = "+ request.status + 
							" message = " + request.responseText + 
							" error = " + error); // 실패 시 처리
					},

				}).done(function(data) {
					if(data.ret == true){
						alert(data.msg);
						location.replace("index.php");
					}else{
						alert(data.msg);
					}
				});
 ```
 
 이 있는데, 작동방식으로는, 데이터를 객체로 넘겨주고 받은 후 동작을 수행합니다. 객체로 넘겨주고 받는 동작은,
 
 done을 통해 나와있습니다.
 
 ajax가 사용되는 이유는 바로 비동기 통신 때문입니다.
 
 ## 비동기 통신
 
 비동기 통신이란, ajax에서 사용하는 통신입니다. 이 통신은, 통신 도중에도 다른 작업을 수행할 수 있습니다. 위의 예시 코드에서는, ajax를 통해 주소와 여러 인자들을 전달하고 전달된 정보들이 데이터베이스에서 수행되는 동안에도 다른 작업이 가능합니다.
 
 이것이 비동기 통신입니다.
 
 <img width="346" alt="화면 캡처 2022-08-08 133512" src="https://user-images.githubusercontent.com/48556879/183340010-e186f787-c60f-48bd-a7d9-f2a4077e7169.png">
(비동기 통신 그림)

이런 방식으로 비동기 통신은 작동합니다.

## ajax 원형

```
$.ajax ({
  // URL은 필수 요소이므로 반드시 구현해야 하는 Property입니다.
  url	: "url", // 요청이 전송될 URL 주소
  type	: "GET", // http 요청 방식 (default: ‘GET’)
  async : true,  // 요청 시 동기화 여부. 기본은 비동기(asynchronous) 요청 (default: true)
  cache : true,  // 캐시 여부
  timeout : 3000, // 요청 제한 시간 안에 완료되지 않으면 요청을 취소하거나 error 콜백을 호출.(단위: ms)
  data  : {key : value}, // 요청 시 포함되어질 데이터
  processData : true, // 데이터를 컨텐트 타입에 맞게 변환 여부
  contentType : "application/json", // 요청 컨텐트 타입 
  dataType    : "json", // 응답 데이터 형식 (명시하지 않을 경우 자동으로 추측)
  beforeSend  : function () {
    // XHR Header를 포함해서 HTTP Request를 하기전에 호출됩니다.
  },
  success : function(data, status, xhr) {
    // 정상적으로 응답 받았을 경우에는 success 콜백이 호출되게 됩니다.
    // 이 콜백 함수의 파라미터에서는 응답 바디, 응답 코드 그리고 XHR 헤더를 확인할 수 있습니다.
  },
  error	: function(xhr, status, error) {
        // 응답을 받지 못하였다거나 정상적인 응답이지만 데이터 형식을 확인할 수 없기 때문에 
        // error 콜백이 호출될 수 있습니다.
        // 예를 들어, dataType을 지정해서 응답 받을 데이터 형식을 지정하였지만,
        // 서버에서는 다른 데이터형식으로 응답하면  error 콜백이 호출되게 됩니다.
  },
  complete : function(xhr, status) {
    // success와 error 콜백이 호출된 후에 반드시 호출됩니다.
    // try - catch - finally의 finally 구문과 동일합니다.
  }
});

```
 ajax의원형입니다. 인터넷에서 찾은 정보인데, 위의 예시 코드처럼 done을 사용하여 수행해도 괜찮습니다. done을 사용할시, 얻은 정보 혹은 객체는 data에 객체 혹은 정보로 저장됩니다.
 
