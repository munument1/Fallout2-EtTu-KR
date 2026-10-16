# 에투 한국어 번역 — 공통 출력 엔진 방식

기준: **EtTu 2.0.3911**. 1.16.3771의 기존 한국어 번역을 유지하고, 2.0에서 달라진 문구만 반영한다. 출력은 공식 sfall 4.5.1과 공통 한국어 출력 모듈을 사용한다.

한국어 번역 데이터는 이 저장소에서, 출력 모듈·글꼴·설치 도구는 [Fallout2 Korean Text Engine](https://github.com/munument1/Fallout2-Korean-Text-Engine)에서 관리한다. 한국어로 수정한 sfall `ddraw.dll`을 덮어쓰는 방식에서 공식 sfall과 별도 한국어 모듈을 사용하는 방식으로 전환한다.

## 현재 상태

EtTu 2.0.3911의 독립 시험본에서 사용자가 확인한 본문·줄바꿈이 정상이라고 확인했고, 영어로 남아 있던 메뉴를 보완한 뒤 한국어 메뉴·배치도 정상이라고 확인했다. 공식 sfall 4.5.1은 그대로 유지했다. 전체 UI·장시간 플레이 검증을 뜻하지 않는다.

[2.0 이행 내역](docs/ETTU_2_0_UPGRADE_KO.md)에 변경 ID와 번역 보존 범위를 기록했다.

배포: **[EtTu 2.0.3911 KR 1.0](https://github.com/munument1/Fallout2-EtTu-KR/releases/tag/v2.0.3911-KR1.0)**. 릴리스의 번역 ZIP과 공통 출력 엔진 ZIP을 함께 사용한다. 기존 1.16 릴리스와 태그는 보존한다.

## 설치

1. [공식 EtTu 2.0.3911](https://github.com/rotators/Fo1in2/releases/tag/v2.0.3911)을 별도 게임 복사본에 설치하고, 공식 UNDAT 도구로 보유한 Fallout 1의 원본 자산을 가져온다. 원본 모드의 스크립트·설정·DAT를 유지한다.
2. EtTu에 포함된 공식 sfall 4.5.1 `ddraw.dll`과 `sfall.dat`를 그대로 사용한다. 이전 한패의 `ddraw.dll`·`LangFont.ini`를 덮어쓰지 않는다.
3. 릴리스의 `korean-text-engine-1.1-profile4.zip`을 게임 밖의 도구 폴더에 풀고, [동봉 설치 안내](docs/NEW_ENGINE_KO.md)에 따라 공통 엔진의 `ettu` 프로필을 설치한다. Python과 별도 보유 CJK 입력 파일이 필요하며, 번역 ZIP만으로 출력 엔진이 설치되지는 않는다.
4. `FO1ET.TU.KOR-v2.0.3911-KR1.0-classic-data.zip`을 **Fallout1in2 폴더**에 푼다. ZIP의 `data`, `Appearance`, `translations`가 해당 폴더 바로 아래에 위치해야 한다. 번역 ZIP에는 엔진 DLL·EXE·모드 스크립트·전체 CFG를 넣지 않는다.
5. `Fallout2.cfg`에서 `[system] language=korean`을 사용한다. 다른 설정은 유지한다.

[자세한 설치와 메뉴 설정](docs/NEW_ENGINE_KO.md). 실행 파일은 클래식 `Fallout2.exe`이며, 동봉 `fallout2-ce.exe`는 이번 릴리스의 검증 대상이 아니다. 릴리스의 `SHA256SUMS.txt`로 첨부 ZIP을 확인할 수 있다.

## 번역 파일과 패키지

기존 MSG의 `{ID}{음성}{본문}` 구조와 번역을 유지한다. CP949 파일을 일괄 재변환하지 않는다. UTF-8 한국어 텍스트가 있으면 클래식 ZIP 생성 시에만 CP949로 엄격 변환한다. 표현할 수 없는 문자는 `?`로 바꾸지 않고 빌드를 중단한다. 원본 파일은 변경하지 않는다.

```shell
python tools/build_translation.py --output dist/korean-classic-data.zip
```

패키지에 포함한 파일 해시와 변환 목록은 `translation-manifest.json`에 들어간다. 게임 데이터의 언어를 중국어나 일본어로 바꾸지 않는다.

## CE/Fission

이 안내와 패키지는 클래식 x86/sfall 경로용이다. EtTu 2.0에 동봉된 CE 실행 파일의 한국어 출력은 이번 클래식 시험 범위에 포함하지 않는다. 기존 CE/Fission 자료는 [별도 엔진 저장소](https://github.com/munument1/Fallout2-Fission-CE-KR)에 있으며 2.0 지원을 자동 승계하지 않는다. 저장소의 CE용 글꼴 파일은 보존하지만 클래식 번역 ZIP에 넣지 않는다.

## 이전 배포 방식과 크레디트

[이전 안내와 크레디트](docs/LEGACY_INSTALLATION_KO.md)는 이력 확인용이다. 원본 게임·원본 모드 파일은 포함하지 않는다. 기존 번역자와 원본 모드·sfall·글꼴 제작자의 기여를 유지한다.
