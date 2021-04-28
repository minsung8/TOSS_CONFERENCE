# 결제 시스템의 SDK와 API 디자인
  
  가맹점 편의를 위해 CRUD => GET, POST 방식만으로 처리 
  beacause, 많은 가맹점이 DELETE, PUT 미지원 및 방화벽 이슈 
  => 예측 가능한 일관성 = 고객의 편의 
  인지하기 쉬운 요청과 응답 => NESTED Object를 정보를 모듈화하는 개념으로 사용
  Recycled Object => 인지하기 쉬운 요청과 응답
  Localization => Accept-Language header 사용
  
  but 자체적인 암호화, 기타 표준을 사용한다면
  - 연동난이도 높아짐
  - 자체 취약점 가질 수 있음
  - 실수할 가능성이 높아짐
  
  FDS => 요청 데이터와 주문 정보 등의 검증
  
# 테스트 코드
  
  테스트로 스페 문서 만들기 
 
  테스트 커버리지는 얼마든지 높힐 수 있다
  테스트 커버리지가 낮으면 빌드 실패하게 하자
  테스트는 빨랴야 한다
  커버리지가 100%라도 버그는 있다
  
  
  SLF4J 초기화 => 불필요한 로깅 설정 제거
  Jackson ObjectMapper() 생성 => Jackson을 Gson으로 교체
  Handlebars 컴파일 => Handlebars 캐시 적용
  Byte Buddy 초기화 => 테스트에서 사용 중단
  코틀린 리플렉션 모듈 초기화 => 함수 호출 제거
  MockK => 필수적이지 않으면 제거
  테스트의 순처적 실행 => 테스트를 클래스 단위로 병렬 실행
  
  
