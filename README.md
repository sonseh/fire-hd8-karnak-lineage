# Fire HD 8 (2018, 8세대, karnak) LineageOS 23.2

아마존 Fire HD 8 2018(8세대, 코드명 karnak)용 **비공식 LineageOS 23.2(Android 16)** 빌드입니다. 빌드 파일은 이 저장소의 **Releases**에 있습니다.

실험용 빌드입니다. 개인 태블릿 한 대에서만 시험했습니다.

## 되는 것과 확인하지 못한 것

| 되는 것 | 확인하지 못한 것 |
|---|---|
| 화면, 터치 | 카메라 |
| Wi-Fi | 블루투스 |
| 스피커 소리 | 이어폰 단자 |
| 가속도·조도 센서 | |
| 배터리, USB 충전 | |
| 영상 재생(SOOP 방송 시청 확인) | |

- MediaTek 디스플레이 드라이버 문제를 피하려고 일반 앱 화면은 GPU로 합성합니다. 영상만 하드웨어 오버레이를 씁니다.
- Google Play 서비스는 들어 있지 않습니다. 앱은 F-Droid나 Aurora Store로 설치할 수 있습니다.

## 설치 전에 필요한 것

- **부트로더 언락과 TWRP**가 이미 되어 있어야 합니다. Fire OS 버전에 따라 케이스를 열고 테스트 포인트를 단락시키는 하드웨어 작업(amonet)이 필요합니다. XDA의 karnak 언락 가이드를 따르세요. 이 저장소에는 언락 도구나 TWRP가 없습니다.
- Fire OS나 다른 ROM에서 넘어올 때는 **데이터 초기화가 필요**합니다. 중요한 파일은 먼저 PC로 옮겨 두세요.
- 비공식 빌드이며 AOSP test-keys로 서명되어 있습니다. 사용에 따른 책임은 사용자에게 있습니다.

## 설치

1. TWRP로 부팅합니다.
2. **Wipe → Advanced Wipe**에서 Dalvik/ART Cache, Cache, Data를 지웁니다(다른 ROM에서 넘어올 때).
3. ROM zip을 태블릿에 복사한 뒤 **Install**로 설치합니다. 또는 **Advanced → ADB Sideload**를 켜고 PC에서 `adb sideload lineage-23.2-<날짜>-UNOFFICIAL-karnak.zip`을 실행합니다.
4. **Reboot → System**. 첫 부팅은 몇 분 걸립니다.

ROM zip은 boot, system, vendor 파티션만 씁니다. TWRP(recovery)는 그대로 남습니다.

## 업데이트

TWRP에서 새 ROM zip을 설치하면 데이터는 그대로 남습니다. 설치 뒤 Dalvik/ART Cache만 지우면 됩니다.

## USB 디버깅

adb를 쓰려면 설정 → 태블릿 정보 → 빌드 번호를 7번 눌러 개발자 옵션을 켜고, 개발자 옵션에서 USB 디버깅을 켠 뒤 화면에 뜨는 허용 창에서 허용을 누르세요.

## 소스

각 릴리스의 `sources-*.zip`에 이 빌드에서 바꾼 소스가 `git format-patch` 형식으로 들어 있습니다(GPL). 기반은 LineageOS 23.2와 GitHub mt8163 조직의 karnak 트리(device/amazon/karnak, kernel 4.9, vendor)입니다.
