## SLURM 기반 가상 HPC 환경 시뮬레이션 프로젝트 연습 for IBS

✅ [1단계] VirtualBox에 Ubuntu VM 3대 생성

1. VirtualBox 설치 → 🔗 다운로드
2. Ubuntu Server 22.04 ISO → 🔗 다운로드

🖥️ VM 구성 계획
VM 이름 | 역할 | RAM | CPU | 디스크 | 비고
head-node | SLURM 컨트롤러 | 2GB | 2 | 20GB | 로그인 및 스케줄러
compute-1 | SLURM 워커 | 1.5GB | 1 | 15GB | 계산 노드
compute-2 | SLURM 워커 | 1.5GB | 1 | 15GB | 계산 노드

### ⚙️ VM 생성 단계 (모든 VM 공통)

1. VirtualBox 실행 → 새로 만들기
2. 이름: 예) head-node
3. 유형: Linux
4. 버전: Ubuntu (64-bit)
5. 메모리: 위 표 참고
6. 하드디스크: 새 하드디스크 생성 > VDI > 동적 할당 > 크기 설정

### 📡 네트워크 설정 (VM 생성 후)

1. 각 VM → 설정 > 네트워크
2. 어댑터 1: NAT (인터넷용)
3. 어댑터 2: 호스트 전용 어댑터. 없다면: VirtualBox 메뉴 → 도구 > 네트워크 > 호스트 전용 네트워크 만들기

### 💿 Ubuntu Server 설치 (ISO 부팅)

1. 각 VM 시작 → ISO 파일 연결 → Ubuntu 설치

2. 설치 중 선택
언어: 한국어 or English
서버 이름: head-node, compute-1, compute-2
사용자: user, 비밀번호: yourpassword (기억 쉽게)
OpenSSH 설치 체크























