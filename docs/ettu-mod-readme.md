폴아웃 에투 (FALLOUT ET TU)
-------------
폴아웃 1을 폴아웃 2 엔진으로 이식하는 프로젝트


폴아웃 에투(Fallout et tu, 다른 명칭: Fallout 1@2, 1at2, 1in2 등)는 폴아웃 1편을 2편 엔진으로 구동하는 모드로, 타당한 범위 내에서 폴아웃 2의 유용한 시스템과 개선 기능을 최대한 활용합니다.

---

토론 및 커뮤니티
- https://nma-fallout.com/threads/218045/ (정식 출시 및 베타)
- https://nma-fallout.com/threads/217892/ (알파 버전)
- https://nma-fallout.com/threads/179809/ (구버전 아카이브)

저장소
- https://github.com/rotators/Fo1in2/


모드 설치 안내 (MOD INSTALLATION)
---------------------------------

1. **폴아웃 1(FALLOUT 1) 설치**
   - 폴아웃 1의 오리지널 데이터가 **반드시 필요**합니다!

2. **폴아웃 2(FALLOUT 2) 설치**
   - 폴아웃 1인2 엔진 이식 모드를 실행하기 위해 **반드시 필요**합니다!

3. **폴아웃 에투(FALLOUT ET TU) 파일 압축 해제**
   - 폴아웃 에투 압축 파일 내용물들을 폴아웃 2가 설치된 메인 폴더(`master.dat` 및 `critter.dat` 파일이 위치한 폴더)에 풀어줍니다.
   - 폴더 구조가 다음과 같아야 합니다:
     ```
     \Fallout 2\Fallout1in2\Fallout2.exe
     ```
     에픽게임즈(Epic Games) 버전 사용 시:
     ```
     \fallout2\Fallout 2 English\Fallout1in2\Fallout2.exe
     ```

4. **`UNDAT.EXE` 실행 및 파일 추출**
   - `UNDAT.EXE`를 실행한 뒤, 폴아웃 1이 설치된 경로에서 `MASTER.DAT` 파일을 선택해 줍니다.
     - 배포 패키지(Pre-release 또는 정식 Release 팩)를 사용하는 경우, `UNDAT.EXE`는 `Fallout1in2` 폴더 내에 있습니다.
     - GitHub 저장소에서 소스를 받은 경우, `UNDAT.EXE`는 `Tools\UndatUI` 폴더에 있습니다.
     - 리눅스(Linux) 환경에서는 `WINE`이 설치된 상태에서 `UNDAT.SH`를 대신 사용할 수 있습니다.
       - 배포 패키지의 경우 `Fallout1in2` 폴더 내에, 저장소 소스의 경우 `Tools/UndatCLI` 폴더에 있습니다.
   - 추출 대상 폴더(Extraction target)로 `Fallout1in2` 폴더를 선택합니다.
   - **Extract** 버튼을 눌러 파일을 추출합니다.

모든 준비가 완료되었습니다! 이제 `Fallout1in2\Fallout2.exe`를 실행하여 게임을 즐기실 수 있습니다.

리눅스 및 와인(Wine) 환경에서 실행 관련 오류가 발생할 경우, Wine의 DLL 재정의(override) 우선순위를 다음과 같이 설정하고 실행해 보세요:
`WINEDLLOVERRIDES="ddraw.dll=n,b" wine Fallout2.exe`


모드 설정 (CONFIGURATION)
-------------------------

모드의 주요 옵션 및 설정은 [../Fallout1in2/config/fo1_settings.ini](../Fallout1in2/config/fo1_settings.ini)에서 변경할 수 있습니다. **반드시 새 게임을 시작하기 전에** 이 설정을 확인하고 입맛에 맞게 튜닝하는 것을 강력히 권장합니다. 게임 도중에 설정을 변경하면 저장 데이터(세이브)가 손상되거나 예측할 수 없는 오류가 발생할 수 있습니다.

기타 유용한 설정 파일:
- [../Fallout1in2/ddraw.ini](../Fallout1in2/ddraw.ini) (sfall 기능 관련 설정)
- [../Fallout1in2/f2_res.ini](../Fallout1in2/f2_res.ini) (고해상도 패치 관련 설정)
- [../Fallout1in2/mods/sfall-mods.ini](../Fallout1in2/mods/sfall-mods.ini) (아이템 하이라이트 및 전투 중 동료 제어 설정)
- [../Fallout1in2/config/](../Fallout1in2/config/) 폴더 (기타 자잘한 편의성 모드 설정)


스팀 연동 (STEAM)
-----------------

오리지널 폴아웃 1을 실행하는 대신 이 모드가 스팀 클라이언트에서 바로 켜지도록 간편하게 연동할 수 있습니다. 번거로운 수동 설정을 최소화하도록 돕는 전용 도구가 출시되어 있으니, 자세한 내용은 아래 링크를 참고하세요.
참조 링크: https://nma-fallout.com/threads/220425/


추가 콘텐츠 (ADDITIONAL CONTENT)
--------------------------------

대부분의 선택형 모드들은 핵심 시스템의 일부로 내장되어 있어 [../Fallout1in2/config/fo1_settings.ini](../Fallout1in2/config/fo1_settings.ini)를 편집하는 것만으로 켜고 끌 수 있지만, 메인 코드베이스와 별개로 통합된 몇 가지 미니 모드들도 함께 포함되어 있습니다.

### 소지 무게 표시기 (Carry Weight Indicator) ###
[../Fallout1in2/mods/ShowLootWeight](../Fallout1in2/mods/ShowLootWeight)

아이템 루팅 및 훔치기 화면에서 현재 소지 무게와 최대 소지 무게를 직관적으로 확인할 수 있도록 무게 표시기를 화면에 추가합니다.

### 폴아웃 1 인터페이스 (Fallout 1 Interface) ###
[../Fallout1in2/mods/fo1_interface](../Fallout1in2/mods/fo1_interface)

**기본 활성화 상태.**
인터페이스 그래픽을 폴아웃 2 스타일에서 오리지널 폴아웃 1 스타일로 변경합니다.

### 폴아웃 1 산악 지대 인카운터 맵 (Fallout 1 Maps - Mountains) ###
[../Fallout1in2/mods/fo1_maps_mountains](../Fallout1in2/mods/fo1_maps_mountains)

**기본 활성화 상태.**
산악 인카운터 맵의 시야 영역을 확장하여 1280x720 픽셀 해상도 사용 시 화면 상하단에 블랙바가 생기는 현상을 방지합니다.

### 사망 애니메이션 개선 (Improved Death Animations) ###
[../Fallout1in2/mods/Anim_ImprovedSMutantDeath](../Fallout1in2/mods/Anim_ImprovedSMutantDeath)

**기본 활성화 상태.**
슈퍼 뮤턴트 및 파워 아머를 입은 대상의 화염 사망 및 감전 사망 애니메이션 크기를 조정하여 일반 크기에 어색하지 않게 잘 맞도록 개선합니다.

### 고해상도 인터페이스 이미지 (Interface Upscaled) ###
[../Fallout1in2/mods/InterfaceUpscaled](../Fallout1in2/mods/InterfaceUpscaled)

일부 고정 이미지(시작화면, 사망 화면, 엔딩 슬라이드, 마을/월드맵 등)가 보다 선명한 고해상도 이미지로 대체됩니다.

### 인벤토리 사용 AP 조절 (Inventory AP cost) ###
[../Fallout1in2/mods/InventoryAPcosts](../Fallout1in2/mods/InventoryAPcosts)

인벤토리를 열고 닫거나 인벤토리 내에서 아이템을 사용할 때의 소모 AP(행동 포인트)를 입맛에 맞춰 조정합니다.

### 독일어 언어 팩 (Language Pack - German) ###
[../Fallout1in2/mods/fo1_lang_german](../Fallout1in2/mods/fo1_lang_german)

폴아웃 에투의 독일어 번역 패치입니다. 해당 폴더 내의 리드미(README) 파일을 읽어보시는 것을 권장합니다.

### 프랑스어 언어 팩 (Language Pack - French) ###
[../Fallout1in2/mods/fo1_lang_french](../Fallout1in2/mods/fo1_lang_french)

폴아웃 에투의 프랑스어 번역 패치입니다. 해당 폴더 내의 리드미(README) 파일을 읽어보시는 것을 권장합니다.

### 로보독 (Robodog) ###
[../Fallout1in2/mods/fo1_robodog](../Fallout1in2/mods/fo1_robodog)

동료인 도그밋(Dogmeat)을 사이보그 개인 '로보독'으로 교체하고 전투 방식을 일부 변경합니다.


추천 추가 모드 (ADDITIONAL MODS)
---------------------------------
폴아웃 에투에 기본 내장되어 있지는 않지만 게임 품질(QoL)을 획기적으로 올려주는 추천 모드들입니다:
- [고음질 음악 패치 (High quality music)](https://github.com/BGforgeNet/Fallout2-HQ-music)
- [동료 일괄 명령 제어 (Party Orders)](https://github.com/BGforgeNet/Fallout2_Party_Orders)
- [FO2 편의성 모드팩 (FO2tweaks)](https://github.com/BGforgeNet/FO2tweaks)
- [Banjo의 폴아웃 2 모드 모음집](https://www.nma-fallout.com/threads/banjos-fallout-2-mods.220413/)
- [HD 리마스터 동영상 패치](https://www.nma-fallout.com/threads/fallout-ettu-hd-videos-playable-ingame.221565/)


특별 감사 (SPECIAL THANKS)
--------------------------

이 프로젝트를 진행하는 동안 아낌없는 인내와 조언, 스크립트 작성 안내, sfall 튜닝 가이드, 테스트 참여 및 전반적인 지원을 아끼지 않아 주신 NovaRain 님과 Mr.Stalin 님께 깊은 감사를 드립니다.
늘 감사하고 사랑합니다!
