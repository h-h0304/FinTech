# FinTech

프로젝트 기능 및 설계
1. 사용자 인증 시스템

 * 회원가입 기능

    * 사용자는 회원가입을 할 수 있다.
    * 회원가입시 아이디와 패스워드, 이름, 이메일을 입력받으며, 아이디는 unique 해야한다.
    * 모든 사용자는 회원가입시 USER 권한을 지닌다.


로그인/로그아웃 기능

사용자는 로그인을 할 수 있다. 로그인시 회원가입때 사용한 아이디와 패스워드가 일치해야한다.
로그인 성공 시 인증 토큰이 발급되며, 이후 계좌 관련 기능은 로그인한 사용자만 이용 가능하다.
사용자는 로그아웃을 할 수 있으며, 로그아웃 시 발급된 토큰은 무효화된다.



2. 계좌 관리 시스템

계좌 생성 기능

로그인한 사용자는 자신의 계좌를 생성할 수 있다.
계좌 생성 시 계좌 이름과 초기 입금액을 설정할 수 있다.
계좌 생성 시 고유한 계좌번호가 자동으로 생성된다.


계좌 목록 조회 기능

로그인한 사용자는 자신의 모든 계좌 목록을 조회할 수 있다.
계좌 목록에는 계좌번호, 계좌 이름, 현재 잔액, 계좌 생성일이 표시된다.


계좌 검색 기능

로그인한 사용자는 자신의 계좌를 계좌번호나 계좌 이름으로 검색할 수 있다.
검색 결과는 정확히 일치하는 계좌 또는 부분 일치하는 계좌 목록을 반환한다.


계좌 삭제 기능

로그인한 사용자는 자신의 계좌를 삭제할 수 있다.
단, 잔액이 0원인 계좌만 삭제할 수 있으며, 잔액이 있는 경우 먼저 출금해야 한다.



3. 입출금 및 송금 시스템

금액 입금 기능

로그인한 사용자는 자신의 계좌에 금액을 입금할 수 있다.
입금 시 입금액과 입금 메모(선택)를 입력할 수 있다.
입금 후 계좌 잔액이 자동으로 업데이트된다.


금액 출금 기능

로그인한 사용자는 자신의 계좌에서 금액을 출금할 수 있다.
출금 시 출금액과 출금 메모(선택)를 입력할 수 있다.
출금 금액은 계좌 잔액보다 클 수 없으며, 출금 후 계좌 잔액이 자동으로 업데이트된다.


송금 기능

로그인한 사용자는 다른 계좌로 금액을 송금할 수 있다.
송금 시 수취인 계좌번호, 송금액, 송금 메모(선택)를 입력할 수 있다.
송금 금액은 계좌 잔액보다 클 수 없으며, 송금 후 양쪽 계좌의 잔액이 자동으로 업데이트된다.
잘못된 계좌번호로는 송금할 수 없으며, 오류 메시지가 표시된다.



4. 거래 이력 관리 시스템

거래 이력 조회 기능

로그인한 사용자는 자신의 계좌에 대한 모든 거래 이력(입금, 출금, 송금)을 조회할 수 있다.
거래 이력은 최신순으로 정렬되며, 페이징 처리가 되어있다.


송금 이력 조회 기능

로그인한 사용자는 자신이 보내거나 받은 모든 송금 이력을 조회할 수 있다.
송금 이력에는 거래 일시, 상대방 계좌번호, 송금액, 송금 메모, 거래 상태가 표시된다.
송금 이력은 최신순으로 정렬되며, 페이징 처리가 되어있다.


거래 상세 조회 기능

로그인한 사용자는 특정 거래의 상세 정보를 조회할 수 있다.
상세 정보에는 거래 유형, 거래 금액, 거래 전후 잔액, 거래 메모, 거래 일시가 포함된다.



5. 계좌 접근 권한 관리

계좌 접근 제한 기능

모든 계좌 관련 기능은 로그인한 사용자만 접근할 수 있다.
사용자는 자신의 계좌에만 접근할 수 있으며, 다른 사용자의 계좌 정보는 조회할 수 없다.
송금 기능 사용 시 수취인의 계좌번호는 알 수 있지만, 수취인의 개인정보나 잔액은 확인할 수 없다.


로그인 세션 관리

일정 시간 동안 활동이 없을 경우 자동 로그아웃 처리된다.
로그아웃 시 계좌 관련 기능에 더 이상 접근할 수 없다.
동시에 여러 기기에서 접속할 경우, 새로운 로그인은 기존 세션을 만료시킨다.


