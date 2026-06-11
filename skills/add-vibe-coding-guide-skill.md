# 🌿 신규 바이브코딩 가이드 생성 및 홈페이지 반영 절차 (스킬 매뉴얼)

이 문서는 '초록덕후의 교실 도구함' 프로젝트에 새로운 바이브코딩 실습 가이드를 제작하여 추가하고, 메인 홈페이지(`index.html`)의 잠금을 풀어 정식으로 릴리즈(배포)할 때 AI 코딩 에이전트가 반드시 수행해야 하는 기술적 절차와 체크리스트(스킬 프로토콜)를 정의합니다.

---

## 🚀 1. 신규 가이드 HTML 작성 및 레이아웃 규격
새로운 가이드는 `guides/vibe-coding-[앱이름].html` 경로에 생성하며, 다음 레이아웃 및 톤앤매너 규격을 엄격하게 준수합니다.

### 🎨 디자인 시스템 준수
- 기존의 초록 시그니처 CSS 변수를 그대로 활용합니다.
  ```css
  --green: #15803d;
  --green-deep: #14532d;
  --green-bright: #16a34a;
  --green-mist: #f0fdf4;
  --warm: #fafaf7;
  --radius-xl: 30px;
  ```
- 가이드 전반의 가독성을 위해 **NanumSquareRound** 및 **Pretendard** 폰트 패밀리를 상속받아 연출합니다.

### 🎚️ 4단계 슬라이더 시스템 이식
- 수강생이 버튼을 눌러 다음 단계로 진행할 수 있는 **Javascript 제어형 슬라이더 구조**를 필수로 탑재합니다.
- 상단 프로그레스 바 (`progressBar`)와 단계 표시기(`stepNumber`, `stepTotal`), 하단 내비게이션 버튼(`btnPrev`, `btnNext`)의 동적 상태 이벤트를 상속 구현합니다.

### 📸 필수 이미지 자산 규격
단계별로 수강생의 혼선을 막기 위한 실물 스크린샷을 매핑하며, 모든 이미지는 `assets/images/` 하위에 배치합니다.
1. **1단계 (준비)**: 기본 제공할 앱의 초기 미리보기 화면 (`guide-step1-preview.png`)
2. **2단계 (리믹스)**:
   - ① 타사 개발자 경고창 (`guide-step2-continue.png`)
   - ② 우측 상단 Remix 버튼 (`guide-step2-remix.png`)
   - ③ 팝업창 Apply 버튼 (`guide-step2-apply.png`)
3. **3단계 (바이브코딩)**: 한글 자연어로 채팅을 입력하는 AI Studio 화면 (`guide-step3-chat.png`)
4. **4단계 (배포 & 다운로드)**:
   - ① Publish 버튼 클릭 (`guide-step4-publish.png`)
   - ② Get started 안내창 (`guide-step4-getstarted.png`)
   - ③ 기본 프로젝트 및 Set up billing (`guide-step4-project.png`)
   - ④ 결제 계정 정보 입력 및 카드 등록 (`guide-step4-billing.png`)
   - ⑤ 배포 완료 및 Visit 버튼 (`guide-step4-complete.png`)
   - ⑥ 크롬 주소창 우측 앱 설치/다운로드 아이콘 (`guide-step4-install.png`)

---

## 🔒 2. 메인 페이지(index.html) 반영 및 잠금 해제 규격
가이드가 완성되면 메인 홈페이지(`index.html`)에서 수강생이 접근할 수 있도록 활성화합니다.

1. **작업중 비활성화 속성 해제**:
   - 수정 대상 카드 엘리먼트에서 `coming-soon` 클래스를 삭제합니다.
   - `<span class="coming-label">🔧 작업중</span>` 태그와 `coming-soon`에 의한 불투명도(`opacity: .55`) 레이아웃 요소를 완전히 제거합니다.
2. **링크 연결 및 featured 속성 부여**:
   - `href="#"`로 되어 있던 더미 링크를 `href="guides/vibe-coding-[앱이름].html"` 실 가이드 경로로 수정합니다.
   - 대표 강좌인 경우 `card` 클래스 옆에 `featured` 클래스를 추가하여 그라디언트 배경 효과로 부각시킵니다.

---

## 💳 3. 결제(Billing) 안심 가이드 의무 문구
초보 교사들의 결제 거부감을 예방하기 위해, 4단계 결제 카드 정보 입력 단계 설명 하단에 반드시 아래 안심 가이드를 수록해야 합니다.

> 💳 **빌링(결제) 설정 관련 안심 가이드**
> - 결제 수단 등록은 **최초 1회만 연동해 두면** 향후 다른 AI 앱 배포 시 번거로운 과정 없이 바로 사용하실 수 있습니다.
> - 개인 실무용(프로토타입) 사용 범위 내에서는 구글 클라우드가 제공하는 기본 무료 요금 한도(Free Tier) 내에 머물기 때문에 **실질적으로 요금이 절대 발생하지 않으므로 안심하고 등록을 진행하세요.**

---

## 💻 4. 크롬 우회 바로가기 생성(PWA) 지원 문구
PWA 감지가 안 될 경우를 대비해, 4단계 다운로드 설명 하단에 브라우저 기본 우회법을 반드시 병기합니다.

> 💡 **앱 설치 아이콘(모니터 화살표)이 나타나지 않는 경우**
> 크롬 브라우저 우측 상단 **[점 3개 메뉴(⋮)] -> [저장 및 공유] -> [바로가기 만들기]**를 선택하신 뒤, **'창으로 열기'** 옵션을 반드시 체크하고 만들기를 누르면 동일하게 바탕화면에 앱처럼 설치됩니다.

---

## 📦 5. 버전 관리 및 릴리즈 프로세스
모든 파일의 생성이 끝나면 다음 Git 커맨드를 순차적으로 제안하여 릴리즈를 종결합니다.

```powershell
# 1. 변경된 파일 스테이징
git add index.html guides/vibe-coding-[앱이름].html assets/images/guide-*

# 2. 규격화된 커밋 메시지 작성
git commit -m "feat: unlock and publish [앱이름] vibe coding guide"

# 3. 원격 저장소 푸시 및 자동 배포 유도
git push origin main
```
