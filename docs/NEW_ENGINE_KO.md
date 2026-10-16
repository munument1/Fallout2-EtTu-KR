# 에투 새 출력 엔진 설치 참고

EtTu 2.0.3911 독립 시험본에서 확인한 본문·줄바꿈과 보완한 한국어 메뉴·배치가 정상임을 사용자가 확인했다. 공식 sfall 4.5.1을 유지하며 전체 UI·장시간 플레이 검증은 별도다.

## 모드와 엔진을 별도 관리

기준 모드: EtTu 2.0.3911. 엔진: [공통 출력 모듈](https://github.com/munument1/Fallout2-Korean-Text-Engine). 실행 프로필: `ettu`.

## KR 1.0 릴리스 설치 순서

릴리스에는 번역 ZIP `FO1ET.TU.KOR-v2.0.3911-KR1.0-classic-data.zip`, 공통 엔진 ZIP `korean-text-engine-1.1-profile4.zip`, `SHA256SUMS.txt`를 제공한다. 두 ZIP은 용도가 다르다.

1. 게임을 종료한다. 원본 EtTu 2.0.3911을 새 독립 폴더에 준비하고 공식 UNDAT 도구로 보유한 Fallout 1 자산을 가져온다. 기존 1.16 한패 폴더 전체를 복사하지 않는다.
2. 공통 엔진 ZIP을 게임 밖의 도구 폴더(예: `D:\Tools\KoreanTextEngine`)에 푼다. Python 3.10 이상을 준비하고 해당 도구 폴더에서 `python -m pip install -r requirements.txt`를 실행한다.
3. 별도로 보유한 `FO2_UPU_CHT_v34`의 원본 `Fallout2.exe`와 `fallout2font.dll`을 준비한다. 이 입력 파일과 원본 게임·공식 sfall 파일은 한패에 동봉하지 않는다. 허용 해시는 엔진 ZIP의 `runtime-manifest.json`에 있다.
4. 엔진 도구 폴더에서 아래 명령을 자신의 경로에 맞춰 실행한다. 먼저 `--dry-run`으로 확인한 뒤 그 옵션만 빼고 설치한다. `ettu`는 검증된 원본 US 1.02d EXE를 사용하는 프로필이므로 별도의 `--base-exe`는 필요하지 않다.

```powershell
python tools/install_engine.py 'D:\Games\Fallout2\Fallout1in2' --profile ettu --cjk-exe 'D:\CJK\Fallout2.exe' --legacy-font 'D:\CJK\fallout2font.dll' --dry-run
```

5. 번역 ZIP을 **`Fallout1in2` 폴더**에 푼다. `Fallout1in2\data\text\korean`이 생기는 위치여야 한다. `Fallout2.cfg`의 `[system] language=korean`을 확인하고 클래식 **`Fallout2.exe`**로 실행한다.

출력 엔진은 공통 엔진 커밋 [`8ce23cfa0529`](https://github.com/munument1/Fallout2-Korean-Text-Engine/tree/8ce23cfa0529080dd76831d82fd5fd7dc80ee53b), manifest `1.1-profile4`에 고정했다. 에투에서 검증한 출력 DLL의 SHA256은 `70c8b352e42c30dcadd19e4cf350e0661772874fe840a9afe6306e6929e3f02f`로 그대로다.

공식 sfall 4.5.1 `ddraw.dll` SHA256: `02469e78c6132010946612ec17cf4bd087aafa85a4485767fae7fba3a4151d24`. 설치 도구는 다른 sfall DLL을 강제로 허용하지 않으며 이 DLL을 수정하지 않는다.

공식 sfall의 DLL은 수정하지 않는다. 공통 엔진은 사용자가 별도로 제공한 CJK EXE·글꼴 DLL에서 런타임을 구성하며, 모드 전용 EXE 변경과 리소스를 보존한다. 지원 EXE 해시는 공통 엔진의 runtime-manifest.json에 한정한다. 검증한 모드와 다른 EXE를 강제로 허용하지 않는다.

번역 적용은 설치본의 language=korean에 맞춰 data/text/korean을 사용한다. 배경 이야기는 data/premade의 .bio 파일을 포함한다. 원본 모드의 CFG 전체·ddraw.ini 전체·sfall.dat·스크립트를 번역 ZIP으로 덮어쓰지 않는다.

## 메뉴 표시 설정

공식 CJK 경로의 메뉴 버튼·글자 배율에 맞춘 확인된 설정이다.

```ini
[MAINMENU]
MAIN_MENU_SIZE=0
USE_HIRES_IMAGES=0
SCALE_BUTTONS_AND_TEXT_MENU=0
```

이 항목은 f2_res.ini에 들어간다. 해상도 자체는 별도로 유지한다. 기존 메뉴 그림을 원래 크기로 표시해 배경만 확대되는 배치 어긋남을 피한다.

글꼴은 TEXT=Galmuri9 / Size 10 / Weight 400, BUTTON=Galmuri11 / Size 14 / Weight 600을 사용한다. SoftGreen=1, SoftTextColors=1은 차분한 글자색 설정이다.

이전 배포물을 되돌리려면 보존된 기존 릴리스를 사용한다. 공통 엔진 설치 도구로 변경한 파일은 해당 도구의 --restore로 복구하며, 사용자가 변경한 파일을 자동 덮어쓰지 않는다.

클래식 ZIP은 게임에서 읽는 번역 텍스트를 대상으로 하며 SVE 원문 백업 파일과 다른 언어의 Appearance 텍스트는 포함하지 않는다. 해당 원본 파일은 저장소에서 보존한다.

2.0은 원본 모드를 새 독립 복사본에 설치하고 Fallout 1 자산을 공식 UNDAT 도구로 가져온 뒤 한국어 모듈과 번역 ZIP을 적용한다. 게임은 클래식 `Fallout2.exe`로 실행한다. 1.16의 스크립트·설정·전체 data 폴더를 2.0 위에 복사하지 않는다.
