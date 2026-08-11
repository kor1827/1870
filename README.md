                          <!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>화연(禾延) 아포칼립스 : 완전판</title>
  
  <!-- Google Fonts & FontAwesome CDN -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Black+Han+Sans&family=Noto+Sans+KR:wght@300;400;600;800&family=Orbitron:wght@500;700;900&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

  <style>
    /* ==========================================================================
       1. Base & Reset
       ========================================================================== */
    :root {
      --bg-main: #0f1012;
      --bg-card: #16181c;
      --bg-card-hover: #1f2228;
      --text-main: #e0e0e0;
      --text-muted: #9e9e9e;
      --accent-red: #e53935;
      --accent-red-bright: #ff5252;
      --accent-green: #00e676;
      --accent-yellow: #ffb300;
      --border-color: rgba(229, 57, 53, 0.25);
      --border-hover: rgba(255, 82, 82, 0.6);
      --font-heading: 'Black Han Sans', sans-serif;
      --font-tech: 'Orbitron', sans-serif;
      --font-body: 'Noto Sans KR', sans-serif;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      background-color: var(--bg-main);
      color: var(--text-main);
      font-family: var(--font-body);
      line-height: 1.6;
      overflow-x: hidden;
      position: relative;
    }

    /* Scanline Overlay Effect */
    body::before {
      content: " ";
      display: block;
      position: fixed;
      top: 0; left: 0; bottom: 0; right: 0;
      background: linear-gradient(rgba(18, 16, 16, 0) 50%, rgba(0, 0, 0, 0.25) 50%), 
                  linear-gradient(90deg, rgba(255, 0, 0, 0.03), rgba(0, 255, 0, 0.01), rgba(0, 0, 255, 0.03));
      z-index: 999;
      background-size: 100% 3px, 6px 100%;
      pointer-events: none;
      opacity: 0.8;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    /* ==========================================================================
       2. Top Ticker / Header Banner
       ========================================================================== */
    .emergency-bar {
      background: #8b0000;
      color: #fff;
      font-size: 0.85rem;
      font-weight: 600;
      padding: 8px 16px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      border-bottom: 1px solid var(--accent-red);
      position: sticky;
      top: 0;
      z-index: 100;
    }

    .ticker-text {
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .pulsing-dot {
      width: 10px;
      height: 10px;
      background-color: var(--accent-red-bright);
      border-radius: 50%;
      box-shadow: 0 0 10px var(--accent-red-bright);
      animation: pulse 1.2s infinite;
    }

    @keyframes pulse {
      0% { transform: scale(0.95); opacity: 1; }
      50% { transform: scale(1.25); opacity: 0.4; }
      100% { transform: scale(0.95); opacity: 1; }
    }

    .timer-badge {
      font-family: var(--font-tech);
      background: rgba(0,0,0,0.6);
      padding: 4px 10px;
      border-radius: 4px;
      border: 1px solid var(--accent-red-bright);
      color: var(--accent-red-bright);
      letter-spacing: 1px;
    }

    /* ==========================================================================
       3. Hero Section & Glitch Effect
       ========================================================================== */
    .hero-section {
      text-align: center;
      padding: 60px 20px 40px;
      background: radial-gradient(circle at center, rgba(229, 57, 53, 0.15) 0%, rgba(15, 16, 18, 1) 70%);
      border-bottom: 1px solid rgba(255, 255, 255, 0.08);
      position: relative;
    }

    .hero-title {
      font-family: var(--font-heading);
      font-size: clamp(2.2rem, 6vw, 4rem);
      color: #fff;
      text-transform: uppercase;
      position: relative;
      display: inline-block;
      letter-spacing: 2px;
      text-shadow: 0 0 15px rgba(229, 57, 53, 0.6);
    }

    /* Glitch Animation */
    .glitch {
      position: relative;
    }
    .glitch::before, .glitch::after {
      content: attr(data-text);
      position: absolute;
      top: 0; left: 0;
      width: 100%; height: 100%;
      clip: rect(0, 0, 0, 0);
    }
    .glitch::before {
      left: -2px;
      text-shadow: 2px 0 var(--accent-red-bright);
      animation: glitch-anim 2.5s infinite linear alternate-reverse;
    }
    .glitch::after {
      left: 2px;
      text-shadow: -2px 0 #00bcd4;
      animation: glitch-anim2 1.8s infinite linear alternate-reverse;
    }

    @keyframes glitch-anim {
      0% { clip: rect(10px, 9999px, 40px, 0); }
      20% { clip: rect(80px, 9999px, 90px, 0); }
      40% { clip: rect(30px, 9999px, 60px, 0); }
      60% { clip: rect(70px, 9999px, 80px, 0); }
      80% { clip: rect(20px, 9999px, 50px, 0); }
      100% { clip: rect(90px, 9999px, 100px, 0); }
    }
    @keyframes glitch-anim2 {
      0% { clip: rect(70px, 9999px, 90px, 0); }
      25% { clip: rect(10px, 9999px, 30px, 0); }
      50% { clip: rect(50px, 9999px, 70px, 0); }
      75% { clip: rect(20px, 9999px, 40px, 0); }
      100% { clip: rect(60px, 9999px, 80px, 0); }
    }

    .hero-subtitle {
      font-size: 1.1rem;
      color: var(--text-muted);
      margin-top: 12px;
      word-break: keep-all;
    }

    .gov-alert-box {
      max-width: 800px;
      margin: 30px auto 0;
      background: rgba(22, 24, 28, 0.85);
      border-left: 4px solid var(--accent-red);
      border-radius: 4px;
      padding: 16px 20px;
      text-align: left;
      font-size: 0.95rem;
      box-shadow: 0 4px 20px rgba(0,0,0,0.5);
    }

    .gov-alert-header {
      color: var(--accent-red-bright);
      font-weight: 700;
      margin-bottom: 6px;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    /* ==========================================================================
       4. Navigation / Tabs
       ========================================================================== */
    .container {
      max-width: 1100px;
      margin: 0 auto;
      padding: 30px 20px 60px;
    }

    .nav-tabs {
      display: flex;
      justify-content: center;
      gap: 10px;
      flex-wrap: wrap;
      margin-bottom: 35px;
      border-bottom: 2px solid rgba(255, 255, 255, 0.08);
      padding-bottom: 12px;
    }

    .tab-btn {
      background: var(--bg-card);
      border: 1px solid rgba(255, 255, 255, 0.1);
      color: var(--text-muted);
      padding: 12px 24px;
      font-size: 1rem;
      font-weight: 600;
      border-radius: 4px;
      cursor: pointer;
      transition: all 0.3s ease;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .tab-btn:hover {
      background: var(--bg-card-hover);
      color: #fff;
      border-color: var(--border-color);
    }

    .tab-btn.active {
      background: var(--accent-red);
      color: #fff;
      border-color: var(--accent-red-bright);
      box-shadow: 0 0 15px rgba(229, 57, 53, 0.4);
    }

    .tab-content {
      display: none;
      animation: fadeIn 0.4s ease-in-out;
    }

    .tab-content.active {
      display: block;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(10px); }
      to { opacity: 1; transform: translateY(0); }
    }

    /* ==========================================================================
       5. Content Sections (Cards, Grids, Elements)
       ========================================================================== */
    .grid-2 {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 20px;
    }

    .grid-3 {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 20px;
    }

    .card {
      background: var(--bg-card);
      border: 1px solid var(--border-color);
      border-radius: 8px;
      padding: 24px;
      transition: all 0.3s ease;
      position: relative;
      overflow: hidden;
    }

    .card:hover {
      border-color: var(--border-hover);
      transform: translateY(-3px);
      box-shadow: 0 6px 20px rgba(0, 0, 0, 0.6);
    }

    .card-title {
      font-size: 1.3rem;
      color: #fff;
      margin-bottom: 12px;
      display: flex;
      align-items: center;
      gap: 10px;
      font-weight: 700;
    }

    .card-title i {
      color: var(--accent-red-bright);
    }

    .badge {
      font-size: 0.75rem;
      padding: 2px 8px;
      border-radius: 3px;
      font-family: var(--font-tech);
      font-weight: 700;
      text-transform: uppercase;
    }

    .badge-red { background: rgba(229, 57, 53, 0.2); color: var(--accent-red-bright); border: 1px solid var(--accent-red); }
    .badge-yellow { background: rgba(255, 179, 0, 0.2); color: var(--accent-yellow); border: 1px solid var(--accent-yellow); }
    .badge-green { background: rgba(0, 230, 118, 0.2); color: var(--accent-green); border: 1px solid var(--accent-green); }

    /* Map & Subway Table */
    .subway-list {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(110px, 1fr));
      gap: 8px;
      margin-top: 15px;
    }

    .subway-station {
      background: rgba(0,0,0,0.4);
      padding: 10px;
      border-radius: 4px;
      text-align: center;
      font-size: 0.85rem;
      border-left: 3px solid var(--accent-red);
    }

    /* Character Profile Styling */
    .profile-header {
      display: flex;
      gap: 20px;
      align-items: flex-start;
      margin-bottom: 20px;
      flex-wrap: wrap;
    }

    .profile-avatar {
      width: 110px;
      height: 110px;
      background: #252830;
      border: 2px solid var(--accent-red);
      border-radius: 8px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      color: var(--accent-red-bright);
      font-size: 2.5rem;
    }

    .profile-info {
      flex: 1;
    }

    .quote-box {
      background: rgba(229, 57, 53, 0.08);
      border-left: 3px solid var(--accent-red-bright);
      padding: 12px 16px;
      font-style: italic;
      margin: 15px 0;
      color: #fff;
    }

    /* ==========================================================================
       6. Interactive Quiz Section
       ========================================================================== */
    .quiz-container {
      background: var(--bg-card);
      border: 1px solid var(--border-color);
      border-radius: 8px;
      padding: 30px;
      margin-top: 40px;
      text-align: center;
      position: relative;
    }

    .quiz-question {
      font-size: 1.2rem;
      font-weight: 700;
      margin: 20px 0;
      color: #fff;
    }

    .quiz-options {
      display: flex;
      flex-direction: column;
      gap: 12px;
      max-width: 600px;
      margin: 0 auto;
    }

    .option-btn {
      background: rgba(255, 255, 255, 0.05);
      border: 1px solid rgba(255, 255, 255, 0.15);
      color: var(--text-main);
      padding: 14px 20px;
      border-radius: 6px;
      cursor: pointer;
      font-size: 0.95rem;
      text-align: left;
      transition: all 0.2s ease;
    }

    .option-btn:hover {
      background: rgba(229, 57, 53, 0.15);
      border-color: var(--accent-red-bright);
      color: #fff;
    }

    .quiz-result {
      display: none;
      padding: 20px;
      background: rgba(0,0,0,0.5);
      border-radius: 6px;
      margin-top: 20px;
    }

    .score-num {
      font-family: var(--font-tech);
      font-size: 3rem;
      color: var(--accent-red-bright);
      font-weight: 900;
    }

    /* Footer */
    footer {
      text-align: center;
      padding: 30px 20px;
      color: var(--text-muted);
      font-size: 0.85rem;
      border-top: 1px solid rgba(255, 255, 255, 0.08);
      margin-top: 60px;
    }

    /* Responsive Rules */
    @media (max-width: 768px) {
      .hero-section { padding: 40px 15px 30px; }
      .nav-tabs { gap: 6px; }
      .tab-btn { padding: 10px 14px; font-size: 0.9rem; flex: 1 1 40%; justify-content: center; }
      .profile-header { flex-direction: column; align-items: center; text-align: center; }
    }
  </style>
</head>
<body>

  <!-- Top Emergency Alert Bar -->
  <div class="emergency-bar">
    <div class="ticker-text">
      <span class="pulsing-dot"></span>
      <span>[재난방송] 화연시 전역 바이러스 경보 발령중</span>
    </div>
    <div class="timer-badge" id="elapsedTimer">00:00:00</div>
  </div>

  <!-- Hero Header -->
  <header class="hero-section">
    <h1 class="hero-title glitch" data-text="화연(禾延) 아포칼립스">화연(禾延) 아포칼립스</h1>
    <p class="hero-subtitle">발병 72시간째, 통신망 두절 임박. 살아남아라.</p>
    
    <div class="gov-alert-box">
      <div class="gov-alert-header">
        <i class="fa-solid fa-triangle-exclamation"></i>
        <span>정부 긴급 브리핑 요약</span>
      </div>
      <p style="color: #ccc;">"제인바이오 연구시설 감염원 유출 확인. 화연시 봉쇄령 발효 3일차. 수돗물 및 주요 전력망 단계적 마비 진행 중. 수질 contamination 가능성에 주의하십시오."</p>
    </div>
  </header>

  <div class="container">
    <!-- Main Content Navigation Tabs -->
    <nav class="nav-tabs">
      <button class="tab-btn active" onclick="switchTab('overview')">
        <i class="fa-solid fa-earth-americas"></i> 개요 & 배경
      </button>
      <button class="tab-btn" onclick="switchTab('locations')">
        <i class="fa-solid fa-map-location-dot"></i> 주요 시설 & 지도
      </button>

      <button class="tab-btn" onclick="switchTab('infected')">
        <i class="fa-solid fa-biohazard"></i> 감염자 도감
      </button>

      <button class="tab-btn" onclick="switchTab('character')">
        <i class="fa-solid fa-user-ninja"></i> 등장인물 (한서우)
      </button>
    </nav>

    <!-- TAB 1: 개요 & 배경 -->
    <section id="overview" class="tab-content active">
      <div class="grid-2">
        <div class="card">
          <div class="card-title">
            <i class="fa-solid fa-city"></i> 무대: 경기도 화연시
          </div>
          <p style="color: var(--text-muted); margin-bottom: 12px;">인구 35만의 지방 중소도시. 고속도로와 외부 연결 도로망은 군 병력에 의해 완전 차단되었으며, 외부와의 접촉이 끊긴 밀폐 공간입니다.</p>
          <ul style="padding-left: 20px; color: #ccc;">
            <li><strong>지형:</strong> 아파트 단지, 중앙병원, 지하철 8개 역, 연구 시설 밀집</li>
            <li><strong>상태:</strong> 72시간 경과 후 전력/통신망 단계적 붕괴</li>
            <li><strong>환경 변수:</strong> 비와 안개가 감염자의 청각 유인 요소로 작용</li>
          </ul>
        </div>

        <div class="card">
          <div class="card-title">
            <i class="fa-solid fa-vial-virus"></i> 발병 원인: 제인바이오 유출
          </div>
          <p style="color: var(--text-muted); margin-bottom: 12px;">신약 개발 기업 '제인바이오' 비밀 연구소에서 유출된 고위험성 신경계 변종 바이러스.</p>
          <div style="background: rgba(0,0,0,0.3); padding: 12px; border-radius: 4px;">
            <p style="font-size: 0.9rem; color: var(--accent-red-bright);"><strong>[잠복기 & 특징]</strong></p>
            <p style="font-size: 0.85rem; color: #aaa;">잠복기 6~12시간. 초기에 고열과 공격성을 보이며, 뇌 손상이 완료되는 순간 통각이 마비된 생체 병기로 변화합니다. 뇌간 파괴 시에만 완벽히 침묵합니다.</p>
          </div>
        </div>
      </div>
    </section>

    <!-- TAB 2: 주요 시설 & 지도 -->
    <section id="locations" class="tab-content">
      <div class="grid-2" style="margin-bottom: 20px;">
        <div class="card">
          <div class="card-title">
            <i class="fa-solid fa-building-user"></i> 한빛아파트 (주요 거점)
            <span class="badge badge-green">안전지대(부분)</span>
          </div>
          <p style="color: var(--text-muted);">101동~103동으로 구성. 주민들이 입구를 봉쇄하고 4층 이상에 집단 거주 중. 내부 물자 고갈이 임박함.</p>
        </div>

        <div class="card">
          <div class="card-title">
            <i class="fa-solid fa-hospital"></i> 화연중앙병원
            <span class="badge badge-red">위험도 극상</span>
          </div>
          <p style="color: var(--text-muted);">의료 물자의 핵심 보급처이나, 초기 대규모 감염 발생지로 수많은 사냥꾼 및 특수변종 상주.</p>
        </div>

        <div class="card">
          <div class="card-title">
            <i class="fa-solid fa-cart-shopping"></i> 하나로마트
            <span class="badge badge-yellow">생존자 점거</span>
          </div>
          <p style="color: var(--text-muted);">식량/생필품 풍부. 무장한 적대적 생존자 무리가 통제 중이며 진입 시 교전 가능성 높음.</p>
        </div>

        <div class="card">
          <div class="card-title">
            <i class="fa-solid fa-flask"></i> 제인바이오 연구소
            <span class="badge badge-red">Ground Zero</span>
          </div>
          <p style="color: var(--text-muted);">원인 바이러스 데이터 및 백신 연구 샘플이 보관된 장소. 자동 보안 시스템이 활성화되어 있음.</p>
        </div>
      </div>

      <div class="card">
        <div class="card-title">
          <i class="fa-solid fa-train-subway"></i> 화연선 지하철 (8개 주요 역)
        </div>
        <p style="color: var(--text-muted);">지상 이동이 불가능할 때 사용할 수 있는 어둡고 위험한 지하 대피로.</p>
        <div class="subway-list">
          <div class="subway-station">화연역(시발점)</div>
          <div class="subway-station">중앙로역</div>
          <div class="subway-station">한빛역</div>
          <div class="subway-station">시청역</div>
          <div class="subway-station">공단역</div>
          <div class="subway-station">병원입구역</div>
          <div class="subway-station">서부역</div>
          <div class="subway-station">종착역(차단)</div>
        </div>
      </div>
    </section>

    <!-- TAB 3: 감염자 도감 -->
    <section id="infected" class="tab-content">
      <div class="grid-2">
        <div class="card">
          <div class="card-title">
            <i class="fa-solid fa-person-running"></i> 1단계: 뜀박이
            <span class="badge badge-yellow">위험도 보통</span>
          </div>
          <p style="color: var(--text-muted);">감염 초기 상태. 신체 근육이 마비되지 않아 시각과 청각에 반응해 전속력으로 뛰어옵니다. 스태미나 소비가 적어 집요함.</p>
        </div>

        <div class="card">
          <div class="card-title">
            <i class="fa-solid fa-person-walking-with-cane"></i> 2단계: 헤매기
            <span class="badge badge-green">위험도 낮음</span>
          </div>
          <p style="color: var(--text-muted);">발병 후 시간이 지나 시력이 가늘어지고 관절이 굳어 느리게 배회하는 유형. 단, 무리 지으면 위협적.</p>
        </div>

        <div class="card">
          <div class="card-title">
            <i class="fa-solid fa-skull"></i> 3단계: 사냥꾼
            <span class="badge badge-red">위험도 높음</span>
          </div>
          <p style="color: var(--text-muted);">시력을 완전히 잃은 대신 청각과 청각 반사가 극도로 발달. 어둠 속에서 벽이나 천장을 타고 이동하기도 함.</p>
        </div>

        <div class="card">
          <div class="card-title">
            <i class="fa-solid fa-spaghetti-monster-flying"></i> 4단계: 특수 변종
            <span class="badge badge-red">위험도 치명적</span>
          </div>
          <ul style="font-size: 0.9rem; color: #ccc; margin-top: 8px;">
            <li><strong>돌격형 (Charger):</strong> 근육 변이로 도어 및 장벽 파괴 가능</li>
            <li><strong>은신형 (Stalker):</strong> 체색 변화 및 소음 최소화 능력</li>
            <li><strong>콜러 (Caller):</strong> 고주파 비명으로 주변 감염자 집결</li>
          </ul>
        </div>
      </div>
    </section>

    <!-- TAB 4: 등장인물 (한서우) -->
    <section id="character" class="tab-content">
      <div class="card">
        <div class="profile-header">
          <div class="profile-avatar">
            <i class="fa-solid fa-user-gear"></i>
            <span style="font-size: 0.7rem; color: #fff; margin-top: 4px;">HAN SEO-WOO</span>
          </div>
          <div class="profile-info">
            <h2 style="color: #fff; font-size: 1.8rem; font-family: var(--font-heading);">한서우 (26세)</h2>
            <p style="color: var(--accent-red-bright); font-weight: 600;">생일: 4월 1일 (만우절)</p>
            <p style="color: var(--text-muted); font-size: 0.95rem; margin-top: 6px;">능글맞고 유쾌한 평소 모습과, 위기 상황에서 급변하는 차갑고 정교한 면모의 갭모에 매력 소유자.</p>
          </div>
        </div>

        <div class="quote-box">
          "거짓말 같죠? 하필 생일날 세상이 망할 게 뭡니까. 그래도 죽기엔 아까운 날이잖아요?"
        </div>

        <div class="grid-2" style="margin-top: 20px;">
          <div>
            <h4 style="color: #fff; margin-bottom: 8px;"><i class="fa-solid fa-screwdriver-wrench"></i> 특기 및 능률</h4>
            <p style="font-size: 0.9rem; color: var(--text-muted);">손재주가 비상하여 폐품과 무전기, 생활 기구를 조합해 부비트랩이나 improvised 무기를 조립하는 데 능함. 기계 수리 및 사격 감각 우수.</p>
          </div>
          <div>
            <h4 style="color: #fff; margin-bottom: 8px;"><i class="fa-solid fa-masks-theater"></i> 성격 포인트 (갭모에)</h4>
            <p style="font-size: 0.9rem; color: var(--text-muted);">농담을 던지며 긴장을 풀어주지만, 감염체나 적대 생존자와 대치 시 장난기가 순식간에 사라지고 계산적이고 위협적인 행동 패턴을 보임.</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Interactive Survival Quiz Section -->
    <div class="quiz-container">
      <h3 style="font-family: var(--font-heading); font-size: 1.6rem; color: #fff;">
        <i class="fa-solid fa-skull-crossbones" style="color: var(--accent-red-bright);"></i> 화연시 생존 가능성 테스트
      </h3>
      <p style="color: var(--text-muted); font-size: 0.9rem; margin-top: 4px;">당신의 선택이 생존율을 결정합니다.</p>

      <div id="quizBox">
        <div class="quiz-question" id="quizQuestion">1. 밤중에 복도에서 이상한 소음이 들릴 때 당신의 행동은?</div>
        <div class="quiz-options" id="quizOptions">
          <button class="option-btn" onclick="answerQuiz(10)">A. 숨을 죽이고 무기를 든 채 문 앞을 경계한다.</button>
          <button class="option-btn" onclick="answerQuiz(0)">B. 무슨 소리인지 확인하러 바로 문을 연다.</button>
          <button class="option-btn" onclick="answerQuiz(5)">C. 소리 나는 반대쪽 창문으로 탈출 시도를 한다.</button>
        </div>
      </div>

      <div class="quiz-result" id="quizResult">
        <h4>당신의 예상 생존율</h4>
        <div class="score-num" id="survivalScore">85%</div>
        <p id="survivalText" style="color: var(--text-muted); margin-top: 10px;">냉정한 판단력을 갖추셨군요. 화연시에서 살아남을 자격이 있습니다.</p>
        <button class="tab-btn" onclick="resetQuiz()" style="margin: 15px auto 0;">다시 테스트하기</button>
      </div>
    </div>
  </div>

  <!-- Footer -->
  <footer>
    <p>© 2026 HWAYEON APOCALYPSE RP / ALL RIGHTS RESERVED.</p>
    <p style="margin-top: 5px; color: #666;">본 페이지는 '화연 아포칼립스' 텍스트 RP 세계관 소개용 프론트엔드 데모입니다.</p>
  </footer>

  <!-- Inline JavaScript -->
  <script>
    // 1. Timer Simulation (Elapsed Time from outbreak)
    let seconds = 259200; // 72 hours in seconds
    const timerElem = document.getElementById('elapsedTimer');

    function updateTimer() {
      seconds++;
      const hrs = String(Math.floor(seconds / 3600)).padStart(2, '0');
      const mins = String(Math.floor((seconds % 3600) / 60)).padStart(2, '0');
      const secs = String(seconds % 60).padStart(2, '0');
      timerElem.textContent = `${hrs}:${mins}:${secs}`;
    }
    setInterval(updateTimer, 1000);

    // 2. Tab Switcher
    function switchTab(tabId) {
      document.querySelectorAll('.tab-content').forEach(content => {
        content.classList.remove('active');
      });
      document.querySelectorAll('.tab-btn').forEach(btn => {
        btn.classList.remove('active');
      });

      document.getElementById(tabId).classList.add('active');
      event.currentTarget.classList.add('active');
    }

    // 3. Mini Quiz System
    const questions = [
      {
        q: "1. 밤중에 복도에서 이상한 소음이 들릴 때 당신의 행동은?",
        options: [
          { text: "A. 숨을 죽이고 무기를 든 채 문 앞을 경계한다.", score: 35 },
          { text: "B. 무슨 소리인지 확인하러 바로 문을 연다.", score: 0 },
          { text: "C. 소리 나는 반대쪽 창문으로 탈출 시도를 한다.", score: 15 }
        ]
      },
      {
        q: "2. 식량이 고갈된 상태에서 하나로마트 수색 제안을 받았다면?",
        options: [
          { text: "A. 서우와 함께 우회로를 탐색하며 조심스럽게 접근한다.", score: 35 },
          { text: "B. 식량이 급하니 마트 전면 정문으로 돌진한다.", score: 5 },
          { text: "C. 위험하니 아파트 안에서 남의 물자를 빼앗는다.", score: 10 }
        ]
      },
      {
        q: "3. 3단계 감염자(사냥꾼)와 어두운 지하철역에서 조우했다면?",
        options: [
          { text: "A. 소리를 내지 않고 소음 발생원을 딴 곳으로 던진 후 이탈한다.", score: 30 },
          { text: "B. 손전등을 켜고 고함을 지르며 기선제압을 시도한다.", score: 0 },
          { text: "C. 정면에서 가진 무기로 타격을 시도한다.", score: 10 }
        ]
      }
    ];

    let currentQ = 0;
    let totalScore = 0;

    function answerQuiz(score) {
      totalScore += score;
      currentQ++;

      if (currentQ < questions.length) {
        showQuestion();
      } else {
        showResult();
      }
    }

    function showQuestion() {
      const qData = questions[currentQ];
      document.getElementById('quizQuestion').textContent = qData.q;
      const optsContainer = document.getElementById('quizOptions');
      optsContainer.innerHTML = '';

      qData.options.forEach(opt => {
        const btn = document.createElement('button');
        btn.className = 'option-btn';
        btn.textContent = opt.text;
        btn.onclick = () => answerQuiz(opt.score);
        optsContainer.appendChild(btn);
      });
    }

    function showResult() {
      document.getElementById('quizBox').style.display = 'none';
      const resultBox = document.getElementById('quizResult');
      resultBox.style.display = 'block';

      const scoreElem = document.getElementById('survivalScore');
      const textElem = document.getElementById('survivalText');

      scoreElem.textContent = `${totalScore}%`;

      if (totalScore >= 80) {
        textElem.textContent = "침착함과 대담함을 겸비하셨군요. 한서우와 함께 화연시를 탈출할 유력한 생존자입니다.";
      } else if (totalScore >= 40) {
        textElem.textContent = "기본적인 생존 본능은 있으나, 치명적인 순간 한 번의 실수가 목숨을 앗아갈 수 있습니다.";
      } else {
        textElem.textContent = "발병 24시간 이내에 감염체로 변할 가능성이 높습니다. 신중한 판단이 필요합니다.";
      }
    }

    function resetQuiz() {
      currentQ = 0;
      totalScore = 0;
      document.getElementById('quizBox').style.display = 'block';
      document.getElementById('quizResult').style.display = 'none';
      showQuestion();
    }
  </script>
</body>
</html>
