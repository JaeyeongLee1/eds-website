# EDSL Website 관리 가이드

이 홈페이지는 디자인 코드와 실제 내용을 분리해 두었습니다. 일상적인 업데이트는 HTML/CSS를 수정하지 않아도 됩니다.

## 가장 쉬운 방법: Pages CMS

1. `https://app.pagescms.org`에 접속합니다.
2. GitHub로 로그인합니다.
3. `kaist-eds-lab/eds-website` 저장소를 선택합니다.
4. 왼쪽에서 수정할 항목을 고릅니다.
   - Professor
   - Members
   - Publications
   - Ph.D. Alumni
   - M.S. Alumni
5. 필요한 내용만 수정하고 Save를 누릅니다.
6. 저장하면 GitHub에 변경 내역이 기록되고, GitHub Pages가 자동으로 새 홈페이지를 빌드합니다.

### 논문 추가

Publications는 연도별로 정리되어 있습니다. 기존 연도에 논문을 추가할 때는 해당 연도를 열고 Publications 목록에 항목을 추가합니다. 새 연도라면 Publications에서 새 연도 파일을 만든 뒤 논문을 입력합니다.

입력 항목은 다음과 같습니다.

- Year
- Code
- Type (Journal / Conference)
- Title
- Authors
- Full citation
- Venue label

임의로 정보를 보충하지 말고, 실제 논문 정보 그대로 입력합니다.

### 학생 추가

Members에서 Ph.D. 또는 M.S. 목록에 학생을 추가합니다.

- Name
- Research Interests
- Email
- Entry year
- Homepage (있는 경우만)
- Photo

사진은 CMS에서 업로드할 수 있도록 구성되어 있습니다. 업로드된 사진은 `assets/images/` 안에 저장됩니다.

## ChatGPT/AI에게 부탁하는 방법

GitHub 쓰기 권한을 사용할 수 있는 ChatGPT/Codex/AI 환경이라면 `kaist-eds-lab/eds-website` 저장소를 연결한 뒤 다음처럼 요청하면 됩니다.

- `eds-website에 이 논문을 추가해줘. AGENTS.md 규칙을 따라줘.`
- `김OO 학생을 Ph.D. Members에 추가해줘. 아래 정보 외에는 추측하지 마.`
- `Professor 페이지 Awards & Honors에 아래 수상 내용을 추가해줘.`

AI는 먼저 `AGENTS.md`를 읽고, 일반적인 콘텐츠 수정에서는 `_data/` 파일만 변경하도록 구성했습니다.

## GitHub에서 직접 수정하는 비상 방법

CMS를 사용할 수 없을 때 GitHub에서 아래 파일을 직접 열고 연필 아이콘으로 수정할 수 있습니다.

- Professor: `_data/professor.yml`
- Members: `_data/members.yml`
- Publications: `_data/publications/<연도>.yml`
- Ph.D. Alumni: `_data/alumni/phd.yml`
- M.S. Alumni: `_data/alumni/ms.yml`

디자인 파일인 `assets/css/`, `_layouts/`, `_includes/`는 홈페이지 디자인을 바꾸려는 경우가 아니면 수정하지 않는 것이 안전합니다.

## 운영상 중요한 원칙

- 홈페이지에 없는 사실을 임의로 추가하지 않습니다.
- 논문 citation은 받은 원문을 그대로 보존합니다.
- 새 학생이나 alumni의 affiliation/homepage를 추측하지 않습니다.
- 디자인 변경과 콘텐츠 업데이트를 분리합니다.
- 문제가 생기면 GitHub commit history에서 이전 상태로 되돌릴 수 있습니다.
- Organization에는 장기 운영을 위해 Owner를 최소 두 명 두는 것을 권장합니다.

## eds.kaist.ac.kr 연결

저장소는 `eds.kaist.ac.kr` custom domain 기준으로 구성되어 있습니다. 루트의 `CNAME` 파일과 `_config.yml`은 해당 도메인을 사용합니다. DNS 전환 시 `eds.kaist.ac.kr`의 CNAME이 `kaist-eds-lab.github.io`를 가리키도록 설정해야 합니다.
