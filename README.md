# RimWorld Mod Manager (림월드 모드 관리자)

RimWorld(Steam판) 모드를 켜고 끄고, 로드 순서를 정리하는 Windows용 도구입니다.
A Windows tool to turn RimWorld (Steam) mods on and off and keep their load order in shape. English below.

> An **unofficial** tool by skybogli, not affiliated with Ludeon Studios. See [LICENSE](LICENSE).

## 받기 / Download

[Releases](https://github.com/skybogli/RimWorld-Mod-Manager/releases)에서 `RimWorld-Mod-Manager-v<버전>-x64.zip`을 받아
압축을 풀고 `RimWorld Mod Manager.exe`를 실행합니다. 설치는 필요 없습니다.
처음 실행하면 Steam에서 림월드 설치 폴더와 창작마당 폴더를 자동으로 찾습니다.
새 버전이 나오면 앱 안에서 알려 주고 업데이트할 수 있습니다.

Get `RimWorld-Mod-Manager-v<version>-x64.zip` from [Releases](https://github.com/skybogli/RimWorld-Mod-Manager/releases),
unzip it and run `RimWorld Mod Manager.exe` (no installer). It finds the game and Workshop folders through Steam,
and tells you in the app when a new version is out.

## 주요 기능

- **규칙 정렬**: 의존 모드와 loadAfter / loadBefore를 지키도록 켜진 모드를 정렬합니다. Harmony·Core·DLC가 앞에 오고,
  자리는 되도록 적게 바꿉니다. 커뮤니티가 모아 둔 순서 규칙도 함께 씁니다(설정에서 끄기 가능).
- **경고**: 필요한 모드 없음·꺼짐, 비호환, 순서 위반, 지원 버전 아님, 같은 packageId 사본, packageId 없는 옛 모드를
  카드 배지와 오른쪽 **문제** 탭에서 보여 줍니다. 모드를 켤 때 꺼져 있는 의존 모드도 함께 켤지 묻습니다.
- **카테고리 정리**: 카테고리로 묶고, 📌 고정, 🚫 로드하지 않는 카테고리, 실제 로드 순서 패널, 되돌리기 / 다시 실행, 메모.
- **프리셋 탭**: 켜짐/꺼짐, 카테고리 배치, 로드 순서를 이름을 붙여 저장하고 불러옵니다. 자동 프리셋, 프리셋끼리 비교.
- **세이브 탭**: 세이브 파일(.rws)의 모드 목록을 지금 목록과 비교합니다.
- **한글화**: 카드에 한국어 번역 포함 여부를 표시하고, 한글화 모드와 원본의 관계를 정리해 보여 줍니다.
  **모드 도구**에서 모드를 번역해 번역 모드로 만들 수 있습니다(구글 번역, AI 엔진).
- **목록 공유**: 내보내기·가져오기(ModsConfig.xml, 모드 목록 파일, 세이브 .rws), 목록 문자열(`RANDY1:`), 목록 뷰어 창.
- **기타**: 창작마당 구독 대기열, 모드 설명 번역, 게임 로그에서 문제 모드 찾기, 11개 언어 화면.

## 게임 파일은 어떻게 다루나요

- 바꾸는 파일은 `ModsConfig.xml`의 `activeMods`(켜진 모드와 순서) 하나뿐입니다. `version`·`knownExpansions`는 그대로 둡니다.
  위치: `%USERPROFILE%\AppData\LocalLow\Ludeon Studios\RimWorld by Ludeon Studios\Config\ModsConfig.xml` (설정에서 바꿀 수 있음)
- 저장하기 전에 이전 파일을 `%APPDATA%\RimWorld Mod Manager\backups`에 백업합니다.
- 모드 파일은 읽기만 합니다. 모드 도구로 만든 번역 모드는 새 폴더로 만들어집니다.

---

## Features (English)

- **Rule sort**: sorts the mods that are on to keep dependencies and loadAfter / loadBefore, Harmony · Core · DLC first,
  moving as few as it can. Uses community-collected load order rules too (can be turned off).
- **Warnings**: missing or disabled dependencies, incompatibilities, order problems, unsupported game versions, duplicate
  packageIds and old mods without one — as card badges and in the right panel's **Problems** tab. Turning a mod on offers
  to turn its disabled dependencies on too.
- **Categories**: group mods, 📌 pins, 🚫 categories that don't load, the actual load order panel, undo / redo, notes.
- **Presets tab**: save and load what's on, the category layout and the load order under a name; auto presets; compare two presets.
- **Saves tab**: a save's (.rws) mod list compared with the current one.
- **Translations**: shows which mods have a Korean (or your game language's) translation; the **Mod Tools** window turns
  a mod's text into a translation mod of its own (Google Translate or AI engines).
- **Sharing**: export / import (ModsConfig.xml, mod list files, saves), list strings (`RANDY1:`), a list viewer window.
- **More**: Workshop subscribe queue, description translation, finding the mod behind errors in the game log, 11 UI languages.

## What it changes in the game

Only `activeMods` in `ModsConfig.xml` (the mods that are on and their order); `version` and `knownExpansions` stay as they are.
The previous file is backed up to `%APPDATA%\RimWorld Mod Manager\backups` first. Mod files are only read.

## License

MIT — see [LICENSE](LICENSE). The third-party notices that go with the app are in its release zip.
RimWorld is a trademark of Ludeon Studios; this project is not affiliated with it.
