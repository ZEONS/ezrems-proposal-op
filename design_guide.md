# ezREMS 제안 인터랙티브 웹 디자인 시스템 가이드 (Design System Guide)

> **일관성 있는 엔터프라이즈 프롭테크 UI/UX를 위한 종합 디자인 지침**  
> 공식 폰트: **Paperlogy** | 테마: **Dark Slate & Glassmorphism** | 프레임워크: **Tailwind CSS**

---

## 🎨 1. 디자인 철학 및 비주얼 원칙 (Design Principles)

1. **Simple, Smart & Solve (명료성 & 신뢰성)**:
   - 방대한 부동산·금융·세무 데이터를 한눈에 파악할 수 있도록 고대비(High Contrast) 다크 테마 기반 정보 구조화.
2. **Enterprise PropTech & FinTech Fusion**:
   - 차분하고 깊이 있는 Slate-950 배경 위에 네온 Cyan 및 Royal Blue 포인트를 활용하여 최첨단 클라우드 및 핀테크 이미지 극대화.
3. **Seamless State Persistence (무결점 상호작용)**:
   - 슬라이드 PT 모드 ↔ 스크롤 문서 모드, 6개 국어(KO, EN, JA, ZH, VI, TH) 전환 시 사용자의 맥락(Context)을 100% 보존.

---

## 🔤 2. 타이포그래피 시스템 (Typography)

### 2.1 공식 폰트: Paperlogy (페이퍼로지)
- **제작사**: 프로젝트 눈누 / 노티드
- **서체 특징**: 기하학적 정밀함과 부드러운 곡률이 조화를 이루는 고가독성 산세리프(Sans-serif) 서체.
- **웹 폰트 선언 (Web Font CDN)**:
  ```css
  @font-face {
    font-family: 'Paperlogy';
    src: url('https://fastly.jsdelivr.net/gh/projectnoonnu/2408-3@1.0/Paperlogy-3Light.woff2') format('woff2');
    font-weight: 300;
  }
  @font-face {
    font-family: 'Paperlogy';
    src: url('https://fastly.jsdelivr.net/gh/projectnoonnu/2408-3@1.0/Paperlogy-4Regular.woff2') format('woff2');
    font-weight: 400;
  }
  @font-face {
    font-family: 'Paperlogy';
    src: url('https://fastly.jsdelivr.net/gh/projectnoonnu/2408-3@1.0/Paperlogy-5Medium.woff2') format('woff2');
    font-weight: 500;
  }
  @font-face {
    font-family: 'Paperlogy';
    src: url('https://fastly.jsdelivr.net/gh/projectnoonnu/2408-3@1.0/Paperlogy-6SemiBold.woff2') format('woff2');
    font-weight: 600;
  }
  @font-face {
    font-family: 'Paperlogy';
    src: url('https://fastly.jsdelivr.net/gh/projectnoonnu/2408-3@1.0/Paperlogy-7Bold.woff2') format('woff2');
    font-weight: 700;
  }
  @font-face {
    font-family: 'Paperlogy';
    src: url('https://fastly.jsdelivr.net/gh/projectnoonnu/2408-3@1.0/Paperlogy-8ExtraBold.woff2') format('woff2');
    font-weight: 800;
  }
  @font-face {
    font-family: 'Paperlogy';
    src: url('https://fastly.jsdelivr.net/gh/projectnoonnu/2408-3@1.0/Paperlogy-9Black.woff2') format('woff2');
    font-weight: 900;
  }
  ```

### 2.2 계층 구조 (Type Hierarchy)
| 계층(Role) | 크기(Desktop) | 굵기(Weight) | 행간(Line-height) | 클래스 예시 | 적용 대상 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Hero Title** | 48px ~ 60px | Black (900) | tight (1.1) | `text-4xl sm:text-6xl font-black` | 표지 메인 카피 |
| **Slide Title** | 24px ~ 30px | ExtraBold (800) | tight (1.2) | `text-2xl sm:text-3xl font-extrabold` | 각 장표 메인 헤더 |
| **Section Title** | 18px ~ 20px | Bold (700) | snug (1.3) | `text-lg sm:text-xl font-bold` | 섹션 소제목, 모달 타이틀 |
| **Card Title** | 14px ~ 15px | Bold (700) | normal (1.4) | `text-sm font-bold text-white` | 10대 자산 카드, 기능 블록 |
| **Body (본문)** | 12px ~ 13px | Medium (500) | relaxed (1.6) | `text-xs text-slate-300 leading-relaxed` | 일반 설명문 및 리스트 |
| **Caption & Badge**| 10px ~ 11px | Bold (700) | none (1.0) | `text-[10px] sm:text-[11px] font-bold` | 태그 뱃지, 챕터 인디케이터 |

---

## 🎨 3. 컬러 팔레트 시스템 (Color System)

### 3.1 Background & Surface Colors (배경 및 서피스)
- **Canvas Dark (기본 캔버스)**: `#030712` (`slate-950`)
- **Stage & Surface (슬라이드 뷰포트)**: `#0f172a` (`slate-900`) with 90% opacity
- **Card Background (카드 배경)**: `#020617` (`slate-950/70`)
- **Border Default (기본 테두리)**: `#1e293b` (`slate-800/80`)
- **Divider Highlight (포커스 테두리)**: `#334155` (`slate-700/80`)

### 3.2 Accent & Semantic Colors (기능 및 포인트 컬러)
| 컬러명 | 대표 코드 (Hex) | Tailwind Class | 의미 및 주요 용도 |
| :--- | :--- | :--- | :--- |
| **Primary Blue** | `#2563eb` / `#3b82f6` | `bg-blue-600`, `text-blue-400` | 브랜드 메인 컬러, 활성 버튼, 주요 지표 |
| **Cyan Tech** | `#06b6d4` / `#22d3ee` | `text-cyan-400`, `border-cyan-500` | 핀테크/프롭테크 테크놀로지, 데이터 지표, 링크 |
| **Emerald Core** | `#059669` / `#10b981` | `text-emerald-400`, `bg-emerald-950`| 10대 자산 코어 엔진, 성과 개선(미납률 감소 등) |
| **Amber Accent** | `#d97706` / `#f59e0b` | `text-amber-400`, `border-amber-500`| 신규 비즈니스 발굴, 주의/강조 지표, 골드 포인트 |
| **Rose Alert** | `#e11d48` / `#f43f5e` | `text-rose-400`, `bg-rose-950` | 시장 한계, 연체 위험 경고, 문제점 강조 |
| **Purple Insight**| `#9333ea` / `#a855f7` | `text-purple-400`, `bg-purple-950` | 추모/안치 시설, 솔루션 심화 기능, 아키텍처 |

### 3.3 Text Gradients (특수 그라디언트)
- **Brand Glow Gradient**:
  ```css
  .gradient-text {
    background: linear-gradient(135deg, #60a5fa 0%, #38bdf8 50%, #818cf8 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }
  ```

---

## 🧩 4. 주요 컴포넌트 명세 (Component Specs)

### 4.1 슬라이드 캔버스 (Presentation Canvas)
- **가로세로 비율**: 16:9 (`aspect-ratio: 16 / 9`) 고정
- **최대 너비**: 1440px
- **모서리 곡률**: `rounded-2xl` (16px)
- **그림자 효과**: `shadow-2xl shadow-blue-950/40`
- **배경**: `bg-slate-900/90` backdrop-blur

### 4.2 내비게이션 바 & 언어 선택 콤보박스 (GNB & Combobox Selector)
- **위치**: GNB 우측 액션 바 최우선 순위
- **디자인 목적**: 가로형 버튼 그룹 대신 컴팩트한 드롭다운 콤보박스를 채택하여, 6개 언어 체계 확장 시에도 헤더 레이아웃이 무너지지 않고 깔끔한 폭(약 130px)을 유지.
- **컴포넌트 구조**:
  ```html
  <!-- Language Selector Combobox (6 Languages) -->
  <div id="lang-selector-group" class="relative flex items-center bg-slate-900 border border-slate-700/80 rounded-xl px-2.5 py-1.5 shadow-inner hover:border-slate-600 transition mr-1">
    <i data-lucide="globe" class="w-3.5 h-3.5 text-cyan-400 mr-1.5 flex-shrink-0"></i>
    <select id="lang-select-combo" onchange="changeLanguage(this.value)" class="bg-transparent text-xs font-bold text-slate-200 focus:outline-none cursor-pointer pr-4 appearance-none">
      <option value="index.html" class="bg-slate-900 text-white" selected>🇰🇷 KO (한국어)</option>
      <option value="index_en.html" class="bg-slate-900 text-white">🇺🇸 EN (English)</option>
      <option value="index_ja.html" class="bg-slate-900 text-white">🇯🇵 JA (日本語)</option>
      <option value="index_zh.html" class="bg-slate-900 text-white">🇨🇳 ZH (中文)</option>
      <option value="index_vi.html" class="bg-slate-900 text-white">🇻🇳 VI (Tiếng Việt)</option>
      <option value="index_th.html" class="bg-slate-900 text-white">🇹🇭 TH (ภาษาไทย)</option>
    </select>
    <i data-lucide="chevron-down" class="w-3 h-3 text-slate-400 pointer-events-none absolute right-2"></i>
  </div>
  ```

### 4.3 아이콘 뱃지 (Icon Badges)
- **크기**: 40px × 40px (`w-10 h-10`)
- **형태**: `rounded-xl` (12px)
- **내부 정렬**: Flexbox Center (`flex items-center justify-center`)
- **스타일**: 반투명 틴트 배경 + 30% 보더 + 네온 컬러 아이콘

### 4.4 10대 유·무형 자산 그리드 카드 (Asset Grid Cards)
- **그리드 레이아웃**: 데스크톱 `grid-cols-5` (5열 × 2행), 모바일 `grid-cols-2`
- **상호작용 효과**: Hover 시 Border 컬러 활성화, Box Shadow 확장, 아이콘 Scale(1.1) 확대
- **하단 브랜딩 바**: Core Platform 코어 단일 엔진 안내 띠바 배치

### 4.5 50+ 고객사 칩 & 랜드마크 포트폴리오 컴포넌트 (Chapter 5 Customers & Landmarks)
- **좌우 분할 레이아웃**: 좌측 5열 (4대 자산군 랜드마크) + 우측 7열 (50+ 엔터프라이즈 고객사 칩)
- **자산군 컬러 코딩**:
  - 리테일 (Retail): Amber Gold (`border-amber-500/30`, `text-amber-300`)
  - 프라임 오피스 (Prime Office): Cyber Blue (`border-blue-500/30`, `text-blue-300`)
  - 임대주택 / 코리빙 (Residential): Emerald Green (`border-emerald-500/30`, `text-emerald-300`)
  - 시니어 레지던스 (Senior Living): Violet Purple (`border-purple-500/30`, `text-purple-300`)
- **고객사 칩 그리드**:
  - `bg-slate-900/80` 배경 위에 은은한 테두리, Hover 시 `border-blue-500/50` 및 텍스트 하이라이트
  - 스크롤 가능 영역(`max-h-[260px] overflow-y-auto`)으로 50+ 고객사 로고/명칭 완벽 수용

---

## 📱 5. 반응형 브레이크포인트 (Responsive Design)

- **Mobile (< 640px)**:
  - 1열 스택 레이아웃, 모달 패딩 축소, 콤보박스 자동 폭 조정
- **Tablet (640px ~ 1024px)**:
  - 2열/3열 그리드 배치, 모드 전환 바 축소형 적용
- **Desktop (1024px+)**:
  - 16:9 슬라이드 캔버스 완벽 유지, 5열 유니버스 카드 풀 렌더링, GNB 풀 버튼 노출

---

## ♿ 6. 접근성 및 디스플레이 규칙 (A11y Rules)

1. **디바이더 격리 규칙**:
   - 슬라이드 PT 모드에서는 장표의 완성도를 위해 `border-b` 구분선 유지.
   - 스크롤 웹 문서 모드에서는 하단 컨텐츠 박스와의 시각적 중복 간섭을 방지하기 위해 `#scroll-content .slide-header { border-bottom: none !important; }` 자동 적용.
2. **단축키 가이드 인지성**:
   - 모든 주요 버튼(목차, 전체화면, 갤러리)의 툴팁(`title`)에 단축키(`F`, `M`, `G`, 화살표) 표기.
