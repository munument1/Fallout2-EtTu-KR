# 에투 한국어 번역 — 공통 출력 엔진 방식

## 기존 설치 폴더에 바로 설치 (v1.2.1)

게임을 종료한 뒤 **Steam을 포함한 기존 게임·모드 설치 폴더**를 선택하세요. 시험용 전체 복사본 준비는 선택 사항입니다. 번역 ZIP을 먼저 적용하고 [한국어 출력 엔진 최신 정식 설치기](https://github.com/munument1/Fallout2-Korean-Text-Engine/releases/latest)를 실행하세요. 변경되는 원본 파일만 `korean_engine_backup_v2`에 자동 백업하며 같은 폴더에서 복구할 수 있습니다.

기준: **EtTu 2.0.3911**. 1.16.3771의 기존 한국어 번역을 유지하고, 2.0에서 달라진 문구만 반영한다. 출력은 공식 sfall 4.5.1과 공통 한국어 출력 모듈을 사용한다.

한국어 번역 데이터는 이 저장소에서, 출력 모듈·글꼴·설치 도구는 [Fallout2 Korean Text Engine](https://github.com/munument1/Fallout2-Korean-Text-Engine)에서 관리한다. 한국어로 수정한 sfall `ddraw.dll`을 덮어쓰는 방식에서 공식 sfall과 별도 한국어 모듈을 사용하는 방식으로 전환한다.

## 새로운 독립형 출력 엔진 (v1.2.1)

기존 번역문의 MSG ID와 본문은 그대로 유지합니다. 이제 게임별 프로필, 중국어 수정 EXE, 중국어 글꼴 DLL을 요구하지 않습니다. [최신 정식 설치기](https://github.com/munument1/Fallout2-Korean-Text-Engine/releases/latest)는 선택한 게임 폴더 안의 호환 Fallout 2 실행 파일을 내부 구조로 자동 인식합니다. 핵심 ABI 자체가 변경된 파일은 무리하게 패치하지 않습니다.

**설치 순서:** 번역 ZIP을 먼저 적용한 뒤 설치기를 실행하세요. 설치기가 한국어 언어 설정까지 자동으로 적용합니다.

전체 게임을 중복으로 백업하지 않습니다. EXE가 수정되므로 원상복구에 필요한 원본 파일 한 벌만 설치기가 보관합니다. 엔진은 최신 정식판이며, 게임별 긴 대화·전투·저장/불러오기를 전수 검증했다는 뜻은 아닙니다.

**독립형 엔진용 번역 ZIP:** [v2.0.3911-native-beta.2](https://github.com/munument1/Fallout2-EtTu-KR/releases/tag/v2.0.3911-native-beta.2). 기존 번역 내용은 유지하고 설치 안내·메타데이터만 독립형 엔진에 맞춰 갱신했습니다. 이전 CJK 기반 릴리스 파일은 그대로 남겨 두었습니다.

## 현재 상태

EtTu 2.0.3911의 독립 시험본에서 사용자가 확인한 본문·줄바꿈이 정상이라고 확인했고, 영어로 남아 있던 메뉴를 보완한 뒤 한국어 메뉴·배치도 정상이라고 확인했다. 공식 sfall 4.5.1은 그대로 유지했다. 전체 UI·장시간 플레이 검증을 뜻하지 않는다.

[2.0 이행 내역](docs/ETTU_2_0_UPGRADE_KO.md)에 변경 ID와 번역 보존 범위를 기록했다.

배포: **[EtTu 2.0.3911 KR 1.0](https://github.com/munument1/Fallout2-EtTu-KR/releases/tag/v2.0.3911-KR1.0)**. 기존 릴리스의 번역 ZIP은 유지할 수 있으나, 그때 첨부된 CJK 엔진 ZIP 대신 새 독립형 설치기를 사용한다. 기존 1.16 릴리스와 태그는 보존한다.

## 설치

1. 번역 버전과 일치하는 원본 모드를 준비합니다. 대상 위치는 **Fallout1in2 폴더**입니다.
2. 번역 ZIP을 **먼저** 적용합니다. GitHub Actions의 korean-classic-data 산출물을 받거나 아래 빌드 명령으로 생성한 ZIP을 게임 폴더에 풀어 data/text/korean 등을 추가합니다. 번역 ZIP에는 게임 EXE, sfall DLL, DAT, INT가 들어가지 않습니다.
3. [최신 독립형 설치기](https://github.com/munument1/Fallout2-Korean-Text-Engine/releases/latest)의 Fallout2-Korean-Native-Setup.exe를 실행하고 게임 폴더만 지정합니다. 게임 종류나 --profile 선택, 중국어 CJK EXE 및 DLL은 필요 없습니다.
4. 설치가 끝나면 기존 게임 실행기로 실행합니다.
5. 한글 표시와 대화, 메뉴, 저장/불러오기를 확인하세요. 되돌릴 때는 같은 설치기의 복구 기능을 사용합니다.

**모드별 주의:** Et Tu 2.0.3911 원본 설치 후 소유한 Fallout 1 원본 자료를 공식 UNDAT로 가져옵니다. 기존 KR1.0 릴리스의 엔진 ZIP은 이전 CJK 방식이며 이번 설치기 대신 사용하지 않습니다. CE 실행 파일은 별도입니다.

[자세한 안내](docs/NEW_ENGINE_KO.md) · [구형 설치 방식 기록](docs/LEGACY_INSTALLATION_KO.md)

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
