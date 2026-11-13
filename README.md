# RimWorld Mod Manager (림월드 모드 관리자)

RimWorld(Steam판) 모드를 켜고 끄고, 로드 순서를 정리하는 Windows용 도구입니다.
A Windows tool to turn RimWorld (Steam) mods on and off and keep their load order in shape. [English below](#english).

> An **unofficial** tool by skybogli, not affiliated with Ludeon Studios. See [LICENSE](LICENSE).

---

## 어떤 프로그램인가요

모드가 수십~수백 개가 되면 어떤 모드가 켜져 있는지, 순서가 맞는지, 빠진 의존 모드는 없는지 게임 안에서 확인하기
어렵습니다. 림월드 모드 관리자는 모드를 **카테고리별 칸**에 나눠 보여 주고, 켜고 끄기·순서 정리·문제 확인을 한 화면에서
하게 해 줍니다. 바꾼 내용은 **저장**을 눌러야 게임의 `ModsConfig.xml`에 반영되며, 저장할 때마다 이전 파일을 백업합니다.

설치 없이 압축만 풀어 실행하고, 새 버전이 나오면 앱 안에서 업데이트할 수 있습니다.

### 한눈에 보기

- **규칙 정렬**: 의존 모드와 loadAfter / loadBefore를 지키도록 로드 순서를 자동으로 정리
- **문제 경고**: 필요한 모드 없음·꺼짐, 비호환, 순서 위반, 지원 버전 아님 등을 카드와 문제 탭에 표시
- **카테고리 정리**: 모드를 칸으로 묶고, 📌 고정, 🚫 로드하지 않는 카테고리, 접기, 메모, 되돌리기
- **프리셋 · 세이브 비교**: 모드 구성을 이름 붙여 저장하고, 프리셋끼리 또는 세이브 파일과 비교
- **목록 공유**: 목록 문자열·파일·창작마당 주소로 모드 목록을 주고받고, 없는 모드는 구독 대기열로
- **한글화 · 모드 도구(베타)**: 한국어 번역 여부 표시, 모드를 번역해 번역 모드로 만들기

## 받기와 실행

1. [Releases](https://github.com/skybogli/RimWorld-Mod-Manager/releases)에서 `RimWorld-Mod-Manager-v<버전>-x64.zip`을 받습니다.
2. 아무 폴더에 압축을 풀고 `RimWorld Mod Manager.exe`를 실행합니다. 설치는 필요 없습니다.
3. 처음 실행하면 Steam에서 림월드 설치 폴더와 창작마당 폴더를 자동으로 찾고, 게임의 `ModsConfig.xml`에서 모드 목록을
   읽습니다. 이어서 카테고리 구성을 고릅니다(모드 이름으로 나누는 기본 분류, 또는 직접 만들기).
4. 시작할 때 새 버전이 있는지 확인하고, 있으면 업데이트할지 묻습니다. 업데이트해도 설정·프리셋은 그대로 남습니다.

## 기능 자세히

### 화면 구성
- **가운데 카테고리 칸**: 모드 카드가 카테고리별로 나뉘어 있습니다. 카드 앞 체크박스로 켜고 끄고, 카테고리 이름 앞
  체크박스로 칸 전체를 켜고 끕니다.
- **실제 로드 순서 패널**: 게임에 저장될 순서 그대로의 목록입니다(위쪽이 먼저 로드). 기본은 카테고리 순서(왼쪽 → 오른쪽,
  위 → 아래)를 따르고, 여기서 끌어다 놓으면 카테고리와 상관없이 자리를 정할 수 있습니다(📌로 표시).
- **오른쪽 패널**: 선택한 모드의 상세(Steam 설명·태그·미리보기), **문제**, **프리셋**, **세이브** 탭.
- **아래 상태 막대**: 전체·켜짐·선택 수, 새로 생기거나 업데이트된 모드, 게임 버전.

### 규칙 정렬과 문제 경고
- **규칙 정렬**은 켜진 모드를 의존 모드, loadAfter / loadBefore(force 포함)에 맞게 정렬합니다. Harmony · Core · DLC가
  앞에 오고, 자리는 되도록 적게 바꿉니다.
- RimSort 커뮤니티가 모아 둔 **순서 규칙**(CC0)도 함께 씁니다. 주 1회 받아 두며, 설정에서 끄거나 지금 받을 수 있습니다.
- **경고 종류**: 필요한 모드 없음 / 꺼짐, 비호환 모드가 함께 켜짐, 순서 위반, 지금 게임 버전을 지원하지 않음,
  같은 packageId 사본, packageId가 없는 옛 모드(림월드 1.1 이전, 찢어진 카드로 표시), 업데이트가 아직 게임 폴더에
  복사되지 않음. 카드 배지와 오른쪽 **문제** 탭에서 보고, F8 / Shift+F8로 다음 / 이전 문제 모드로 이동합니다.
- 모드를 켤 때 꺼져 있는 의존 모드가 있으면 함께 켤지 묻습니다.

### 카테고리
- 모드는 끌어다 놓기, 오른쪽 클릭, 옮기기/붙여넣기, 단축키로 옮깁니다. 카테고리 순서가 곧 로드 순서입니다.
- 카테고리 이름 바꾸기·색·순서 바꾸기, 칸 폭 조절, 가로 / 세로 배치.
- **📌 고정**: 로드 순서에서 직접 자리를 정한 모드. ⟲ 버튼으로 모두 풀고 카테고리 순서로 맞출 수 있습니다.
- **🚫 로드하지 않음**: 이 카테고리의 모드는 게임에서 빠집니다. 각 모드가 켜져 있었는지는 기억했다가, 카테고리에서
  꺼내면 되돌립니다.
- **접기**: 카테고리의 모드 목록을 접어 둡니다(헤더 · 카테고리 목록의 오른쪽 클릭). 접힌 카테고리의 모드로 이동하면
  자동으로 펼치고 알려 줍니다.
- **카테고리별 정렬**: 이름순 등 기준을 정하고 자동 정렬을 켤 수 있습니다. **자동 분류**는 미분류 모드를 이름과
  packageId로 나눕니다.
- **메모**, **되돌리기 / 다시 실행**(Ctrl+Z / Ctrl+Y).

### 프리셋과 세이브
- **프리셋 탭**: 켜진 모드, 로드 순서, 카테고리 배치를 이름을 붙여 저장하고 불러옵니다. 게임에 저장할 때마다 자동
  프리셋을 남길 수 있고(설정), 두 프리셋을 골라 무엇이 다른지 비교합니다.
- **세이브 탭**: 세이브 파일(.rws)에 기록된 모드 목록을 지금 목록과 비교하고, 그 목록을 불러올 수 있습니다.

### 목록 공유
- **내보내기 / 가져오기**: 로드 순서와 카테고리 배치를 텍스트 파일로 저장합니다. 가져오기는 그 파일과
  `ModsConfig.xml`, RimSort · RimPy 목록, 세이브(.rws)를 읽습니다.
- **목록 문자열**(`RANDY1:`로 시작): 모드 목록을 한 줄 문자열로 복사해 채팅 등으로 주고받습니다.
- **주소 붙여 넣기 · 끌어다 놓기**: 창작마당 주소·번호, packageId, 모드 이름을 붙여 넣거나 브라우저에서 끌어다 놓아도
  됩니다. 목록 문자열과 섞여 있어도 함께 읽습니다.
- **모드 목록 뷰어**: 목록을 별도 창으로 열어 보고, 빈 뷰어에 모드를 모으거나 창 사이에 모드를 보내고, 프리셋으로
  저장합니다.
- 목록에 있지만 설치되지 않은 모드는 **자리표시**로 들어오며, **구독 대기열**에서 차례로 창작마당 페이지를 열어 받습니다.

### DLC
- Core와 각 DLC의 설명(게임 파일에서 읽음, 번역 가능)과 Steam 상점 페이지를 보여 줍니다.
- 받은 목록에 갖고 있지 않은 DLC가 있으면 **구매 필요**로 표시하고, 누르면 상점 페이지를 엽니다.

### 한글화와 모드 도구 (베타)
- 카드에 한국어(또는 게임 언어) 번역이 들어 있는지 표시하고, 한글화 모드와 원본 모드의 관계를 정리해 보여 줍니다.
- **모드 도구**(Ctrl+T) 창에서 모드의 글(Keyed, DefInjected)을 번역해 **번역 모드**로 만듭니다.
  - 번역 방식: 구글 번역, AI 엔진(Claude · OpenAI · Gemini · OpenAI 호환 주소의 로컬 모델), 또는 AI 채팅에
    복사해 넣고 결과를 붙여 넣기. API 키는 이 PC에서만 암호화해 저장합니다.
  - **번역·적용** 탭: 번역할 모드를 고르고(켜진 모드 / 꺼진 모드 / 전체 / 직접 고르기) 번역 모드를 만듭니다.
    만든 번역 모드는 원본 바로 뒤에 켜 둡니다.
  - **번역 검수** 탭: 줄마다 원문과 번역을 나란히 보고 고치거나 다시 번역합니다. `{0}`, `[PAWN_…]`, `<color>` 같은
    자리는 상자로 보여 주고, 빠지면 경고합니다.
  - 번역은 자동으로 백업되며 복원 · 내보내기를 할 수 있습니다.
- ⚠ **모드 도구는 아직 충분히 검증되지 않은 기능(베타)입니다.** 만든 번역 모드가 게임에서 제대로 보이지 않거나
  오류를 낼 수 있으니, 게임에 쓰기 전에 확인해 주세요. 원본 모드는 바꾸지 않으며, 만든 번역 모드는 '지우기'로
  휴지통에 보낼 수 있습니다.

### 그 밖의 기능
- **모드 설명 번역**: 상세 패널에서 모드 이름·설명을 구글 번역으로 봅니다.
- **게임 로그**: `Player.log`의 오류를 읽어 어떤 모드에서 났는지 추정합니다(도움말 → 게임 로그).
- **새 모드 · 업데이트 표시**, 모드 검색, 모드 파일 삭제.
- **화면 언어 11개**, 단축키 바꾸기, 확대 / 축소, 창 크기 · 위치 기억, 앱 안의 사용 설명서(Alt+H).

## 게임 파일은 어떻게 다루나요

- 바꾸는 파일은 `ModsConfig.xml`의 `activeMods`(켜진 모드와 순서) 하나뿐입니다. `version`·`knownExpansions`는 그대로 둡니다.
  위치: `%USERPROFILE%\AppData\LocalLow\Ludeon Studios\RimWorld by Ludeon Studios\Config\ModsConfig.xml` (설정에서 바꿀 수 있음)
- 저장하기 전에 이전 파일을 `%APPDATA%\RimWorld Mod Manager\backups`에 백업합니다(최근 30개).
- 모드 파일은 읽기만 합니다. 모드 도구로 만든 번역 모드는 새 폴더로 만들어집니다.

## 자주 묻는 것

- **게임 폴더를 못 찾아요**: ⚙ 설정(Ctrl+,)에서 림월드 설치 폴더와 Config 폴더를 직접 고를 수 있습니다.
- **저장 전으로 되돌리고 싶어요**: 저장 전이면 새로고침(Ctrl+R)으로 게임 파일 상태로 돌아갑니다. 저장 후라면 ⚙ 설정 →
  백업 폴더 열기에서 이전 `ModsConfig.xml`을 꺼내 쓰거나, 프리셋 탭의 자동 프리셋을 불러오세요.
- **설정은 어디에 있나요**: `%APPDATA%\RimWorld Mod Manager`. 앱을 업데이트하거나 폴더를 옮겨도 그대로 남습니다.
- **'미설치 / 업데이트 필요'가 떠요**: Steam이 받은 새 버전이 아직 게임 폴더에 복사되지 않은 상태입니다. 게임을 한 번
  실행하면 정리됩니다.

---

<a id="english"></a>

## What is it?

With dozens or hundreds of mods, it gets hard to see in the game which ones are on, whether their order is right and
whether a dependency is missing. RimWorld Mod Manager shows your mods in **category columns** and lets you turn them on
and off, fix the load order and check problems on one screen. Changes reach the game's `ModsConfig.xml` only when you
**Save**, and the previous file is backed up every time.

No installer: unzip and run. New versions can be installed from inside the app.

### At a glance

- **Rule sort**: puts the load order in shape so dependencies and loadAfter / loadBefore are kept
- **Warnings**: missing or disabled dependencies, incompatibilities, order problems, unsupported game versions and more,
  on the cards and in the Problems tab
- **Categories**: group mods into columns, 📌 pins, 🚫 categories that don't load, folding, notes, undo
- **Presets · saves**: save a mod setup under a name and compare presets with each other or with a save file
- **Sharing**: pass mod lists around as strings, files or Workshop links; missing mods go to a subscribe queue
- **Translations · Mod Tools (beta)**: see which mods have a translation, and turn a mod into a translation mod

## Download and run

1. Get `RimWorld-Mod-Manager-v<version>-x64.zip` from [Releases](https://github.com/skybogli/RimWorld-Mod-Manager/releases).
2. Unzip it anywhere and run `RimWorld Mod Manager.exe`. Nothing to install.
3. On the first run it finds the game and Workshop folders through Steam and reads the mod list from the game's
   `ModsConfig.xml`. Then you pick a category layout (the default one, sorted by mod name, or your own).
4. At start it checks for a new version and asks before updating. Your settings and presets are kept.

## Features in detail

### The screen
- **Category columns** in the middle hold the mod cards. The checkbox on a card turns that mod on or off; the one by a
  category name turns the whole column on or off.
- **The actual load order panel** lists the mods in the order the game will get them (top loads first). It follows the
  category order (left → right, top → bottom); drag a mod here to give it its own place regardless of its category (📌).
- **The right panel**: the selected mod's details (Steam description, tags, preview), and the **Problems**, **Presets**
  and **Saves** tabs.
- **The status bar**: total / on / selected counts, new and updated mods, the game version.

### Rule sort and warnings
- **Rule sort** sorts the mods that are on to keep dependencies and loadAfter / loadBefore (force ones included),
  Harmony · Core · DLC first, moving as few mods as it can.
- It also uses the load order rules collected by the RimSort community (CC0), fetched once a week; turn this off or
  fetch now in Settings.
- **Warnings**: missing or disabled dependencies, incompatible mods on together, order problems, no support for the
  current game version, duplicate packageIds, old mods without a packageId (before RimWorld 1.1, shown as torn cards),
  updates not yet copied to the game folder. See them as card badges and in the **Problems** tab, and jump to the
  next / previous problem with F8 / Shift+F8.
- Turning a mod on offers to turn its disabled dependencies on too.

### Categories
- Move mods by dragging, right-click, cut / paste or shortcuts. The category order is the load order.
- Rename, color and reorder categories, set column widths, lay them out horizontally or vertically.
- **📌 Pins**: mods placed by hand in the load order. ⟲ unpins them all and follows the category order again.
- **🚫 Don't load**: the mods in this category are left out of the game. Whether each one was on is remembered and
  restored when it leaves the category.
- **Folding**: fold a category's mod list (right-click its header or its entry in the category list). Jumping to a mod in
  a folded category unfolds it and says so.
- **Per-category sorting** by name and more, with auto sort. **Auto categorize** sorts uncategorized mods by name and
  packageId.
- **Notes**, **undo / redo** (Ctrl+Z / Ctrl+Y).

### Presets and saves
- **Presets tab**: save and load what's on, the load order and the category layout under a name. An auto preset can be kept
  on every save (a setting), and two presets can be compared side by side.
- **Saves tab**: compares the mod list recorded in a save (.rws) with the current one, and can load it.

### Sharing
- **Export / import**: the load order and category layout as a text file. Import reads that file, `ModsConfig.xml`,
  RimSort · RimPy lists and saves (.rws).
- **List strings** (starting with `RANDY1:`): copy a mod list as one line to share in a chat.
- **Paste or drag in links**: Workshop links and numbers, packageIds and mod names, pasted or dragged in from a browser,
  mixed with list strings too.
- **Mod list viewer**: open a list in its own window, gather mods in an empty viewer, send mods between windows, save as
  a preset.
- Mods in a list that aren't installed come in as **placeholders**; the **subscribe queue** opens their Workshop pages
  one by one.

### DLC
- Descriptions of Core and each DLC (read from the game files, translatable) and their Steam store pages.
- A DLC in a list that you don't own is marked **Not owned**; clicking it opens the store page.

### Translations and Mod Tools (beta)
- Cards show whether a mod has a Korean (or your game language's) translation, and translation mods are linked to the
  mods they translate.
- The **Mod Tools** window (Ctrl+T) translates a mod's text (Keyed, DefInjected) into a **translation mod** of its own.
  - Ways to translate: Google Translate, AI engines (Claude · OpenAI · Gemini · a local model on an OpenAI-compatible
    address), or copy into an AI chat and paste the answer back. API keys are stored encrypted, on this PC only.
  - **Translate** tab: pick the mods (on / off / all / by hand) and make translation mods, which are turned on right
    after their originals.
  - **Review** tab: original and translation side by side, line by line, to edit or translate again. Placeholders such as
    `{0}`, `[PAWN_…]` and `<color>` are shown as boxes, with a warning when one goes missing.
  - Translations are backed up automatically and can be restored or exported.
- ⚠ **Mod Tools is not fully tested yet (beta).** A translation mod it makes may not show up right or may cause errors in
  the game, so check it before you rely on it. The original mods are never changed, and 'Remove' sends a made translation
  mod to the Recycle Bin.

### More
- **Description translation**: see a mod's name and description through Google Translate in the details panel.
- **Game log**: reads errors in `Player.log` and guesses which mod they came from (Help → Game log).
- **New / updated marks**, mod search, deleting mod files.
- **11 UI languages**, custom shortcuts, zoom, remembered window size and position, a built-in guide (Alt+H).

## What it changes in the game

- Only `activeMods` in `ModsConfig.xml` (the mods that are on and their order); `version` and `knownExpansions` stay as
  they are. Location: `%USERPROFILE%\AppData\LocalLow\Ludeon Studios\RimWorld by Ludeon Studios\Config\ModsConfig.xml`
  (can be changed in Settings).
- The previous file is backed up to `%APPDATA%\RimWorld Mod Manager\backups` first (the last 30).
- Mod files are only read. Translation mods made with Mod Tools go into new folders.

## FAQ

- **It can't find the game**: pick the RimWorld folder and the Config folder in ⚙ Settings (Ctrl+,).
- **I want to go back**: before saving, Reload (Ctrl+R) returns to what the game files say. After saving, take an
  earlier `ModsConfig.xml` from ⚙ Settings → Open backup folder, or load an auto preset in the Presets tab.
- **Where are the settings?** `%APPDATA%\RimWorld Mod Manager`. They stay when you update the app or move its folder.
- **"Not installed / needs update"**: Steam has downloaded a new version that isn't copied to the game folder yet. Run
  the game once and it's sorted out.

## License

MIT — see [LICENSE](LICENSE). The third-party notices that go with the app are in its release zip.
RimWorld is a trademark of Ludeon Studios; this project is not affiliated with it.
