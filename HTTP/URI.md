# URI(uniform Resource Identifier)
리소스를 식별한다 
URI = (URL(reource locator) + URN(resource name))
urn 이름만으로 실제 리소스를 찾을수 있는 방법이 보편화 되어 있지 않음 그래서 uri 는 url 과 동일하다고 볼수 있다.

URI :Locator;, 리소스가 있는 위치를 지정
URN : Name; 리소스에 이름을 부여
위치는 변할 수 있지만, 이름은 변하지 않는다.

URL
문법

프로토콜: 어떤 방식으로 자원에 접근 할 것인가 하는 약속 규칙) https(http + secure), http

호스트명 - 도메인명 또는 IP주소를 직접 입력 가능
포트번호 - 생략가능 http 08 https 443
패스 - 리소스 경로 , 계층적 구조
쿼리 파라미터/query string - key = value 형태 ?로 시작, &로 추가 가능
fragment - html 내부 북마크 등에 사용, 서버에 전송하는 정보 아님

