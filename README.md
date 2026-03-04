## 원형석 포트폴리오 페이지 입니다.


### ai사용해서 c++게임서버 개발
[Game Sver Test]
<img width="2262" height="905" alt="image" src="https://github.com/user-attachments/assets/a451b83a-0e0c-470e-86b3-39cf735cd8c4" />

1. Game Server (GS-A / GS-B)
Boost.Asio 기반 TCP 서버로, 실제 클라이언트가 접속하는 메인 서버.

세션 관리 — 클라이언트 접속/해제, 패킷 수신·파싱·디스패치
로그인 처리 — 일반 로그인 + 채널 이동 후 토큰 기반 재로그인 (S_LOGIN)
게임 룸 — 플레이어 입장/퇴장, 룸 내 브로드캐스트
채널 이동 — 클라이언트 요청 시 ChannelServer에 이동 요청 → 토큰 발급받아 클라이언트에 전달


2. Channel Server
GS들 사이의 중재자 허브 역할. 클라이언트는 직접 접속하지 않음.

GS 등록 관리 — GS가 시작할 때 자신을 등록, 접속 중인 GS 목록 유지
서버 목록 브로드캐스트 — 새 GS가 등록되면 기존 GS 전체에 최신 목록 푸시 (BroadcastServerList)
채널 이동 중재 — 클라이언트 이동 요청 수신 → 대상 GS 선택 → 이동 토큰 발급 → 원본 GS에 전달

3.DB -SQLite

4.MEMORY DB - REDIS
채널 이동 토큰 — GS-A가 발급 → Redis에 저장 (TTL 30초) → GS-B가 검증 후 삭제

(Server-C++ , ChannelServer C++, DummyClient- C++)

### 1인 c# 게임개발 GameVideos
[Casual Game Video](https://youtu.be/LajW9NKrUU0).
(Server-C# , Client-Unity3d)

### IOCP -> BOOST::ASIO로 변환 라이브러리 수정작업
[C++ Iocp -> BoostAsio](https://github.com/WonHyeongSeok/boostAsioServer).


