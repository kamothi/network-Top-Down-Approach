# 4.5 미들박스

- 이 장과 이전 장들에서 데이터 경로에 위치하여 전달 이외의 기능을 수행하는 네트워크 장비(’박스’)를 배움
- 미들박스(Middlebox)는 출발지 호스트와 목적지 호스트 사이의 데이터 경로에 위치하여 IP 라우터의 정상적이고 표준적인 기능과는 별도로 특정 기능을 수행하는 네트워크 장비

“출발지 호스트와 목적지 호스트 사이의 데이터 경로에서 IP 라우터의 정상적이고 표준적인 기능과는 별도로 기능을 수행하는 모든 미들박스” → TCP 연결 스플리터, NAT, 방화벽, 침입 탐지 시스템

미들박스가 수행하는 세 가지 유형

- NAT 변환
    - NAT 박스는 사설 네트워크 주소체계를 구현하여 데이터그램 헤더 IP 주소 및 포트 번호를 다시 작성
- 보안 서비스
    - 방화벽은 헤더 필드값을 기준으로 트래픽을 차단하거나 DPI(Deep Packet Inspection) 같은 추가 처리를 위해 패킷을 리다이렉션
    - 미리 결정된 패턴을 감지하고 그에 따라 패킷을 필터링
- 성능 향상
    - 미들박스는 압축과 같은 서비스를 수행
    - 즉, 원하는 서비스를 제공할 수 있는 서버 집합 중 하나에 대한 서비스 요청의 로드 밸런싱 하는 주체

- 예전 인터넷 아키텍처는 네트워크 계층과 트랜스포트/애플리케이션 계층 사이에 명확한 분리가 있었음
- 미들 박스는 네트워크 계층과 트랜스포트계층, 애플리케이션 계층을 명확히 구분하는 이전 네트워크의 분리를 명백히 위반한다.
    - 예를 들어, 라우터와 호스트 사이에 위치한 NAT 박스는 네트워크 계층 IP 주소와 트랜스포트 계층 포트 번호를 다시 쓴다.
- 네트워크 내의 방화벽 블록은 IP 데이터그램 헤더 뿐만 아니라 애플리케이션 계층, 트랜스포트 계층 헤더까지 사용하여 데이터그램을 의심한다.
- 미들박스를 아키텍처적으로 혐오스럽다고 간주하는 사람들도 있지만, 다른 이들은 이러한 미들 박스가 '중요하고 영구적으로 존재한다'는 철학을 채택하고 있다.