# 폴아웃 1in2 (Fallout et tu) 한국어 패치

> [!IMPORTANT]
> **한국어 번역 리소스 전용 저장소 안내**
> - 본 저장소는 오리지널 모드(`Fallout et tu / Fallout 1 in 2`)의 전체 소스 코드를 포함하지 않으며, **한국어 번역 리소스 파일만 업로드하여 관리 및 배포하는 독립 저장소**입니다.
> - 모드를 사용하기 위해서는 반드시 원본 모드가 먼저 설치되어 있어야 합니다. 원본 모드는 아래 링크를 통해 다운로드해 주세요.
> - 원본 모드 프로젝트: [rotators/Fo1in2](https://github.com/rotators/Fo1in2)

---

## 소개 (About the Project)

폴아웃 에투(Fallout et tu, 다른 명칭: Fallout 1@2, 1at2, 1in2 등)는 폴아웃 1편을 폴아웃 2 엔진으로 구동하는 엔진 이식 모드로, 타당한 범위 내에서 폴아웃 2의 유용한 시스템과 개선 기능을 최대한 활용하여 더욱 쾌적한 플레이를 제공합니다.

### 주요 특징
- 폴아웃 1을 폴아웃 2 엔진 상에 거의 1:1 비율로 재현
- 영웅 외형(Hero Appearance) 모드 기본 통합 (대머리, 장발, 흑인 남성 캐릭터 및 펑크 스타일 여성 캐릭터 외형 추가)
- 폴아웃 2 스타일의 상인 인벤토리 재입고(Restocking) 시스템 적용
- 동료 및 일반 NPC 밀치기 기능 지원 (길막 해결)
- 동료 레벨업 시스템 및 착용 방어구에 따른 동료 외형 변경 기능
- 전투 중 동료를 직접 조종할 수 있는 옵션 제공
- 자동 문 여닫기 기능
- 나만의 오토바이를 구매하여 황무지 횡단 가능
- 게임 밸런스를 해치지 않는 선에서 엄선된 폴아웃 2 무기들이 세계관 곳곳에 추가
- 폴아웃 2 스타일의 무기 개조/업그레이드 기능
- 클래식 폴아웃 2 스타일의 동굴 및 신규 광산 조우(인카운터) 맵 탐험
- 인카운터 맵에서 게코(Gecko)와 같은 폴아웃 2 크리처 등장
- 게임 완료 후에도 계속 플레이 가능(Post-endgame)
- 수많은 버그가 수정되어 오리지널 1편보다 훨씬 더 안정적인 구동 가능

---

## 설치 가이드 (Installation Guide)

한국어 패치를 적용하려면 먼저 오리지널 **폴아웃 에투(Fallout et tu)** 모드가 설치되어 있어야 합니다.

### 1단계: 폴아웃 에투 원본 모드 설치
1. **폴아웃 1(FALLOUT 1)**과 **폴아웃 2(FALLOUT 2)**를 PC에 설치합니다. (두 게임 모두 정식 파일이 반드시 필요합니다.)
2. [폴아웃 에투 최신 버전](https://github.com/rotators/Fo1in2/releases/latest/download/Fallout1in2.zip)을 다운로드합니다.
3. 다운로드한 압축 파일 내용물들을 폴아웃 2 설치 메인 디렉토리(즉, `master.dat`와 `critter.dat` 파일이 위치한 폴더)에 풀어줍니다.
   - **올바른 폴더 구조 예시:**
     ```text
     \Fallout 2\Fallout1in2\Fallout2.exe
     ```
4. `Fallout1in2\UNDAT.EXE`를 실행한 후, 폴아웃 1이 설치된 경로에서 `MASTER.DAT` 파일을 지정해 줍니다.
5. 추출 대상 폴더(Extraction target)로 `Fallout1in2` 폴더를 선택하고 **Extract** 버튼을 눌러 원본 자원 파일 추출을 진행합니다.

### 2단계: 한국어 패치 적용
1. 본 한국어 패치 저장소의 릴리즈 페이지에서 최신 배포 파일을 다운로드하거나, 우측 상단의 초록색 **`Code` -> `Download ZIP`** 버튼을 클릭하여 전체 파일을 다운로드합니다.
2. 다운로드한 파일의 압축을 푼 뒤, 내부에 들어 있는 `Fallout1in2` 폴더를 복사하여 **폴아웃 2 메인 디렉토리**에 붙여넣습니다. (기존 폴더에 덮어쓰기 합니다.)

### 3단계: 게임 실행
- `Fallout1in2\Fallout2.exe`를 실행하여 한국어로 번역된 폴아웃 에투를 플레이합니다!

> [!NOTE]
> 리눅스 및 와인(Wine) 환경에서 게임 구동에 문제가 발생할 경우, Wine의 DLL 재정의(override) 우선순위를 다음과 같이 설정해 보세요:
> `WINEDLLOVERRIDES="ddraw.dll=n,b" wine Fallout2.exe`

---

## 모드 설정 (Configuration)

모드의 상세 옵션 설정은 [Fallout1in2/config/fo1_settings.ini](Fallout1in2/config/fo1_settings.ini)에서 변경할 수 있습니다. **반드시 새 게임을 시작하기 전에** 이 설정을 확인하고 입맛에 맞게 변경하는 것을 권장합니다. 게임 도중에 설정을 변경하면 저장 데이터가 깨지거나 오류가 발생할 수 있습니다.

기타 설정 파일들:
- [Fallout1in2/ddraw.ini](Fallout1in2/ddraw.ini): sfall 엔진 개선 및 유틸리티 설정
- [Fallout1in2/f2_res.ini](Fallout1in2/f2_res.ini): 고해상도 그래픽 패치 설정
- [Fallout1in2/mods/sfall-mods.ini](Fallout1in2/mods/sfall-mods.ini): 바닥 아이템 하이라이트 및 전투 중 동료 제어 설정
- [Fallout1in2/config/](Fallout1in2/config/) 폴더: 기타 하위 편의성 모드 설정

---

## 스팀 연동 (Steam Client Integration)

오리지널 폴아웃 1 대신 이 이식 모드가 스팀 클라이언트 상에서 바로 실행되도록 손쉽게 연동할 수 있습니다. 번거로운 설정을 도와주는 전용 런처 연동 도구가 있으니 자세한 방법은 아래 스레드를 참고해 주세요.
- 관련 안내: https://nma-fallout.com/threads/220425/

---

## 추가 모드 추천 (Recommended Mods)

폴아웃 에투에 기본 내장되어 있지는 않으나 함께 사용 시 게임의 편의성을 높여주는 추천 모드 목록입니다.
- [고음질 음악 패치 (High quality music)](https://github.com/BGforgeNet/Fallout2-HQ-music)
- [동료 일괄 명령 제어 (Party Orders)](https://github.com/BGforgeNet/Fallout2_Party_Orders)
- [FO2 편의성 모드팩 (FO2tweaks)](https://github.com/BGforgeNet/FO2tweaks)
- [Banjo의 폴아웃 2 모드 컬렉션](https://www.nma-fallout.com/threads/banjos-fallout-2-mods.220413/)
- [HD 리마스터 동영상 패치](https://www.nma-fallout.com/threads/fallout-ettu-hd-videos-playable-ingame.221565/)

---

## 관련 번역 문서 링크 (Translated Documents)

- [폴아웃 에투 소개서 (docs/ettu-readme.md)](docs/ettu-readme.md)
- [폴아웃 에투 세부 설명서 (docs/ettu-mod-readme.md)](docs/ettu-mod-readme.md)
- [변경 사항 이력 (docs/NEWS.md)](docs/NEWS.md)
- * SFall 한글호환패치 [소스코드](https://github.com/munument1/Unofficial-KR-Sfall)

---

## 특별 감사 (Special Thanks)

이 멋진 프로젝트가 탄생하고 유지될 수 있도록 아낌없이 도와주신 NovaRain 님과 Mr.Stalin 님께 깊은 감사를 전합니다.
또한, 한국어 번역 작업을 위해 함께해 주시는 모든 번역가분들의 노고에 진심으로 감사드립니다.

