[index_1.html](https://github.com/user-attachments/files/32542461/index_1.html)
<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
<title>꿈비 합포 가이드</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@400;500;700;900&display=swap" rel="stylesheet">
<style>
:root{
  --bg:#eaf4f4; --card:#fff; --ink:#132628; --muted:#56696b; --line:#d3e3e4;
  --brand:#2d7c81; --brand-d:#1d5559; --brand-l:#e0f1f2;
  --amber:#8a4b00; --amber-bg:#fff3d1; --amber-line:#f2c863;
  --ok:#116b35; --ok-bg:#d9f7e3; --red:#b42318; --red-bg:#fde8e6;
  --bag:#1d4ed8; --bag-bg:#e4ecff;
  --r:16px;
}
*{box-sizing:border-box;-webkit-tap-highlight-color:transparent}
html,body{margin:0}
body{font-family:'Noto Sans KR',system-ui,-apple-system,sans-serif;background:var(--bg);color:var(--ink);font-size:16px;line-height:1.45;min-height:100vh;display:flex;flex-direction:column}
button{font:inherit;color:inherit;cursor:pointer;border:0;background:none}
input,select,textarea{font:inherit;color:inherit}
.hidden{display:none!important}
.wrap{width:100%;max-width:520px;margin:0 auto;padding:0 16px}

/* 헤더 */
header{background:var(--brand-d);color:#fff;position:sticky;top:0;z-index:30}
header .wrap{display:flex;align-items:center;justify-content:space-between;height:56px}
.logo{display:flex;align-items:center;gap:10px;font-weight:900;font-size:17px;letter-spacing:-.2px}
.logo small{display:block;font-weight:500;font-size:11px;opacity:.75;letter-spacing:0}
.chip{font-size:12px;font-weight:700;padding:4px 10px;border-radius:999px;background:rgba(255,255,255,.15)}
.chip.admin{background:#ffd666;color:#5c3900}

main{flex:1;padding:16px 0 24px}
.stack>*+*{margin-top:12px}
.card{background:var(--card);border-radius:var(--r);border:1px solid var(--line);padding:16px}

/* 로비 */
.search{position:relative}
.search input{width:100%;height:56px;border-radius:14px;border:2px solid var(--line);background:#fff;padding:0 16px 0 48px;font-size:17px;font-weight:500;outline:none}
.search input:focus{border-color:var(--brand)}
.search svg{position:absolute;left:16px;top:50%;transform:translateY(-50%);width:22px;height:22px;color:var(--muted)}
.hint{font-size:13px;color:var(--muted);margin:6px 4px 0}
.group{background:#fff;border-radius:var(--r);border:1px solid var(--line);overflow:hidden}
.group-h{display:flex;align-items:center;gap:10px;width:100%;padding:16px;text-align:left;font-weight:700;font-size:17px}
.group-h .cnt{flex:none;font-size:13px;font-weight:700;color:var(--brand-d);background:var(--brand-l);padding:2px 9px;border-radius:999px}
.group-h .chev{margin-left:auto;width:20px;height:20px;transition:transform .2s;color:var(--muted)}
.group.open .chev{transform:rotate(180deg)}
.group-h>span:first-child{min-width:0}
.group-h .del{white-space:nowrap;flex:none;font-size:13px;color:var(--red);padding:4px 8px;border-radius:8px;background:var(--red-bg)}
.group-body{border-top:1px solid var(--line)}
.prod{display:flex;align-items:center;gap:12px;width:100%;padding:14px 16px;text-align:left;border-bottom:1px solid var(--line);background:#fff}
.prod:last-child{border-bottom:0}
.prod:active{background:var(--brand-l)}
.prod .zone{flex:none;min-width:52px;height:52px;border-radius:12px;background:var(--brand-l);color:var(--brand-d);display:flex;flex-direction:column;align-items:center;justify-content:center;font-weight:900;font-size:18px;line-height:1.1;padding:0 6px}
.prod .zone small{font-size:10px;font-weight:700;opacity:.7}
.prod .info{flex:1;min-width:0}
.prod .nm{font-weight:700;font-size:15.5px;line-height:1.35}
.prod .meta{display:flex;flex-wrap:wrap;gap:6px;margin-top:5px;font-size:13px;color:var(--muted)}
.tag{display:inline-block;font-size:12.5px;font-weight:700;padding:2px 8px;border-radius:7px;background:#f1f5f5;color:var(--ink)}
.tag.box{background:var(--amber-bg);color:var(--amber)}
.tag.ab{background:var(--ink);color:#fff}
.prod .arrow{flex:none;width:20px;height:20px;color:var(--muted)}
.prod input[type=checkbox]{width:24px;height:24px;accent-color:var(--brand);flex:none}
.empty{text-align:center;padding:40px 16px;color:var(--muted);font-weight:500}
.sec-label{font-size:13px;font-weight:700;color:var(--muted);margin:18px 4px 8px}

/* 관리자 박스 */
.admin-bar{background:#fffbea;border:1px dashed #e0b43a;border-radius:var(--r);padding:14px}
.admin-bar h3{margin:0 0 4px;font-size:15px}
.admin-bar p{margin:0 0 10px;font-size:13px;color:#6b5200}
.btn-row{display:flex;gap:8px;flex-wrap:wrap}
.btn{display:inline-flex;align-items:center;justify-content:center;gap:6px;min-height:48px;padding:0 16px;border-radius:12px;font-weight:700;font-size:15px;background:#fff;border:1.5px solid var(--line)}
.btn.primary{background:var(--brand);border-color:var(--brand);color:#fff}
.btn.warn{background:var(--red-bg);border-color:#f6c3bd;color:var(--red)}
.btn.amber{background:#ffd666;border-color:#ffd666;color:#4d3000}
.btn.grow{flex:1}
.btn.sm{min-height:40px;font-size:14px;padding:0 12px}

/* 상세 */
.topbar{display:flex;align-items:center;justify-content:space-between;gap:8px}
.back{display:inline-flex;align-items:center;gap:4px;min-height:48px;padding:0 14px 0 8px;border-radius:12px;background:#fff;border:1.5px solid var(--line);font-weight:700;font-size:15px}
.back svg{width:20px;height:20px}
.hero{display:flex;gap:14px;align-items:stretch}
.hero .rack{flex:none;width:84px;border-radius:14px;background:var(--ink);color:#fff;display:flex;flex-direction:column;align-items:center;justify-content:center;padding:8px 4px;text-align:center}
.hero .rack small{font-size:12px;font-weight:700;opacity:.7}
.hero .rack b{font-size:28px;font-weight:900;line-height:1.1;word-break:break-all}
.hero h1{font-size:19px;line-height:1.35;margin:0;font-weight:900;letter-spacing:-.3px}
.hero .code{margin-top:6px;font-size:13px;color:var(--muted);font-family:ui-monospace,Menlo,monospace}

.split{background:var(--red-bg);border:2px solid #f3a79e;border-radius:var(--r);padding:14px 16px}
.split b{display:block;font-size:17px;color:var(--red)}
.split p{margin:4px 0 10px;font-size:15px}
.split .btn{width:100%;background:#fff;border-color:#f3a79e;color:var(--red)}

.step-h{display:flex;align-items:center;gap:10px;font-weight:900;font-size:16px;margin-bottom:12px}
.step-n{flex:none;width:28px;height:28px;border-radius:50%;background:var(--brand);color:#fff;display:flex;align-items:center;justify-content:center;font-size:15px}
.boxcard{background:var(--brand-d);color:#fff;border:0}
.boxcard .step-n{background:#fff;color:var(--brand-d)}
.boxname{display:flex;align-items:center;gap:14px;background:rgba(255,255,255,.12);border-radius:14px;padding:16px}
.boxname .ico{font-size:40px;line-height:1}
.boxname b{font-size:30px;font-weight:900;line-height:1.15;letter-spacing:-.5px}
.boxname small{display:block;font-size:13px;opacity:.8;font-weight:500}
.qty{display:flex;align-items:center;justify-content:space-between;gap:12px;margin-bottom:12px}
.qty .lbl{font-size:15px;font-weight:700}
.qty .lbl small{display:block;font-weight:500;font-size:12.5px;opacity:.8}
.stepper{display:flex;align-items:center;gap:6px}
.stepper button{width:56px;height:56px;border-radius:14px;background:#fff;color:var(--brand-d);font-size:30px;font-weight:900;line-height:1}
.stepper button:disabled{opacity:.35}
.stepper output{min-width:56px;text-align:center;font-size:32px;font-weight:900}

.caution{background:var(--amber-bg);border:1.5px solid var(--amber-line);border-radius:var(--r);padding:14px 16px}
.caution h2{margin:0 0 6px;font-size:16px;color:var(--amber);display:flex;gap:6px;align-items:center}
.caution ul{margin:0;padding-left:20px}
.caution li{font-size:15.5px;font-weight:500;margin:3px 0}
.caution li.star{font-weight:900;color:var(--red);list-style:none;margin-left:-20px}

.progress{display:flex;align-items:center;gap:10px;margin-bottom:6px}
.progress .bar{flex:1;height:10px;border-radius:99px;background:#e6eeee;overflow:hidden}
.progress .bar i{display:block;height:100%;background:var(--brand);border-radius:99px;transition:width .2s}
.progress .num{font-weight:900;font-size:16px;min-width:56px;text-align:right}
.sub-h{display:flex;align-items:center;gap:8px;font-size:14px;font-weight:900;margin:16px 0 8px;padding:6px 10px;border-radius:10px;background:#f1f5f5}
.sub-h.bag{background:var(--bag-bg);color:var(--bag)}
.sub-h small{font-weight:500;opacity:.85}
.item{display:flex;align-items:center;gap:12px;width:100%;min-height:60px;padding:8px 12px;border-radius:14px;border:2px solid var(--line);background:#fff;text-align:left;margin-top:8px;transition:background .15s,border-color .15s}
.item .ck{flex:none;width:30px;height:30px;border-radius:50%;border:2.5px solid #9fb5b7;display:flex;align-items:center;justify-content:center}
.item .ck svg{width:18px;height:18px;color:#fff;opacity:0}
.item .nm{flex:1;font-size:17px;font-weight:700;line-height:1.3}
.item .q{flex:none;font-size:26px;font-weight:900;letter-spacing:-.5px}
.item .q small{font-size:14px;font-weight:700;margin-left:1px}
.item .q.check{font-size:14px;color:var(--amber);background:var(--amber-bg);padding:4px 8px;border-radius:8px}
.item.on{background:var(--ok-bg);border-color:#8bd9a8}
.item.on .ck{background:var(--ok);border-color:var(--ok)}
.item.on .ck svg{opacity:1}
.item.on .nm,.item.on .q{color:var(--ok);text-decoration:line-through;text-decoration-thickness:2px}
.done{margin-top:14px;background:var(--ok);color:#fff;border-radius:14px;padding:16px;text-align:center;font-weight:900;font-size:18px}
.done small{display:block;font-weight:500;font-size:14px;opacity:.9}
.reset{margin-top:10px;width:100%}
.photo img{width:100%;border-radius:12px;display:block}

/* QR */
.qr{display:flex;gap:14px;align-items:center}
.qr img{width:120px;height:120px;border-radius:8px;border:1px solid var(--line);flex:none;background:#fff}
.qr .link{font-size:12.5px;color:var(--muted);word-break:break-all;font-family:ui-monospace,Menlo,monospace;margin:6px 0 10px}

footer{text-align:center;font-size:12.5px;color:var(--muted);padding:18px 16px 28px}
footer button{margin-top:8px;font-size:13px;font-weight:700;color:var(--brand-d);padding:8px 14px;border-radius:10px;border:1.5px solid var(--line);background:#fff}

/* 모달 */
.modal{position:fixed;inset:0;background:rgba(10,30,32,.55);z-index:50;display:flex;align-items:flex-end;justify-content:center}
.sheet{background:#fff;width:100%;max-width:520px;max-height:92vh;overflow-y:auto;border-radius:20px 20px 0 0;padding:18px 16px 24px}
@media(min-width:560px){.modal{align-items:center}.sheet{border-radius:20px}}
.sheet h2{margin:0 0 12px;font-size:18px;display:flex;justify-content:space-between;align-items:center}
.f{margin-bottom:12px}
.f label{display:block;font-size:13.5px;font-weight:700;margin-bottom:4px;color:var(--muted)}
.f input,.f select,.f textarea{width:100%;border:1.5px solid var(--line);border-radius:10px;padding:10px 12px;font-size:16px;background:#f8fbfb;outline:none}
.f input:focus,.f select:focus,.f textarea:focus{border-color:var(--brand)}
.grid2{display:grid;grid-template-columns:1fr 1fr;gap:8px}
.fs{border:1.5px solid var(--line);border-radius:14px;padding:12px;margin-bottom:12px;background:#fbfdfd}
.fs>b{display:block;font-size:14px;margin-bottom:8px}
.row{display:flex;gap:6px;align-items:center;margin-bottom:6px;flex-wrap:wrap}
.row input[type=text]{flex:1;min-width:120px}
.row input[type=number]{width:64px}
.row input{border:1.5px solid var(--line);border-radius:8px;padding:8px;font-size:15px}
.sw{width:22px;height:22px;border-radius:50%;border:2px solid #fff;box-shadow:0 0 0 1px #bbb}
.sw.sel{box-shadow:0 0 0 2.5px var(--ink)}
.note{font-size:12.5px;color:var(--muted);margin:0 0 8px}

.toast{position:fixed;left:50%;bottom:24px;transform:translateX(-50%) translateY(20px);background:var(--ink);color:#fff;padding:12px 18px;border-radius:12px;font-weight:700;font-size:15px;opacity:0;pointer-events:none;transition:all .25s;z-index:60;max-width:90vw;width:max-content;text-align:center}
.toast.show{opacity:1;transform:translateX(-50%)}

/* 라벨 인쇄 */
#print-label{display:none}
@media print{
  body.printing>*:not(#print-label){display:none!important}
  body.printing #print-label{display:flex!important;flex-direction:column;align-items:center;gap:8px;padding:10mm;text-align:center}
  #print-label img{width:45mm;height:45mm}
  #print-label .z{font-size:28pt;font-weight:900}
  #print-label .n{font-size:12pt;font-weight:700;max-width:80mm}
  #print-label .c{font-size:10pt;font-family:monospace}
}
</style>
</head>
<body>
<header>
  <div class="wrap">
    <div class="logo"><span style="font-size:22px">📦</span><div>꿈비 합포 가이드<small>GGUMBI STORE</small></div></div>
    <div style="display:flex;gap:6px"><span id="admin-chip" class="chip admin hidden">관리자</span><span class="chip">안성 1물류</span></div>
  </div>
</header>

<main>
  <div class="wrap">
    <!-- 로비 -->
    <section id="view-lobby" class="stack">
      <div id="admin-lobby" class="admin-bar hidden">
        <h3>🛠 관리자 도구</h3>
        <p>이 폰에서 바꾼 내용은 다른 폰에 바로 반영되지 않아요. 수정 후 <b>index.html 저장</b> → GitHub에 업로드하면 전체 반영됩니다.</p>
        <div class="btn-row">
          <button class="btn primary grow" onclick="openEditor(false)">＋ 제품 추가</button>
          <button class="btn grow" id="group-edit-btn" onclick="toggleGroupEdit()">그룹 편집</button>
        </div>
        <div class="btn-row" style="margin-top:8px">
          <button class="btn amber grow" onclick="downloadUpdatedHtml()">💾 index.html 저장</button>
        </div>
        <div id="group-toolbar" class="hidden" style="margin-top:12px;border-top:1px dashed #e0b43a;padding-top:12px">
          <p style="margin-bottom:8px">아래 목록에서 제품을 체크하고 그룹 이름을 입력하세요. (같은 이름이면 기존 그룹에 추가)</p>
          <div class="f" style="margin-bottom:8px"><input id="group-name-input" placeholder="예: 하이가드 베이비룸 세트"></div>
          <div class="btn-row">
            <button class="btn primary grow" onclick="saveNewGroup()">그룹 저장</button>
            <button class="btn sm" onclick="selectAllEdit(true)">전체</button>
            <button class="btn sm" onclick="selectAllEdit(false)">해제</button>
          </div>
          <p id="edit-count" style="margin:8px 0 0">선택: 0개</p>
        </div>
      </div>

      <div>
        <div class="search">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round"><circle cx="11" cy="11" r="7"/><path d="m20 20-3.5-3.5"/></svg>
          <input id="search-input" type="search" placeholder="제품명 · 바코드 · 랙 구역 검색" oninput="renderLobby()" autocomplete="off">
        </div>
      </div>
      <div id="product-list"></div>
    </section>

    <!-- 상세 -->
    <section id="view-detail" class="stack hidden"></section>
  </div>
</main>

<footer>
  <div>© 2026 GGUMBI Store 안성 1물류 합포 가이드</div>
  <button id="admin-toggle" onclick="toggleAdmin()">관리자 모드 켜기</button>
</footer>

<!-- 편집 모달 -->
<div id="editor" class="modal hidden" onclick="if(event.target===this)closeEditor()">
  <div class="sheet">
    <h2><span id="editor-title">제품 추가</span><button class="btn sm" onclick="closeEditor()">닫기</button></h2>
    <input type="hidden" id="edit-original-id">
    <div class="f"><label>제품 유형</label>
      <select id="input-type" onchange="toggleEditorType()">
        <option value="tpu-mat">TPU 매트 (수량에 따라 박스 선택)</option>
        <option value="babyroom">하이가드 베이비룸 세트</option>
      </select></div>
    <div class="f"><label>제품명</label><input id="input-name"></div>
    <div class="grid2">
      <div class="f"><label>바코드 / 제품코드</label><input id="input-code" inputmode="numeric"></div>
      <div class="f"><label>랙 구역</label><input id="input-zone" placeholder="예: HW"></div>
    </div>

    <div id="ed-tpu" class="fs">
      <b>매트 박스 규칙</b>
      <div class="grid2">
        <div class="f"><label>기본 입수(장)</label><input type="number" id="input-default-qty"></div>
        <div class="f"><label>최대 합포(장)</label><input type="number" id="input-max-qty"></div>
      </div>
      <div class="f"><label>이 수량 이하면 작은 박스</label><input type="number" id="input-box-threshold"></div>
      <div class="grid2">
        <div class="f"><label>작은 박스 이름</label><input id="input-box-small-name"></div>
        <div class="f"><label>큰 박스 이름</label><input id="input-box-large-name"></div>
      </div>
      <b style="margin-top:4px">함께 넣는 부자재 <span style="font-weight:500;color:var(--muted);font-size:12.5px">(수량 0 = 현장 확인)</span></b>
      <div id="ed-acc"></div>
      <button class="btn sm" onclick="tmpAcc.push({name:'',qty:1});renderEdRows()">＋ 부자재 추가</button>
    </div>

    <div id="ed-baby" class="fs hidden">
      <b>베이비룸 구성</b>
      <div class="grid2">
        <div class="f"><label>세트 규격</label>
          <select id="input-babyroom-size">
            <option value="10P">10P</option><option value="12P">12P</option><option value="14P">14P</option>
            <option value="16P">16P (2박스 분할)</option><option value="18P">18P (2박스 분할)</option><option value="20P">20P (2박스 분할)</option>
          </select></div>
        <div class="f"><label>사용 박스</label><input id="input-babyroom-box-name" placeholder="예: 8P A박스 사용"></div>
      </div>
      <p class="note">가드·도어는 '큰 부품', 그 외는 자동으로 '지퍼백 부자재' 칸에 나뉘어 표시돼요. 색 점은 글자 강조용입니다.</p>
      <div id="ed-comp"></div>
      <button class="btn sm" onclick="tmpComp.push({name:'',qty:1,color:COLOR_PALETTE[0]});renderEdRows()">＋ 구성품 추가</button>
    </div>

    <div class="f"><label>주의사항 (한 줄에 하나씩, ⭐로 시작하면 빨간 강조)</label><textarea id="input-warning" rows="3"></textarea></div>
    <div class="f"><label>포장 사진 주소 (선택)</label><input id="input-photo" placeholder="https://... (GitHub에 올린 사진 주소)"></div>
    <div class="btn-row"><button class="btn grow" onclick="closeEditor()">취소</button><button class="btn primary grow" onclick="saveProduct()">저장</button></div>
  </div>
</div>

<div id="toast" class="toast"></div>
<div id="print-label"></div>

<script>
    const CLIENT_VERSION = "1780561783260";

    const COLOR_PALETTE = [
        { label: "기본(검정)", text: "#223d40", bg: "" },
        { label: "파랑", text: "#1d4ed8", bg: "#dbeafe" },
        { label: "주황", text: "#b45309", bg: "#fef3c7" },
        { label: "초록", text: "#15803d", bg: "#dcfce7" },
        { label: "핑크", text: "#be185d", bg: "#fce7f3" },
        { label: "보라", text: "#6d28d9", bg: "#ede9fe" },
        { label: "빨강", text: "#dc2626", bg: "#fee2e2" },
        { label: "청록", text: "#0f766e", bg: "#ccfbf1" },
    ];

    /* DATA_PLACEHOLDER_START */
    const initialProductsDb = [
      {
            "id": "licoco-corner",
            "type": "tpu-mat",
            "code": "8800368450026",
            "name": "[리코코] 디자인 TPU 클립매트 60x60x2.5cm 모던 갤럭시 코너형",
            "zone": "1N",
            "warning": "-매트 기본 입수 6개\n-전용 고정 클립 수량 확인",
            "defaultQty": 6,
            "maxQty": 6,
            "boxThreshold": 2,
            "boxSmallName": "2P 소형박스",
            "boxLargeName": "6P 표준박스",
            "accessories": [
                  {
                        "name": "전용 고정 클립 (코너)",
                        "qty": 6
                  }
            ]
      },
      {
            "id": "licoco-center",
            "type": "tpu-mat",
            "code": "8800368450019",
            "name": "[리코코] 디자인 TPU 클립매트 60x60x2.5cm 모던 갤럭시 센터형",
            "zone": "1N",
            "warning": "-매트 기본 입수 6개\n-전용 고정 클립 수량 확인",
            "defaultQty": 6,
            "maxQty": 6,
            "boxThreshold": 2,
            "boxSmallName": "2P 소형박스",
            "boxLargeName": "6P 표준박스",
            "accessories": [
                  {
                        "name": "전용 고정 클립 (센터)",
                        "qty": 12
                  }
            ]
      },
      {
            "id": "licoco-side",
            "type": "tpu-mat",
            "code": "8800368450002",
            "name": "[리코코] 디자인 TPU 클립매트 60x60x2.5cm 모던 갤럭시 사이드형",
            "zone": "1N",
            "warning": "-매트 기본 입수 6개\n-전용 고정 클립 수량 확인",
            "defaultQty": 6,
            "maxQty": 6,
            "boxThreshold": 2,
            "boxSmallName": "2P 소형박스",
            "boxLargeName": "6P 표준박스",
            "accessories": [
                  {
                        "name": "전용 고정 클립 (사이드)",
                        "qty": 9
                  }
            ]
      },
      {
            "id": "ggumbi-babyroom",
            "type": "babyroom",
            "code": "8800257942298",
            "name": "[꿈비] 하이가드 베이비룸 200x140 아이보리 10p",
            "zone": "HW",
            "warning": "- 가드 및 도어를 제외한 부자재는 부자재용 비닐 지퍼백 사용\n- 부자재는 파란색 텍스트로 되어있음",
            "babyroomSize": "10P",
            "boxRecommended": "10P 전용 박스",
            "components": [
                  {
                        "name": "640 가드",
                        "qty": 2
                  },
                  {
                        "name": "730 가드",
                        "qty": 2
                  },
                  {
                        "name": "750 가드",
                        "qty": 5
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 6,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "3.5M 고정밴드",
                        "qty": 2,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 1,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780374858590",
            "type": "babyroom",
            "code": "8800257942304",
            "name": "[꿈비] 하이가드 베이비룸 252x140 아이보리 12p",
            "zone": "HW",
            "warning": "- 가드 및 도어를 제외한 부자재는 부자재용 비닐 지퍼백 사용\n- 부자재는 파란색 텍스트로 되어있음",
            "babyroomSize": "12P",
            "boxRecommended": "12P 전용 박스 사용",
            "components": [
                  {
                        "name": "640 가드",
                        "qty": 6
                  },
                  {
                        "name": "730 가드",
                        "qty": 2
                  },
                  {
                        "name": "750 가드",
                        "qty": 3
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 8,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "3.5M 고정밴드",
                        "qty": 3,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 32,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780374987406",
            "type": "babyroom",
            "code": "8800257942311",
            "name": "[꿈비] 하이가드 베이비룸 292x140 아이보리 12p",
            "zone": "HW",
            "warning": "- 가드 및 도어를 제외한 부자재는 부자재용 비닐 지퍼백 사용\n- 부자재는 파란색 텍스트로 되어있음",
            "babyroomSize": "12P",
            "boxRecommended": "12P 전용 박스 사용",
            "components": [
                  {
                        "name": "730 가드",
                        "qty": 4
                  },
                  {
                        "name": "750 가드",
                        "qty": 5
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "840 가드",
                        "qty": 2
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 8,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "3.5M 고정밴드",
                        "qty": 3,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 32,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780375100758",
            "type": "babyroom",
            "code": "8800257942328",
            "name": "[꿈비] 하이가드 베이비룸 323x140 아이보리 14p",
            "zone": "HW",
            "warning": "- 가드 및 도어를 제외한 부자재는 부자재용 비닐 지퍼백 사용\n- 부자재는 파란색 텍스트로 되어있음",
            "babyroomSize": "14P",
            "boxRecommended": "14P 전용 박스 사용",
            "components": [
                  {
                        "name": "640 가드",
                        "qty": 6
                  },
                  {
                        "name": "730 가드",
                        "qty": 2
                  },
                  {
                        "name": "750 가드",
                        "qty": 5
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 10,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "3.5M 고정밴드",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 38,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780375210150",
            "type": "babyroom",
            "code": "8800257942441",
            "name": "[꿈비] 하이가드 자이언트 베이비룸 252x200 아이보리 14p",
            "zone": "HW",
            "warning": "- 가드 및 도어를 제외한 부자재는 부자재용 비닐 지퍼백 사용\n- 부자재는 파란색 텍스트로 되어있음",
            "babyroomSize": "14P",
            "boxRecommended": "14P 박스 사용",
            "components": [
                  {
                        "name": "640 가드",
                        "qty": 8
                  },
                  {
                        "name": "730 가드",
                        "qty": 2
                  },
                  {
                        "name": "750 가드",
                        "qty": 3
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 10,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "5M 고정밴드",
                        "qty": 3,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 38,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780375366237",
            "type": "babyroom",
            "code": "8800257942465",
            "name": "[꿈비] 하이가드 자이언트 베이비룸 292x200 아이보리 14p",
            "zone": "HW",
            "warning": "- 가드 및 도어를 제외한 부자재는 부자재용 비닐 지퍼백 사용\n- 부자재는 파란색 텍스트로 되어있음",
            "babyroomSize": "14P",
            "boxRecommended": "14P 박스 사용",
            "components": [
                  {
                        "name": "640 가드",
                        "qty": 2
                  },
                  {
                        "name": "730 가드",
                        "qty": 4
                  },
                  {
                        "name": "750 가드",
                        "qty": 5
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "840 가드",
                        "qty": 2
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 10,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "5M 고정밴드",
                        "qty": 3,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 38,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780375534918",
            "type": "babyroom",
            "code": "8800257942472,8800257942489",
            "name": "[꿈비] 하이가드 자이언트 베이비룸 323x200 아이보리_8p_A",
            "zone": "HW",
            "warning": "⭐ 8P 박스 2개 분할 패킹 필수 ⭐\n-8P A박스 , 8P B박스 각각 가드,도어 분할해서 출고\n- 가드 및 도어를 제외한 부자재는 부자재용 비닐 지퍼백 사용\n- 부자재는 파란색 텍스트로 되어있음",
            "babyroomSize": "16P",
            "boxRecommended": "8P A박스사용",
            "components": [
                  {
                        "name": "640 가드",
                        "qty": 8
                  }
            ]
      },
      {
            "id": "item-1780375614053",
            "type": "babyroom",
            "code": "8800257942489,8800257942472",
            "name": "[꿈비] 하이가드 자이언트 베이비룸 323x200 아이보리_8p_B",
            "zone": "HW",
            "warning": "⭐ 8P 박스 2개 분할 패킹 필수 ⭐\n-8P A박스 , 8P B박스 각각 가드,도어 분할해서 출고\n- 가드 및 도어를 제외한 부자재는 부자재용 비닐 지퍼백 사용\n- 부자재는 파란색 텍스트로 되어있음",
            "babyroomSize": "16P",
            "boxRecommended": "8P B박스 사용",
            "components": [
                  {
                        "name": "730 가드",
                        "qty": 2
                  },
                  {
                        "name": "750 가드",
                        "qty": 5
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 12,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "3.5M 고정밴드",
                        "qty": 1,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "5M 고정밴드",
                        "qty": 3,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 44,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780385173903",
            "type": "babyroom",
            "code": "8800257942533,8800257942540",
            "name": "[꿈비] 하이가드 자이언트 베이비룸 382x200 아이보리_8p_A",
            "zone": "HW",
            "warning": "⭐ 8P 박스 2개 분할 패킹 필수 ⭐\n-8P A박스 , 8P B박스 각각 가드,도어 분할해서 출고\n- 가드 및 도어를 제외한 부자재는 부자재용 비닐 지퍼백 사용\n- 부자재는 파란색 텍스트로 되어있음",
            "babyroomSize": "16P",
            "boxRecommended": "8P A박스사용",
            "components": [
                  {
                        "name": "640 가드",
                        "qty": 2
                  },
                  {
                        "name": "840 가드",
                        "qty": 6
                  }
            ]
      },
      {
            "id": "item-1780385267503",
            "type": "babyroom",
            "code": "8800257942540,8800257942533",
            "name": "[꿈비] 하이가드 자이언트 베이비룸 382x200 아이보리_8p_B",
            "zone": "HW",
            "warning": "⭐ 8P 박스 2개 분할 패킹 필수 ⭐\n-8P A박스 , 8P B박스 각각 가드,도어 분할해서 출고\n- 가드 및 도어를 제외한 부자재는 부자재용 비닐 지퍼백 사용\n- 부자재는 파란색 텍스트로 되어있음",
            "babyroomSize": "16P",
            "boxRecommended": "8P B박스사용",
            "components": [
                  {
                        "name": "730 가드",
                        "qty": 4
                  },
                  {
                        "name": "750 가드",
                        "qty": 3
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 12,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "3.5M 고정밴드",
                        "qty": 1,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "5M 고정밴드",
                        "qty": 3,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 44,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780385585167",
            "type": "babyroom",
            "code": "8800257942496,8800257942502",
            "name": "[꿈비] 하이가드 자이언트 베이비룸 323x230 아이보리_8p_A",
            "zone": "HW",
            "warning": "⭐ 8P 박스 2개 분할 패킹 필수 ⭐\n-8P A박스 , 8P B박스 각각 가드,도어 분할해서 출고\n- 가드 및 도어를 제외한 부자재는 부자재용 비닐 지퍼백 사용\n- 부자재는 파란색 텍스트로 되어있음",
            "babyroomSize": "16P",
            "boxRecommended": "8P A박스사용",
            "components": [
                  {
                        "name": "640 가드",
                        "qty": 6
                  },
                  {
                        "name": "730 가드",
                        "qty": 2
                  }
            ]
      },
      {
            "id": "item-1780385661143",
            "type": "babyroom",
            "code": "8800257942502,8800257942496",
            "name": "[꿈비] 하이가드 자이언트 베이비룸 323x230 아이보리_8p_B",
            "zone": "HW",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "babyroomSize": "16P",
            "boxRecommended": "8P B박스사용",
            "components": [
                  {
                        "name": "750 가드",
                        "qty": 3
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "840 가드",
                        "qty": 4
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 12
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4
                  },
                  {
                        "name": "3.5M 고정밴드",
                        "qty": 4
                  },
                  {
                        "name": "5M 고정밴드",
                        "qty": 2
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 44
                  }
            ]
      },
      {
            "id": "item-1780385741247",
            "type": "babyroom",
            "code": "8800257942557,8800257942564",
            "name": "[꿈비] 하이가드 자이언트 베이비룸 382x230 아이보리_8p_A",
            "zone": "HW",
            "warning": "⭐ 8P 박스 2개 분할 패킹 필수 ⭐\n-8P A박스 , 8P B박스 각각 가드,도어 분할해서 출고\n- 가드 및 도어를 제외한 부자재는 부자재용 비닐 지퍼백 사용\n- 부자재는 파란색 텍스트로 되어있음",
            "babyroomSize": "16P",
            "boxRecommended": "8P A박스사용",
            "components": [
                  {
                        "name": "730 가드",
                        "qty": 4
                  },
                  {
                        "name": "750 가드",
                        "qty": 1
                  },
                  {
                        "name": "840 가드",
                        "qty": 2
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  }
            ]
      },
      {
            "id": "item-1780385827831",
            "type": "babyroom",
            "code": "8800257942564,8800257942557",
            "name": "[꿈비] 하이가드 자이언트 베이비룸 382x230 아이보리_8p_B",
            "zone": "HW",
            "warning": "⭐ 8P 박스 2개 분할 패킹 필수 ⭐\n-8P A박스 , 8P B박스 각각 가드,도어 분할해서 출고\n- 가드 및 도어를 제외한 부자재는 부자재용 비닐 지퍼백 사용\n- 부자재는 파란색 텍스트로 되어있음",
            "babyroomSize": "16P",
            "boxRecommended": "8P B박스사용",
            "components": [
                  {
                        "name": "840 가드",
                        "qty": 8
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 12,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "3.5M 고정밴드",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "5M 고정밴드",
                        "qty": 2,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 44,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780386009959",
            "type": "babyroom",
            "code": "8800257942229",
            "name": "[꿈비] 하이가드 더블원피스 베이비룸 284x240 아이보리_14p",
            "zone": "HW",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "babyroomSize": "14P",
            "boxRecommended": "14P 박스 사용",
            "components": [
                  {
                        "name": "730 가드",
                        "qty": 2
                  },
                  {
                        "name": "750 가드",
                        "qty": 5
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "840 가드",
                        "qty": 6
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 10,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "3.5M 고정밴드",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "5M 고정밴드",
                        "qty": 1,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 38,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780386145575",
            "type": "babyroom",
            "code": "8800257942205,8800257942212",
            "name": "[꿈비] 하이가드 더블원피스 베이비룸 252x252 아이보리_8p_A",
            "zone": "HW",
            "warning": "⭐ 8P 박스 2개 분할 패킹 필수 ⭐\n-8P A박스 , 8P B박스 각각 가드,도어 분할해서 출고\n- 가드 및 도어를 제외한 부자재는 부자재용 비닐 지퍼백 사용\n- 부자재는 파란색 텍스트로 되어있음",
            "babyroomSize": "16P",
            "boxRecommended": "8P A박스 사용",
            "components": [
                  {
                        "name": "640 가드",
                        "qty": 8
                  }
            ]
      },
      {
            "id": "item-1780386263095",
            "type": "babyroom",
            "code": "8800257942212,8800257942205",
            "name": "[꿈비] 하이가드 더블원피스 베이비룸 252x252 아이보리_8p_B",
            "zone": "HW",
            "warning": "⭐ 8P 박스 2개 분할 패킹 필수 ⭐\n-8P A박스 , 8P B박스 각각 가드,도어 분할해서 출고\n- 가드 및 도어를 제외한 부자재는 부자재용 비닐 지퍼백 사용\n- 부자재는 파란색 텍스트로 되어있음",
            "babyroomSize": "16P",
            "boxRecommended": "8P B박스 사용",
            "components": [
                  {
                        "name": "640 가드",
                        "qty": 4
                  },
                  {
                        "name": "750 가드",
                        "qty": 3
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 12,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "3.5M 고정밴드",
                        "qty": 8,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 44,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780386876614",
            "type": "babyroom",
            "code": "8809527903502",
            "name": "[꿈비x소브] 하이가드 베이비룸 220x280 아이보리_14p",
            "zone": "HW",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "babyroomSize": "14P",
            "boxRecommended": "14P 박스 사용",
            "components": [
                  {
                        "name": "730 가드",
                        "qty": 8
                  },
                  {
                        "name": "750 가드",
                        "qty": 3
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "840 가드",
                        "qty": 2
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 10,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "3.5m 고정밴드",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "5m 고정밴드",
                        "qty": 1,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 38,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780387350437",
            "type": "babyroom",
            "code": "8800280932723",
            "name": "[꿈비] 하이가드 베이비룸 260x280 아이보리 16p",
            "zone": "HW",
            "warning": "⭐ 8P 박스 2개 분할 패킹 필수 ⭐\n-8P A박스 , 8P B박스 각각 가드,도어 분할해서 출고\n- 가드 및 도어를 제외한 부자재는 부자재용 비닐 지퍼백 사용\n- 부자재는 파란색 텍스트로 되어있음",
            "babyroomSize": "16P",
            "boxRecommended": "8P A박스 사용",
            "components": [
                  {
                        "name": "730 가드",
                        "qty": 8
                  }
            ]
      },
      {
            "id": "item-1780387407645",
            "type": "babyroom",
            "code": "8800280932723",
            "name": "[꿈비] 하이가드 베이비룸 260x280 아이보리 16p",
            "zone": "HW",
            "warning": "⭐ 8P 박스 2개 분할 패킹 필수 ⭐\n-8P A박스 , 8P B박스 각각 가드,도어 분할해서 출고\n- 가드 및 도어를 제외한 부자재는 부자재용 비닐 지퍼백 사용\n- 부자재는 파란색 텍스트로 되어있음",
            "babyroomSize": "16P",
            "boxRecommended": "8P B박스 사용",
            "components": [
                  {
                        "name": "640 가드",
                        "qty": 4
                  },
                  {
                        "name": "730 가드",
                        "qty": 2
                  },
                  {
                        "name": "750 가드",
                        "qty": 1
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 12,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "3.5M 고정밴드",
                        "qty": 8,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 44,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780387444933",
            "type": "babyroom",
            "code": "8800280932730",
            "name": "[꿈비] 하이가드 베이비룸 280x280 아이보리 16P",
            "zone": "HW",
            "warning": "⭐ 8P 박스 2개 분할 패킹 필수 ⭐\n-8P A박스 , 8P B박스 각각 가드,도어 분할해서 출고\n- 가드 및 도어를 제외한 부자재는 부자재용 비닐 지퍼백 사용\n- 부자재는 파란색 텍스트로 되어있음",
            "babyroomSize": "16P",
            "boxRecommended": "8P A박스 사용",
            "components": [
                  {
                        "name": "730 가드",
                        "qty": 8
                  }
            ]
      },
      {
            "id": "item-1780387497254",
            "type": "babyroom",
            "code": "8800280932730",
            "name": "[꿈비] 하이가드 베이비룸 280x280 아이보리 16P",
            "zone": "HW",
            "warning": "⭐ 8P 박스 2개 분할 패킹 필수 ⭐\n-8P A박스 , 8P B박스 각각 가드,도어 분할해서 출고\n- 가드 및 도어를 제외한 부자재는 부자재용 비닐 지퍼백 사용\n- 부자재는 파란색 텍스트로 되어있음",
            "babyroomSize": "16P",
            "boxRecommended": "8P B박스 사용",
            "components": [
                  {
                        "name": "730 가드",
                        "qty": 4
                  },
                  {
                        "name": "750 가드",
                        "qty": 3
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 12,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "3.5M 고정밴드",
                        "qty": 8,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 44,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780387555541",
            "type": "babyroom",
            "code": "8800257942236,8800257942243",
            "name": "[꿈비] 하이가드 더블원피스 베이비룸 292x252 아이보리_8p_A",
            "zone": "HW",
            "warning": "⭐ 8P 박스 2개 분할 패킹 필수 ⭐\n-8P A박스 , 8P B박스 각각 가드,도어 분할해서 출고\n- 가드 및 도어를 제외한 부자재는 부자재용 비닐 지퍼백 사용\n- 부자재는 파란색 텍스트로 되어있음",
            "babyroomSize": "16P",
            "boxRecommended": "8P A박스 사용",
            "components": [
                  {
                        "name": "640 가드",
                        "qty": 6
                  },
                  {
                        "name": "730 가드",
                        "qty": 2
                  }
            ]
      },
      {
            "id": "item-1780387648742",
            "type": "babyroom",
            "code": "8800257942243,8800257942236",
            "name": "[꿈비] 하이가드 더블원피스 베이비룸 292x252 아이보리_8p_B",
            "zone": "HW",
            "warning": "⭐ 8P 박스 2개 분할 패킹 필수 ⭐\n-8P A박스 , 8P B박스 각각 가드,도어 분할해서 출고\n- 가드 및 도어를 제외한 부자재는 부자재용 비닐 지퍼백 사용\n- 부자재는 파란색 텍스트로 되어있음",
            "babyroomSize": "16P",
            "boxRecommended": "8P B박스 사용",
            "components": [
                  {
                        "name": "750 가드",
                        "qty": 5
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "840 가드",
                        "qty": 2
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 12,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "3.5M 고정밴드",
                        "qty": 1,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 44,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780387720277",
            "type": "babyroom",
            "code": "8800257942250,8800257942267",
            "name": "[꿈비] 하이가드 더블원피스 베이비룸 323x252 아이보리_10p_A",
            "zone": "HW",
            "warning": "⭐ 8P 박스 2개 분할 패킹 필수 ⭐\n-10P A박스 , 8P B박스 각각 가드,도어 분할해서 출고\n- 가드 및 도어를 제외한 부자재는 부자재용 비닐 지퍼백 사용\n- 부자재는 파란색 텍스트로 되어있음",
            "babyroomSize": "18P",
            "boxRecommended": "10P A박스 사용",
            "components": [
                  {
                        "name": "640 가드",
                        "qty": 10
                  }
            ]
      },
      {
            "id": "item-1780387888006",
            "type": "babyroom",
            "code": "8800257942267,8800257942250",
            "name": "[꿈비] 하이가드 더블원피스 베이비룸 323x252 아이보리_8p_B",
            "zone": "HW",
            "warning": "⭐ 8P 박스 2개 분할 패킹 필수 ⭐\n-10P A박스 , 8P B박스 각각 가드,도어 분할해서 출고\n- 가드 및 도어를 제외한 부자재는 부자재용 비닐 지퍼백 사용\n- 부자재는 파란색 텍스트로 되어있음",
            "babyroomSize": "18P",
            "boxRecommended": "8P B박스 사용",
            "components": [
                  {
                        "name": "640 가드",
                        "qty": 2
                  },
                  {
                        "name": "730 가드",
                        "qty": 2
                  },
                  {
                        "name": "750 가드",
                        "qty": 3
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 14,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "3.5M 고정밴드",
                        "qty": 8,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "5M 고정밴드",
                        "qty": 1,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 50,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780388037102",
            "type": "babyroom",
            "code": "8800257942274,8800257942281",
            "name": "[꿈비] 하이가드 더블원피스 베이비룸 382x282 아이보리_10p_A",
            "zone": "HW",
            "warning": "⭐ 10P,8P 박스 2개 분할 패킹 필수 ⭐\n-10P A박스 , 8P B박스 각각 가드,도어 분할해서 출고\n- 가드 및 도어를 제외한 부자재는 부자재용 비닐 지퍼백 사용\n- 부자재는 파란색 텍스트로 되어있음",
            "babyroomSize": "18P",
            "boxRecommended": "10P A박스 사용",
            "components": [
                  {
                        "name": "730 가드",
                        "qty": 8
                  },
                  {
                        "name": "750 가드",
                        "qty": 2
                  }
            ]
      },
      {
            "id": "item-1780388125021",
            "type": "babyroom",
            "code": "8800257942281,8800257942274",
            "name": "[꿈비] 하이가드 더블원피스 베이비룸 382x282 아이보리_8p_B",
            "zone": "HW",
            "warning": "⭐ 10P,8P 박스 2개 분할 패킹 필수 ⭐\n-10P A박스 , 8P B박스 각각 가드,도어 분할해서 출고\n- 가드 및 도어를 제외한 부자재는 부자재용 비닐 지퍼백 사용\n- 부자재는 파란색 텍스트로 되어있음",
            "babyroomSize": "18P",
            "boxRecommended": "8P B박스 사용",
            "components": [
                  {
                        "name": "750 가드",
                        "qty": 1
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "840 가드",
                        "qty": 6
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 14,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "3.5M 고정밴드",
                        "qty": 7,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "5M 고정밴드",
                        "qty": 2,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 50,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780388578437",
            "type": "babyroom",
            "code": "코드X",
            "name": "[꿈비] 트리플 원피스 베이비룸 세트 252X400 20P",
            "zone": "HW",
            "warning": "⭐ 10P 박스 2개 분할 패킹 필수 ⭐\n-10P A박스 , 10P B박스 각각 가드,도어 분할해서 출고\n- 가드 및 도어를 제외한 부자재는 부자재용 비닐 지퍼백 사용\n- 부자재는 파란색 텍스트로 되어있음",
            "babyroomSize": "20P",
            "boxRecommended": "10P A박스 사용",
            "components": [
                  {
                        "name": "640 가드",
                        "qty": 10
                  }
            ]
      },
      {
            "id": "item-1780388660701",
            "type": "babyroom",
            "code": "코드X",
            "name": "[꿈비] 트리플 원피스 베이비룸 세트 252X400 20P",
            "zone": "HW",
            "warning": "⭐ 10P 박스 2개 분할 패킹 필수 ⭐\n-10P A박스 , 10P B박스 각각 가드,도어 분할해서 출고\n- 가드 및 도어를 제외한 부자재는 부자재용 비닐 지퍼백 사용\n- 부자재는 파란색 텍스트로 되어있음",
            "babyroomSize": "20P",
            "boxRecommended": "10P B박스 사용",
            "components": [
                  {
                        "name": "730 가드",
                        "qty": 8
                  },
                  {
                        "name": "750 가드",
                        "qty": 1
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 16,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "3.5M 고정밴드",
                        "qty": 11,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "5M 고정밴드",
                        "qty": 1,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 56,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780388702677",
            "type": "babyroom",
            "code": "코드X",
            "name": "트리플 원피스 베이비룸 세트 323X400 22P",
            "zone": "HW",
            "warning": "⭐ 10P,12P 박스 2개 분할 패킹 필수 ⭐\n-10P A박스 , 12P B박스 각각 가드,도어 분할해서 출고\n- 가드 및 도어를 제외한 부자재는 부자재용 비닐 지퍼백 사용\n- 부자재는 파란색 텍스트로 되어있음",
            "babyroomSize": "20P",
            "boxRecommended": "10P A박스 사용",
            "components": [
                  {
                        "name": "640 가드",
                        "qty": 10
                  }
            ]
      },
      {
            "id": "item-1780388835437",
            "type": "babyroom",
            "code": "코드X",
            "name": "트리플 원피스 베이비룸 세트 323X400 22P",
            "zone": "HW",
            "warning": "⭐ 10P,12P 박스 2개 분할 패킹 필수 ⭐\n-10P A박스 , 12P B박스 각각 가드,도어 분할해서 출고\n- 가드 및 도어를 제외한 부자재는 부자재용 비닐 지퍼백 사용\n- 부자재는 파란색 텍스트로 되어있음",
            "babyroomSize": "20P",
            "boxRecommended": "12P B박스 사용",
            "components": [
                  {
                        "name": "730 가드",
                        "qty": 10
                  },
                  {
                        "name": "750 가드",
                        "qty": 1
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 18,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "3.5M 고정밴드",
                        "qty": 10,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "5M 고정밴드",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 62,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780530594480",
            "type": "babyroom",
            "code": "8800260085913",
            "name": "트윈스타 플러스 매트 210x180 (패밀리)_크림화이트",
            "zone": "1N",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "babyroomSize": "12P",
            "boxRecommended": "12P 박스 사용",
            "components": [
                  {
                        "name": "640 가드",
                        "qty": 6
                  },
                  {
                        "name": "730 가드",
                        "qty": 4
                  },
                  {
                        "name": "750 가드",
                        "qty": 1
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 8,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "5M 고정밴드",
                        "qty": 2,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 32,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780530701568",
            "type": "babyroom",
            "code": "8800257940546",
            "name": "[꿈비] 럭키스타 특대형 전용 하이가드 베이비룸 10p",
            "zone": "HW",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "babyroomSize": "10P",
            "boxRecommended": "10P 박스 사용",
            "components": [
                  {
                        "name": "640 가드",
                        "qty": 4
                  },
                  {
                        "name": "730 가드",
                        "qty": 4
                  },
                  {
                        "name": "750 가드",
                        "qty": 1
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 6,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "3.5M 고정밴드",
                        "qty": 2,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 26,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780530791240",
            "type": "babyroom",
            "code": "8800257941901",
            "name": "[꿈비] 월드스타 특대형 전용 하이가드 베이비룸 10p",
            "zone": "HW",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "babyroomSize": "10P",
            "boxRecommended": "10P 박스 사용",
            "components": [
                  {
                        "name": "730 가드",
                        "qty": 2
                  },
                  {
                        "name": "750 가드",
                        "qty": 3
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "840 가드",
                        "qty": 4
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 6,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "5M 고정밴드",
                        "qty": 2,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 26,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780530879720",
            "type": "babyroom",
            "code": "8800257942007",
            "name": "[꿈비] 트윈스타 슈퍼특대형 전용 하이가드 베이비룸 14p",
            "zone": "HW",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "babyroomSize": "14P",
            "boxRecommended": "14P 박스 사용",
            "components": [
                  {
                        "name": "640 가드",
                        "qty": 6
                  },
                  {
                        "name": "750 가드",
                        "qty": 1
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "840 가드",
                        "qty": 6
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 10,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "5M 고정밴드",
                        "qty": 3,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 38,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780530976047",
            "type": "babyroom",
            "code": "8800257942014",
            "name": "[꿈비] 트윈스타 자이언트특대형 전용 하이가드 베이비룸 14p",
            "zone": "HW",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "babyroomSize": "14P",
            "boxRecommended": "14P 박스 사용",
            "components": [
                  {
                        "name": "640 가드",
                        "qty": 4
                  },
                  {
                        "name": "730 가드",
                        "qty": 2
                  },
                  {
                        "name": "750 가드",
                        "qty": 1
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "840 가드",
                        "qty": 6
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 10,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "5M 고정밴드",
                        "qty": 3,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 38,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780531117696",
            "type": "babyroom",
            "code": "8809527903205",
            "name": "[꿈비] 하이가드 범퍼침대 베이비룸 8p",
            "zone": "HW",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "babyroomSize": "10P",
            "boxRecommended": "8P 박스 사용",
            "components": [
                  {
                        "name": "750 가드",
                        "qty": 3
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "840 가드",
                        "qty": 4
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "5M 고정밴드",
                        "qty": 2,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 20,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780532133711",
            "type": "babyroom",
            "code": "8809527903564",
            "name": "[꿈비] 하이가드 범퍼침대 베이비룸 10p",
            "zone": "HW",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "babyroomSize": "10P",
            "boxRecommended": "10P 박스 사용",
            "components": [
                  {
                        "name": "640 가드",
                        "qty": 2
                  },
                  {
                        "name": "730 가드",
                        "qty": 2
                  },
                  {
                        "name": "750 가드",
                        "qty": 5
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 6,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "3.5M 고정밴드",
                        "qty": 2,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 26,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780532197599",
            "type": "babyroom",
            "code": "8809527903199",
            "name": "[꿈비] 하이가드 범퍼침대 베이비룸 12p",
            "zone": "HW",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "babyroomSize": "12P",
            "boxRecommended": "12P 박스 사용",
            "components": [
                  {
                        "name": "640 가드",
                        "qty": 4
                  },
                  {
                        "name": "730 가드",
                        "qty": 4
                  },
                  {
                        "name": "750 가드",
                        "qty": 3
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 8,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "5M 고정밴드",
                        "qty": 2,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 32,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780532265782",
            "type": "babyroom",
            "code": "8800280934550",
            "name": "[꿈비] 하이가드 범퍼침대 베이비룸 12p 슈퍼특대형 오픈형",
            "zone": "HW",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "babyroomSize": "12P",
            "boxRecommended": "12P 박스 사용",
            "components": [
                  {
                        "name": "640 가드",
                        "qty": 4
                  },
                  {
                        "name": "750 가드",
                        "qty": 3
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "840 가드",
                        "qty": 4
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 8,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "5M 고정밴드",
                        "qty": 2,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 32,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780532709766",
            "type": "babyroom",
            "code": "코드X",
            "name": "[꿈비] 하이가드 범퍼침대 베이비룸 16p 슈퍼특대형 실속형",
            "zone": "HW",
            "warning": "⭐ 8P 박스 2개 분할 패킹 필수 ⭐\n-8P A박스 , 8P B박스 각각 가드,도어 분할해서 출고\n- 가드 및 도어를 제외한 부자재는 부자재용 비닐 지퍼백 사용\n- 부자재는 파란색 텍스트로 되어있음",
            "babyroomSize": "16P",
            "boxRecommended": "8P A박스 사용",
            "components": [
                  {
                        "name": "640 가드",
                        "qty": 8
                  }
            ]
      },
      {
            "id": "item-1780532812174",
            "type": "babyroom",
            "code": "코드X",
            "name": "[꿈비] 하이가드 범퍼침대 베이비룸 16p 슈퍼특대형 실속형",
            "zone": "HW",
            "warning": "⭐ 8P 박스 2개 분할 패킹 필수 ⭐\n-8P A박스 , 8P B박스 각각 가드,도어 분할해서 출고\n- 가드 및 도어를 제외한 부자재는 부자재용 비닐 지퍼백 사용\n- 부자재는 파란색 텍스트로 되어있음",
            "babyroomSize": "16P",
            "boxRecommended": "8P B박스 사용",
            "components": [
                  {
                        "name": "640 가드",
                        "qty": 2
                  },
                  {
                        "name": "750 가드",
                        "qty": 5
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 12,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "3.5M 고정밴드",
                        "qty": 1,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "5M 고정밴드",
                        "qty": 3,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 44,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780532911486",
            "type": "babyroom",
            "code": "8800257942373",
            "name": "[꿈비] 하이가드 베이비룸 Q 사이즈 매트용 아이보리 10p",
            "zone": "HW",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "babyroomSize": "10P",
            "boxRecommended": "10P 박스 사용",
            "components": [
                  {
                        "name": "640 가드",
                        "qty": 2
                  },
                  {
                        "name": "730 가드",
                        "qty": 2
                  },
                  {
                        "name": "750 가드",
                        "qty": 3
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "840 가드",
                        "qty": 2
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 6,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "5M 고정밴드",
                        "qty": 2,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 26,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780532976542",
            "type": "babyroom",
            "code": "8800257942403",
            "name": "[꿈비] 하이가드 베이비룸 SS+SS 사이즈 매트용 아이보리 12p",
            "zone": "HW",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "babyroomSize": "12P",
            "boxRecommended": "12P 박스 사용",
            "components": [
                  {
                        "name": "640 가드",
                        "qty": 2
                  },
                  {
                        "name": "730 가드",
                        "qty": 4
                  },
                  {
                        "name": "750 가드",
                        "qty": 3
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "840 가드",
                        "qty": 2
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 8,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "5M 고정밴드",
                        "qty": 2,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 32,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780533038686",
            "type": "babyroom",
            "code": "8800257942397",
            "name": "[꿈비] 하이가드 베이비룸 SS+Q 사이즈 매트용 아이보리 14p",
            "zone": "HW",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "babyroomSize": "14P",
            "boxRecommended": "14P 박스 사용",
            "components": [
                  {
                        "name": "640 가드",
                        "qty": 6
                  },
                  {
                        "name": "730 가드",
                        "qty": 6
                  },
                  {
                        "name": "750 가드",
                        "qty": 1
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 10,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "5M 고정밴드",
                        "qty": 3,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 38,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780533132422",
            "type": "babyroom",
            "code": "8800257942380",
            "name": "[꿈비] 하이가드 베이비룸 Q+Q 사이즈 매트용 아이보리 14p",
            "zone": "HW",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "babyroomSize": "14P",
            "boxRecommended": "14P 박스 사용",
            "components": [
                  {
                        "name": "640 가드",
                        "qty": 2
                  },
                  {
                        "name": "730 가드",
                        "qty": 6
                  },
                  {
                        "name": "750 가드",
                        "qty": 1
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "840 가드",
                        "qty": 4
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 10,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "5M 고정밴드",
                        "qty": 3,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 38,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780533207678",
            "type": "babyroom",
            "code": "8809527902932",
            "name": "[소브] 하이가드 베리2단 베이비룸 200x140 아이보리_10p",
            "zone": "HW",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "babyroomSize": "10P",
            "boxRecommended": "10P 박스 사용",
            "components": [
                  {
                        "name": "640 가드",
                        "qty": 2
                  },
                  {
                        "name": "730 가드",
                        "qty": 4
                  },
                  {
                        "name": "750 가드",
                        "qty": 3
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 6,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "3.5M 고정밴드",
                        "qty": 2,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 26,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780533272741",
            "type": "babyroom",
            "code": "8809527902949",
            "name": "[소브] 하이가드 베리2단 베이비룸 240x140 아이보리_10p",
            "zone": "HW",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "babyroomSize": "10P",
            "boxRecommended": "10P 박스 사용",
            "components": [
                  {
                        "name": "730 가드",
                        "qty": 2
                  },
                  {
                        "name": "750 가드",
                        "qty": 1
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "840 가드",
                        "qty": 6
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 6,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "3.5M 고정밴드",
                        "qty": 2,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 26,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780533380430",
            "type": "babyroom",
            "code": "8809527903533",
            "name": "[꿈비x소브] 하이가드 베이비룸 240x280 아이보리_14p",
            "zone": "HW",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "babyroomSize": "14P",
            "boxRecommended": "14P 박스 사용",
            "components": [
                  {
                        "name": "730 가드",
                        "qty": 6
                  },
                  {
                        "name": "750 가드",
                        "qty": 1
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "840 가드",
                        "qty": 6
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 10,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "3.5M 고정밴드",
                        "qty": 5,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 38,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780533471893",
            "type": "babyroom",
            "code": "8809527902956",
            "name": "[소브] 하이가드 제로빅 베이비룸 300x140 아이보리_12p",
            "zone": "HW",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "babyroomSize": "12P",
            "boxRecommended": "12P 박스 사용",
            "components": [
                  {
                        "name": "730 가드",
                        "qty": 6
                  },
                  {
                        "name": "750 가드",
                        "qty": 1
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "840 가드",
                        "qty": 4
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 8,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "3.5M 고정밴드",
                        "qty": 3,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 32,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780533540709",
            "type": "babyroom",
            "code": "8809527902963",
            "name": "[소브] 하이가드 제로빅 베이비룸 260x200 아이보리_14p",
            "zone": "HW",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "babyroomSize": "14P",
            "boxRecommended": "14P 박스 사용",
            "components": [
                  {
                        "name": "640 가드",
                        "qty": 6
                  },
                  {
                        "name": "730 가드",
                        "qty": 6
                  },
                  {
                        "name": "750 가드",
                        "qty": 1
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 10,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "5M 고정밴드",
                        "qty": 3,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 38,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780533610878",
            "type": "babyroom",
            "code": "8809527902970",
            "name": "[꿈비x소브] 하이가드 베이비룸 300x200 아이보리_14p",
            "zone": "HW",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "babyroomSize": "14P",
            "boxRecommended": "14P 박스 사용",
            "components": [
                  {
                        "name": "640 가드",
                        "qty": 2
                  },
                  {
                        "name": "730 가드",
                        "qty": 6
                  },
                  {
                        "name": "750 가드",
                        "qty": 1
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "840 가드",
                        "qty": 4
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 10,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "5M 고정밴드",
                        "qty": 3,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 38,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780533681853",
            "type": "babyroom",
            "code": "8809527903502",
            "name": "[꿈비x소브] 하이가드 베이비룸 220x280 아이보리_14p",
            "zone": "HW",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "babyroomSize": "14P",
            "boxRecommended": "14P 박스 사용",
            "components": [
                  {
                        "name": "730 가드",
                        "qty": 8
                  },
                  {
                        "name": "750 가드",
                        "qty": 3
                  },
                  {
                        "name": "750 도어",
                        "qty": 1
                  },
                  {
                        "name": "840 가드",
                        "qty": 2
                  },
                  {
                        "name": "일자 커넥터",
                        "qty": 10,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "코너 커넥터",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "3.5M 고정밴드",
                        "qty": 4,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "5M 고정밴드",
                        "qty": 1,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  },
                  {
                        "name": "미끄럼 방지 패드",
                        "qty": 38,
                        "color": {
                              "label": "파랑",
                              "text": "#1d4ed8",
                              "bg": "#dbeafe"
                        }
                  }
            ]
      },
      {
            "id": "item-1780533791478",
            "type": "tpu-mat",
            "code": "8800280939661",
            "name": "[리코코] 디자인 TPU 클립매트 60x60x2.5cm 모던 민트 센터형",
            "zone": "1N",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "defaultQty": 6,
            "maxQty": 6,
            "boxThreshold": 2,
            "boxSmallName": "2P 박스",
            "boxLargeName": "14P 박스",
            "accessories": [
                  {
                        "name": "전용 고정 클립",
                        "qty": 12
                  }
            ]
      },
      {
            "id": "item-1780533821286",
            "type": "tpu-mat",
            "code": "8800280939654",
            "name": "[리코코] 디자인 TPU 클립매트 60x60x2.5cm 모던 민트 사이드형",
            "zone": "1N",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "defaultQty": 6,
            "maxQty": 6,
            "boxThreshold": 2,
            "boxSmallName": "2P 박스",
            "boxLargeName": "14P 박스",
            "accessories": [
                  {
                        "name": "전용 고정 클립",
                        "qty": 9
                  }
            ]
      },
      {
            "id": "item-1780533843661",
            "type": "tpu-mat",
            "code": "8800280939678",
            "name": "[리코코] 디자인 TPU 클립매트 60x60x2.5cm 모던 민트 코너형",
            "zone": "1N",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "defaultQty": 6,
            "maxQty": 6,
            "boxThreshold": 2,
            "boxSmallName": "2P 박스",
            "boxLargeName": "14P 박스",
            "accessories": [
                  {
                        "name": "전용 고정 클립",
                        "qty": 6
                  }
            ]
      },
      {
            "id": "item-1780533893229",
            "type": "tpu-mat",
            "code": "8800368450088",
            "name": "[리코코] 디자인 TPU 클립매트 60x60x2.5cm 클라우드 사이드형",
            "zone": "1N",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "defaultQty": 6,
            "maxQty": 6,
            "boxThreshold": 2,
            "boxSmallName": "2P 박스",
            "boxLargeName": "6P 박스",
            "accessories": [
                  {
                        "name": "전용 고정 클립",
                        "qty": 6
                  }
            ]
      },
      {
            "id": "item-1780533918814",
            "type": "tpu-mat",
            "code": "8800368450071",
            "name": "[리코코] 디자인 TPU 클립매트 60x60x2.5cm 클라우드 센터형",
            "zone": "1N",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "defaultQty": 6,
            "maxQty": 6,
            "boxThreshold": 2,
            "boxSmallName": "2P 박스",
            "boxLargeName": "6P 박스",
            "accessories": [
                  {
                        "name": "전용 고정 클립",
                        "qty": 12
                  }
            ]
      },
      {
            "id": "item-1780533948718",
            "type": "tpu-mat",
            "code": "8800368450064",
            "name": "[리코코] 디자인 TPU 클립매트 60x60x2.5cm 클라우드 코너형",
            "zone": "1N",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "defaultQty": 6,
            "maxQty": 6,
            "boxThreshold": 2,
            "boxSmallName": "2P 박스",
            "boxLargeName": "6P 박스",
            "accessories": [
                  {
                        "name": "전용 고정 클립",
                        "qty": 9
                  }
            ]
      },
      {
            "id": "item-1780534012525",
            "type": "tpu-mat",
            "code": "8800280931078",
            "name": "[리코코] N자이언트 TPU 퍼즐매트 사이드형 1P 크림",
            "zone": "1Q",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "defaultQty": 6,
            "maxQty": 6,
            "boxThreshold": 1,
            "boxSmallName": "2P 박스",
            "boxLargeName": "6P 박스",
            "accessories": []
      },
      {
            "id": "item-1780534038109",
            "type": "tpu-mat",
            "code": "8800280931061",
            "name": "[리코코] N자이언트 TPU 퍼즐매트 센터형 1P 크림",
            "zone": "1Q",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "defaultQty": 6,
            "maxQty": 6,
            "boxThreshold": 2,
            "boxSmallName": "2P 박스",
            "boxLargeName": "6P 박스",
            "accessories": []
      },
      {
            "id": "item-1780534058613",
            "type": "tpu-mat",
            "code": "8800280931085",
            "name": "[리코코] N자이언트 TPU 퍼즐매트 코너형 1P 크림",
            "zone": "1Q",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "defaultQty": 6,
            "maxQty": 6,
            "boxThreshold": 2,
            "boxSmallName": "2P 박스",
            "boxLargeName": "6P 박스",
            "accessories": []
      },
      {
            "id": "item-1780534265653",
            "type": "tpu-mat",
            "code": "8800257943653",
            "name": "[리코코] TPU 셀프시공 퍼즐매트 사이드형 1p 크림베이지",
            "zone": "2F",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "defaultQty": 12,
            "maxQty": 12,
            "boxThreshold": 12,
            "boxSmallName": "12P 박스",
            "boxLargeName": "12P 박스",
            "accessories": []
      },
      {
            "id": "item-1780534296109",
            "type": "tpu-mat",
            "code": "8800257943691",
            "name": "[리코코] TPU 셀프시공 퍼즐매트 센터형 1p 크림베이지",
            "zone": "2F",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "defaultQty": 12,
            "maxQty": 12,
            "boxThreshold": 12,
            "boxSmallName": "12P 박스",
            "boxLargeName": "12P 박스",
            "accessories": []
      },
      {
            "id": "item-1780534321253",
            "type": "tpu-mat",
            "code": "8800257943721",
            "name": "[리코코] TPU 셀프시공 퍼즐매트 코너형 1p 크림베이지",
            "zone": "2F",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "defaultQty": 12,
            "maxQty": 12,
            "boxThreshold": 12,
            "boxSmallName": "12P 박스",
            "boxLargeName": "12P 박스",
            "accessories": []
      },
      {
            "id": "item-1780534369397",
            "type": "tpu-mat",
            "code": "8800257943745",
            "name": "[리코코] TPU 와플 퍼즐매트 50x50x1.0cm 크림베이지",
            "zone": "2G",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "defaultQty": 25,
            "maxQty": 25,
            "boxThreshold": 25,
            "boxSmallName": "25P 박스",
            "boxLargeName": "25P 박스",
            "accessories": [
                  {
                        "name": "[리코코] TPU 와플 퍼즐매트 십자 커넥터",
                        "qty": 0
                  }
            ]
      },
      {
            "id": "item-1780534417957",
            "type": "tpu-mat",
            "code": "8800257943776",
            "name": "[리코코] TPU 워터가드 퍼즐매트 사이드형 1p 크림베이지",
            "zone": "2C",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "defaultQty": 10,
            "maxQty": 10,
            "boxThreshold": 10,
            "boxSmallName": "10P 박스",
            "boxLargeName": "10P 박스",
            "accessories": [
                  {
                        "name": "[리코코] TPU 워터가드 퍼즐매트 십자클립 1p",
                        "qty": 0
                  }
            ]
      },
      {
            "id": "item-1780534444590",
            "type": "tpu-mat",
            "code": "8800257943790",
            "name": "[리코코] TPU 워터가드 퍼즐매트 센터형 1p 크림베이지",
            "zone": "2C",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "defaultQty": 10,
            "maxQty": 10,
            "boxThreshold": 10,
            "boxSmallName": "10P 소형박스",
            "boxLargeName": "10P 박스",
            "accessories": [
                  {
                        "name": "[리코코] TPU 워터가드 퍼즐매트 십자클립 1p",
                        "qty": 0
                  }
            ]
      },
      {
            "id": "item-1780534476197",
            "type": "tpu-mat",
            "code": "8800257943820",
            "name": "[리코코] TPU 워터가드 퍼즐매트 코너형 1p 크림베이지",
            "zone": "2C",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "defaultQty": 10,
            "maxQty": 10,
            "boxThreshold": 10,
            "boxSmallName": "10P 박스",
            "boxLargeName": "10P 박스",
            "accessories": [
                  {
                        "name": "[리코코] TPU 워터가드 퍼즐매트 십자클립 1p",
                        "qty": 0
                  }
            ]
      },
      {
            "id": "item-1780534601189",
            "type": "tpu-mat",
            "code": "8800280931115",
            "name": "[리코코] 황변방지 TPU 퍼즐매트 사이드형 1P 60x60x2cm 그라운드",
            "zone": "1Q",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "defaultQty": 14,
            "maxQty": 14,
            "boxThreshold": 14,
            "boxSmallName": "14P 박스",
            "boxLargeName": "14P 박스",
            "accessories": []
      },
      {
            "id": "item-1780534665757",
            "type": "tpu-mat",
            "code": "8800280931122",
            "name": "[리코코] 황변방지 TPU 퍼즐매트 센터형 1P 60x60x2cm 그라운드",
            "zone": "1Q",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "defaultQty": 14,
            "maxQty": 14,
            "boxThreshold": 14,
            "boxSmallName": "14P 박스",
            "boxLargeName": "14P 박스",
            "accessories": []
      },
      {
            "id": "item-1780534695437",
            "type": "tpu-mat",
            "code": "8800280931108",
            "name": "[리코코] 황변방지 TPU 퍼즐매트 코너형 1P 60x60x2cm 그라운드",
            "zone": "1Q",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "defaultQty": 14,
            "maxQty": 14,
            "boxThreshold": 14,
            "boxSmallName": "14P 박스",
            "boxLargeName": "14P 박스",
            "accessories": []
      },
      {
            "id": "item-1780534725277",
            "type": "tpu-mat",
            "code": "8800280931146",
            "name": "[리코코] 황변방지 TPU 퍼즐매트 사이드형 1P 60x60x2cm 페일스톤",
            "zone": "1Q",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "defaultQty": 14,
            "maxQty": 14,
            "boxThreshold": 14,
            "boxSmallName": "14P 박스",
            "boxLargeName": "14P 박스",
            "accessories": []
      },
      {
            "id": "item-1780534749724",
            "type": "tpu-mat",
            "code": "8800280931153",
            "name": "[리코코] 황변방지 TPU 퍼즐매트 센터형 1P 60x60x2cm 페일스톤",
            "zone": "1Q",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "defaultQty": 14,
            "maxQty": 14,
            "boxThreshold": 14,
            "boxSmallName": "14P 박스",
            "boxLargeName": "14P 박스",
            "accessories": []
      },
      {
            "id": "item-1780534772709",
            "type": "tpu-mat",
            "code": "8800280931139",
            "name": "[리코코] 황변방지 TPU 퍼즐매트 코너형 1P 60x60x2cm 페일스톤",
            "zone": "1Q",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "defaultQty": 14,
            "maxQty": 14,
            "boxThreshold": 14,
            "boxSmallName": "14P 박스",
            "boxLargeName": "14P 박스",
            "accessories": []
      },
      {
            "id": "item-1780534837061",
            "type": "tpu-mat",
            "code": "8800280935007",
            "name": "[리코코] 황변방지 TPU 퍼즐매트 60x60x2.5cm 그라운드_사이드형 1P",
            "zone": "1Q",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "defaultQty": 6,
            "maxQty": 6,
            "boxThreshold": 2,
            "boxSmallName": "2P 박스",
            "boxLargeName": "6P 박스",
            "accessories": []
      },
      {
            "id": "item-1780534860613",
            "type": "tpu-mat",
            "code": "8800280934994",
            "name": "[리코코] 황변방지 TPU 퍼즐매트 60x60x2.5cm 페일스톤_센터형 1P",
            "zone": "1Q",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "defaultQty": 6,
            "maxQty": 6,
            "boxThreshold": 2,
            "boxSmallName": "2P 박스",
            "boxLargeName": "6P 박스",
            "accessories": []
      },
      {
            "id": "item-1780534915708",
            "type": "tpu-mat",
            "code": "8800280935014",
            "name": "[리코코] 황변방지 TPU 퍼즐매트 60x60x2.5cm 그라운드_센터형 1P",
            "zone": "1Q",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "defaultQty": 6,
            "maxQty": 6,
            "boxThreshold": 2,
            "boxSmallName": "2P 박스",
            "boxLargeName": "6P 박스",
            "accessories": []
      },
      {
            "id": "item-1780534938221",
            "type": "tpu-mat",
            "code": "8800280934994",
            "name": "[리코코] 황변방지 TPU 퍼즐매트 60x60x2.5cm 페일스톤_사이드형 1P",
            "zone": "1Q",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "defaultQty": 6,
            "maxQty": 6,
            "boxThreshold": 2,
            "boxSmallName": "2P 박스",
            "boxLargeName": "6P 박스",
            "accessories": []
      },
      {
            "id": "item-1780535013253",
            "type": "tpu-mat",
            "code": "8800280934994",
            "name": "[리코코] 황변방지 TPU 퍼즐매트 60x60x2.5cm 그라운드_코너형 1P",
            "zone": "1Q",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "defaultQty": 6,
            "maxQty": 6,
            "boxThreshold": 2,
            "boxSmallName": "2P 박스",
            "boxLargeName": "6P 박스",
            "accessories": []
      },
      {
            "id": "item-1780535044828",
            "type": "tpu-mat",
            "code": "8800280935045",
            "name": "[리코코] 황변방지 TPU 퍼즐매트 60x60x2.5cm 페일스톤_코너형 1P",
            "zone": "1Q",
            "warning": "기본 포장 시 부자재 겹치지 않도록 밀착 검수 요망",
            "defaultQty": 6,
            "maxQty": 6,
            "boxThreshold": 2,
            "boxSmallName": "2P 박스",
            "boxLargeName": "6P 박스",
            "accessories": []
      },
      {
            "id": "item-1780535411180",
            "type": "tpu-mat",
            "code": "8809527909368",
            "name": "[꿈비] 끼임방지 침대가드 200cm 라이트그레이",
            "zone": "1R",
            "warning": "- 한 박스 내입수량 2개 참고하여 출고\n- 고정밴드 1P 및 코너커넥터 2P(1set) 합포 수량 참고하여 출고",
            "defaultQty": 2,
            "maxQty": 2,
            "boxThreshold": 1,
            "boxSmallName": "1P 박스",
            "boxLargeName": "2P 박스",
            "accessories": [
                  {
                        "name": "침대가드 고정밴드 1P",
                        "qty": 0
                  },
                  {
                        "name": "침대가드 코너커넥터",
                        "qty": 0
                  }
            ]
      },
      {
            "id": "item-1780535466932",
            "type": "tpu-mat",
            "code": "8809527909351",
            "name": "[꿈비] 끼임방지 침대가드 180cm 라이트그레이",
            "zone": "1R",
            "warning": "- 한 박스 내입수량 2개 참고하여 출고\n- 고정밴드 1P 및 코너커넥터 2P(1set) 합포 수량 참고하여 출고",
            "defaultQty": 2,
            "maxQty": 2,
            "boxThreshold": 1,
            "boxSmallName": "1P 박스",
            "boxLargeName": "2P 박스",
            "accessories": [
                  {
                        "name": "고정밴드 1P",
                        "qty": 0
                  },
                  {
                        "name": "코너커넥터 2P(1set)",
                        "qty": 0
                  }
            ]
      },
      {
            "id": "item-1780535511133",
            "type": "tpu-mat",
            "code": "8809527909344",
            "name": "[꿈비] 끼임방지 침대가드 165cm 라이트그레이",
            "zone": "1Q",
            "warning": "- 한 박스 내입수량 2개 참고하여 출고\n- 고정밴드 1P 및 코너커넥터 2P(1set) 합포 수량 참고하여 출고",
            "defaultQty": 2,
            "maxQty": 2,
            "boxThreshold": 1,
            "boxSmallName": "1P 박스",
            "boxLargeName": "2P 박스",
            "accessories": [
                  {
                        "name": "고정밴드 1P",
                        "qty": 0
                  },
                  {
                        "name": "코너커넥터 2P(1set)",
                        "qty": 0
                  }
            ]
      },
      {
            "id": "item-1780535556948",
            "type": "tpu-mat",
            "code": "8809527909337",
            "name": "[꿈비] 끼임방지 침대가드 150cm 라이트그레이",
            "zone": "1R",
            "warning": "- 한 박스 내입수량 2개 참고하여 출고\n- 고정밴드 1P 및 코너커넥터 2P(1set) 합포 수량 참고하여 출고",
            "defaultQty": 2,
            "maxQty": 2,
            "boxThreshold": 1,
            "boxSmallName": "1P 박스",
            "boxLargeName": "2P 박스",
            "accessories": [
                  {
                        "name": "고정밴드 1P",
                        "qty": 0
                  },
                  {
                        "name": "코너커넥터 2P(1set)",
                        "qty": 0
                  }
            ]
      },
      {
            "id": "item-1780535603588",
            "type": "tpu-mat",
            "code": "8809527909320",
            "name": "[꿈비] 끼임방지 침대가드 110cm 라이트그레이",
            "zone": "1R",
            "warning": "- 한 박스 내입수량 2개 참고하여 출고\n- 고정밴드 1P 및 코너커넥터 2P(1set) 합포 수량 참고하여 출고",
            "defaultQty": 2,
            "maxQty": 2,
            "boxThreshold": 1,
            "boxSmallName": "1P 박스",
            "boxLargeName": "2P 박스",
            "accessories": [
                  {
                        "name": "고정밴드 1P",
                        "qty": 0
                  },
                  {
                        "name": "코너커넥터 2P(1set)",
                        "qty": 0
                  }
            ]
      },
      {
            "id": "item-1780535741244",
            "type": "tpu-mat",
            "code": "8800257946081",
            "name": "[파미야] 셀프시공 카페트 매트 50X50_그레이_1P",
            "zone": "1H",
            "warning": "-12개 이하 출고 시 12P 박스 사용",
            "defaultQty": 24,
            "maxQty": 24,
            "boxThreshold": 12,
            "boxSmallName": "12P 소형박스",
            "boxLargeName": "24P 대형박스",
            "accessories": []
      },
      {
            "id": "item-1780535777892",
            "type": "tpu-mat",
            "code": "8800257946098",
            "name": "[파미야] 셀프시공 카페트 매트 50X50_딥그린_1P",
            "zone": "1H",
            "warning": "-12개 이하 출고 시 12P 박스 사용",
            "defaultQty": 24,
            "maxQty": 24,
            "boxThreshold": 12,
            "boxSmallName": "12P 소형박스",
            "boxLargeName": "24P 대형박스",
            "accessories": []
      },
      {
            "id": "item-1780535803652",
            "type": "tpu-mat",
            "code": "8800257946104",
            "name": "[파미야] 셀프시공 카페트 매트 50X50_딥블루_1P",
            "zone": "1H",
            "warning": "-12개 이하 출고 시 12P 박스 사용",
            "defaultQty": 24,
            "maxQty": 24,
            "boxThreshold": 12,
            "boxSmallName": "12P 소형박스",
            "boxLargeName": "24P 대형박스",
            "accessories": []
      },
      {
            "id": "item-1780535838252",
            "type": "tpu-mat",
            "code": "8800257946128",
            "name": "[파미야] 셀프시공 카페트 매트 50X50_베이지_1P",
            "zone": "1H",
            "warning": "-12개 이하 출고 시 12P 박스 사용",
            "defaultQty": 24,
            "maxQty": 24,
            "boxThreshold": 12,
            "boxSmallName": "12P 소형박스",
            "boxLargeName": "24P 대형박스",
            "accessories": []
      },
      {
            "id": "item-1780535862837",
            "type": "tpu-mat",
            "code": "8800257946135",
            "name": "[파미야] 셀프시공 카페트 매트 50X50_브라운_1P",
            "zone": "1H",
            "warning": "-12개 이하 출고 시 12P 박스 사용",
            "defaultQty": 24,
            "maxQty": 24,
            "boxThreshold": 12,
            "boxSmallName": "12P 소형박스",
            "boxLargeName": "24P 대형박스",
            "accessories": []
      },
      {
            "id": "item-1780535893333",
            "type": "tpu-mat",
            "code": "8800257946142",
            "name": "[파미야] 셀프시공 카페트 매트 50X50_블루그레이_1P",
            "zone": "1H",
            "warning": "-12개 이하 출고 시 12P 박스 사용",
            "defaultQty": 24,
            "maxQty": 24,
            "boxThreshold": 12,
            "boxSmallName": "12P 소형박스",
            "boxLargeName": "24P 대형박스",
            "accessories": []
      },
      {
            "id": "item-1780535917652",
            "type": "tpu-mat",
            "code": "8800257946159",
            "name": "[파미야] 셀프시공 카페트 매트 50X50_아이보리_1P",
            "zone": "1H",
            "warning": "-12개 이하 출고 시 12P 박스 사용",
            "defaultQty": 24,
            "maxQty": 24,
            "boxThreshold": 12,
            "boxSmallName": "12P 소형박스",
            "boxLargeName": "24P 대형박스",
            "accessories": []
      },
      {
            "id": "item-1780535941181",
            "type": "tpu-mat",
            "code": "8800257946166",
            "name": "[파미야] 셀프시공 카페트 매트 50X50_코퍼_1P",
            "zone": "1H",
            "warning": "-12개 이하 출고 시 12P 박스 사용",
            "defaultQty": 24,
            "maxQty": 24,
            "boxThreshold": 12,
            "boxSmallName": "12P 소형박스",
            "boxLargeName": "24P 대형박스",
            "accessories": []
      },
      {
            "id": "item-1780535965700",
            "type": "tpu-mat",
            "code": "8800257946173",
            "name": "[파미야] 셀프시공 카페트 매트 50X50_크림_1P",
            "zone": "1H",
            "warning": "-12개 이하 출고 시 12P 박스 사용",
            "defaultQty": 24,
            "maxQty": 24,
            "boxThreshold": 12,
            "boxSmallName": "12P 소형박스",
            "boxLargeName": "24P 대형박스",
            "accessories": []
      },
      {
            "id": "item-1780536023124",
            "type": "tpu-mat",
            "code": "8800257946180",
            "name": "[파미야] 셀프시공 카페트 매트 60X60_베이지_1P",
            "zone": "1H",
            "warning": "- 수량 확인 후 출고",
            "defaultQty": 12,
            "maxQty": 12,
            "boxThreshold": 12,
            "boxSmallName": "12P 박스",
            "boxLargeName": "12P 박스",
            "accessories": []
      },
      {
            "id": "item-1780536068404",
            "type": "tpu-mat",
            "code": "8800257946197",
            "name": "[파미야] 셀프시공 카페트 매트 60X60_아이보리_1P",
            "zone": "1H",
            "warning": "- 수량 확인 후 출고",
            "defaultQty": 12,
            "maxQty": 12,
            "boxThreshold": 12,
            "boxSmallName": "12P 박스",
            "boxLargeName": "12P 박스",
            "accessories": []
      },
      {
            "id": "item-1780536092868",
            "type": "tpu-mat",
            "code": "8800257946203",
            "name": "[파미야] 셀프시공 카페트 매트 60X60_크림_1P",
            "zone": "1H",
            "warning": "- 수량 확인 후 출고",
            "defaultQty": 12,
            "maxQty": 12,
            "boxThreshold": 12,
            "boxSmallName": "12P 박스",
            "boxLargeName": "12P 박스",
            "accessories": []
      }
];
    const initialGroupsDb = [
      {
            "id": "grp-1780549972924",
            "name": "디자인 TPU",
            "productIds": [
                  "licoco-corner",
                  "licoco-center",
                  "licoco-side",
                  "item-1780533791478",
                  "item-1780533821286",
                  "item-1780533843661",
                  "item-1780533893229",
                  "item-1780533918814",
                  "item-1780533948718"
            ],
            "collapsed": true
      },
      {
            "id": "grp-1780550040099",
            "name": "하이가드 베이비룸 세트",
            "productIds": [
                  "ggumbi-babyroom",
                  "item-1780374858590",
                  "item-1780374987406",
                  "item-1780375100758",
                  "item-1780375210150",
                  "item-1780375366237",
                  "item-1780375534918",
                  "item-1780375614053",
                  "item-1780385173903",
                  "item-1780385267503",
                  "item-1780385585167",
                  "item-1780385661143",
                  "item-1780385741247",
                  "item-1780385827831",
                  "item-1780386009959",
                  "item-1780386145575",
                  "item-1780386263095",
                  "item-1780386876614",
                  "item-1780387350437",
                  "item-1780387407645",
                  "item-1780387444933",
                  "item-1780387497254",
                  "item-1780387555541",
                  "item-1780387648742",
                  "item-1780387720277",
                  "item-1780387888006",
                  "item-1780388037102",
                  "item-1780388125021",
                  "item-1780388578437",
                  "item-1780388660701",
                  "item-1780388702677",
                  "item-1780388835437",
                  "item-1780530594480",
                  "item-1780530701568",
                  "item-1780530791240",
                  "item-1780530879720",
                  "item-1780530976047",
                  "item-1780531117696",
                  "item-1780532133711",
                  "item-1780532197599",
                  "item-1780532265782",
                  "item-1780532709766",
                  "item-1780532812174",
                  "item-1780532911486",
                  "item-1780532976542",
                  "item-1780533038686",
                  "item-1780533132422",
                  "item-1780533207678",
                  "item-1780533272741",
                  "item-1780533380430",
                  "item-1780533471893",
                  "item-1780533540709",
                  "item-1780533610878",
                  "item-1780533681853"
            ],
            "collapsed": true
      },
      {
            "id": "grp-1780550083971",
            "name": "N자이언트 TPU",
            "productIds": [
                  "item-1780534012525",
                  "item-1780534038109",
                  "item-1780534058613"
            ],
            "collapsed": true
      },
      {
            "id": "grp-1780550099898",
            "name": "TPU 셀프시공 퍼즐매트",
            "productIds": [
                  "item-1780534265653",
                  "item-1780534296109",
                  "item-1780534321253"
            ],
            "collapsed": true
      },
      {
            "id": "grp-1780550122356",
            "name": "TPU 워터가드",
            "productIds": [
                  "item-1780534417957",
                  "item-1780534444590",
                  "item-1780534476197"
            ],
            "collapsed": true
      },
      {
            "id": "grp-1780550139483",
            "name": "TPU 와플 퍼즐매트 50X50X1.0",
            "productIds": [
                  "item-1780534369397"
            ],
            "collapsed": true
      },
      {
            "id": "grp-1780550188763",
            "name": "황변방지 TPU 60X60X2",
            "productIds": [
                  "item-1780534601189",
                  "item-1780534665757",
                  "item-1780534695437",
                  "item-1780534725277",
                  "item-1780534749724",
                  "item-1780534772709"
            ],
            "collapsed": true
      },
      {
            "id": "grp-1780550242379",
            "name": "끼임방지 침대가드",
            "productIds": [
                  "item-1780535411180",
                  "item-1780535466932",
                  "item-1780535511133",
                  "item-1780535556948",
                  "item-1780535603588"
            ],
            "collapsed": true
      },
      {
            "id": "grp-1780550267555",
            "name": "셀프시공 카페트 매트",
            "productIds": [
                  "item-1780535741244",
                  "item-1780535777892",
                  "item-1780535803652",
                  "item-1780535838252",
                  "item-1780535862837",
                  "item-1780535893333",
                  "item-1780535917652",
                  "item-1780535941181",
                  "item-1780535965700",
                  "item-1780536023124",
                  "item-1780536068404",
                  "item-1780536092868"
            ],
            "collapsed": true
      },
      {
            "id": "grp-1780550832419",
            "name": "황변방지 TPU 60X60X2.5",
            "productIds": [
                  "item-1780534837061",
                  "item-1780534860613",
                  "item-1780534915708",
                  "item-1780534938221",
                  "item-1780535013253",
                  "item-1780535044828"
            ],
            "collapsed": true
      }
];
    /* DATA_PLACEHOLDER_END */

    // =============================================
    // 상태
    // =============================================
    let productsDb = [];
    let groupsDb = [];
    let currentId = null;
    let matQty = 1;
    let checked = new Set();
    let isAdmin = false;
    let groupEdit = false;
    let editSel = new Set();
    let tmpAcc = [], tmpComp = [];

    const $ = id => document.getElementById(id);
    const esc = s => String(s ?? '').replace(/[&<>"']/g, c => ({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c]));
    const store = {
        get(k){ try { return localStorage.getItem(k); } catch(e){ return null; } },
        set(k,v){ try { localStorage.setItem(k,v); } catch(e){} }
    };
    const ICON_CHECK = '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3.5" stroke-linecap="round" stroke-linejoin="round"><path d="m5 12 5 5 9-10"/></svg>';
    const ICON_RIGHT = '<svg class="arrow" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round"><path d="m9 5 7 7-7 7"/></svg>';
    const ICON_DOWN = '<svg class="chev" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round"><path d="m6 9 6 6 6-6"/></svg>';

    // =============================================
    // 데이터 로드/저장 (기존과 동일한 저장 키 사용)
    // =============================================
    function loadProductsData() {
        const savedVersion = store.get('GGUMBI_CLIENT_VERSION');
        const savedData = store.get('GGUMBI_PRODUCTS_DB_DYNAMIC');
        if (savedVersion !== CLIENT_VERSION || !savedData) {
            productsDb = JSON.parse(JSON.stringify(initialProductsDb));
            store.set('GGUMBI_PRODUCTS_DB_DYNAMIC', JSON.stringify(productsDb));
            store.set('GGUMBI_CLIENT_VERSION', CLIENT_VERSION);
            store.set('GGUMBI_GROUPS_DB', JSON.stringify(initialGroupsDb));
        } else {
            try { productsDb = JSON.parse(savedData); } catch(e) { productsDb = JSON.parse(JSON.stringify(initialProductsDb)); }
        }
        const savedGroups = store.get('GGUMBI_GROUPS_DB');
        try { groupsDb = savedGroups ? JSON.parse(savedGroups) : JSON.parse(JSON.stringify(initialGroupsDb)); }
        catch(e) { groupsDb = JSON.parse(JSON.stringify(initialGroupsDb)); }
    }
    function saveProductsData(){ store.set('GGUMBI_PRODUCTS_DB_DYNAMIC', JSON.stringify(productsDb)); }
    function saveGroupsData(){ store.set('GGUMBI_GROUPS_DB', JSON.stringify(groupsDb)); }

    // =============================================
    // 제품 해석 도우미
    // =============================================
    const isBaby = p => p.type === 'babyroom';
    const isSplitSize = p => isBaby(p) && ['16P','18P','20P'].includes(p.babyroomSize);
    function boxLetter(p) {
        const m = String(p.boxRecommended || '').match(/([AB])\s*박스/i) || String(p.name).match(/_([AB])\s*$/i);
        return m ? m[1].toUpperCase() : null;
    }
    const cleanBox = s => String(s || '').replace(/\s*사용\s*$/,'').replace(/박스사용$/,'박스').trim();
    const baseName = p => String(p.name).replace(/_\d+p_[AB]\s*$/i, '').trim();
    function siblingOf(p) {
        const L = boxLetter(p); if (!L) return null;
        return productsDb.find(o => o.id !== p.id && isBaby(o) && baseName(o) === baseName(p) && boxLetter(o) && boxLetter(o) !== L) || null;
    }
    function tpuBox(p, q) {
        const th = parseInt(p.boxThreshold) || 2;
        return q <= th ? (p.boxSmallName || '2P 소형박스') : (p.boxLargeName || '6P 표준박스');
    }
    function lobbyBoxText(p) {
        if (isBaby(p)) return cleanBox(p.boxRecommended) || (p.babyroomSize + ' 박스');
        const s = p.boxSmallName, l = p.boxLargeName;
        return (!s || s === l) ? (l || '') : `${s} / ${l}`;
    }
    const isBigPart = name => /가드|도어/.test(name);
    const warnLines = p => String(p.warning || '').split('\n').map(s => s.replace(/^\s*[-•·]\s*/, '').trim())
        .filter(s => s && !/파란색\s*텍스트/.test(s));

    // =============================================
    // 관리자 모드
    // =============================================
    function toggleAdmin() {
        isAdmin = !isAdmin;
        store.set('GGUMBI_ADMIN_MODE', isAdmin ? '1' : '0');
        if (!isAdmin && groupEdit) toggleGroupEdit();
        applyAdmin();
        if (!$('view-detail').classList.contains('hidden')) renderDetail(); else renderLobby();
        toast(isAdmin ? '관리자 모드가 켜졌어요' : '작업자 모드로 돌아왔어요');
    }
    function applyAdmin() {
        $('admin-chip').classList.toggle('hidden', !isAdmin);
        $('admin-lobby').classList.toggle('hidden', !isAdmin);
        $('admin-toggle').textContent = isAdmin ? '관리자 모드 끄기' : '관리자 모드 켜기';
    }

    // =============================================
    // 로비
    // =============================================
    function prodRow(p) {
        const L = boxLetter(p);
        const meta = [];
        const bt = lobbyBoxText(p);
        if (bt) meta.push(`<span class="tag box">📦 ${esc(bt)}</span>`);
        if (L && isSplitSize(p)) meta.push(`<span class="tag ab">${L}박스</span>`);
        meta.push(`<span>${esc(p.code)}</span>`);
        const cb = groupEdit ? `<input type="checkbox" ${editSel.has(p.id) ? 'checked' : ''} tabindex="-1">` : '';
        return `<button class="prod" onclick="${groupEdit ? `toggleSel('${p.id}')` : `openProduct('${p.id}')`}">
            ${cb}
            <div class="zone"><small>랙</small>${esc(p.zone || '-')}</div>
            <div class="info"><div class="nm">${esc(p.name)}</div><div class="meta">${meta.join('')}</div></div>
            ${groupEdit ? '' : ICON_RIGHT}
        </button>`;
    }

    function renderLobby() {
        const box = $('product-list');
        const q = $('search-input').value.trim().toLowerCase();
        if (q) {
            const hit = productsDb.filter(p => [p.name, p.code, p.zone].some(v => String(v || '').toLowerCase().includes(q)));
            box.innerHTML = hit.length
                ? `<div class="sec-label">검색 결과 ${hit.length}개</div><div class="group open"><div class="group-body" style="border:0">${hit.map(prodRow).join('')}</div></div>`
                : `<div class="empty">'${esc(q)}'에 맞는 제품이 없어요</div>`;
            return;
        }
        const inGroup = new Set();
        let html = '';
        groupsDb.forEach(g => {
            const items = g.productIds.map(id => productsDb.find(p => p.id === id)).filter(Boolean);
            items.forEach(p => inGroup.add(p.id));
            if (!items.length) return;
            const open = groupEdit || !g.collapsed;
            html += `<div class="group ${open ? 'open' : ''}">
                <div class="group-h" role="button" onclick="toggleGroup('${g.id}')">
                    <span>${esc(g.name)}</span><span class="cnt">${items.length}</span>
                    ${isAdmin ? `<span class="del" onclick="deleteGroup('${g.id}',event)">그룹 삭제</span>` : ''}
                    ${ICON_DOWN}
                </div>
                <div class="group-body ${open ? '' : 'hidden'}">${items.map(prodRow).join('')}</div>
            </div>`;
        });
        const rest = productsDb.filter(p => !inGroup.has(p.id));
        if (rest.length) {
            html += `<div class="sec-label">${groupsDb.length ? '그룹 없는 제품' : '전체 제품'}</div>
                <div class="group open"><div class="group-body" style="border:0">${rest.map(prodRow).join('')}</div></div>`;
        }
        box.innerHTML = `<div class="stack">${html || '<div class="empty">등록된 제품이 없어요</div>'}</div>`;
    }

    function toggleGroup(id) {
        const g = groupsDb.find(x => x.id === id);
        if (g) { g.collapsed = !g.collapsed; saveGroupsData(); renderLobby(); }
    }
    function deleteGroup(id, e) {
        e.stopPropagation();
        if (!confirm('이 그룹을 삭제할까요? (제품은 그대로 남아요)')) return;
        groupsDb = groupsDb.filter(g => g.id !== id); saveGroupsData(); renderLobby(); toast('그룹을 삭제했어요');
    }
    function toggleGroupEdit() {
        groupEdit = !groupEdit; editSel.clear();
        $('group-toolbar').classList.toggle('hidden', !groupEdit);
        $('group-edit-btn').textContent = groupEdit ? '그룹 편집 닫기' : '그룹 편집';
        $('edit-count').textContent = '선택: 0개';
        if (!groupEdit) $('group-name-input').value = '';
        renderLobby();
    }
    function toggleSel(id) {
        editSel.has(id) ? editSel.delete(id) : editSel.add(id);
        $('edit-count').textContent = `선택: ${editSel.size}개`; renderLobby();
    }
    function selectAllEdit(on) {
        editSel = on ? new Set(productsDb.map(p => p.id)) : new Set();
        $('edit-count').textContent = `선택: ${editSel.size}개`; renderLobby();
    }
    function saveNewGroup() {
        const name = $('group-name-input').value.trim();
        if (!name) return toast('그룹 이름을 입력해 주세요');
        if (!editSel.size) return toast('그룹에 넣을 제품을 먼저 체크해 주세요');
        const ex = groupsDb.find(g => g.name === name);
        if (ex) editSel.forEach(id => { if (!ex.productIds.includes(id)) ex.productIds.push(id); });
        else groupsDb.push({ id: 'grp-' + Date.now(), name, productIds: [...editSel], collapsed: false });
        saveGroupsData(); toggleGroupEdit(); toast(`그룹 "${name}" 저장 완료`);
    }

    // =============================================
    // 상세 (작업자 화면)
    // =============================================
    function openProduct(id, fromQr) {
        const p = productsDb.find(x => x.id === id);
        if (!p) return;
        currentId = id;
        checked = new Set();
        matQty = parseInt(p.defaultQty) || 1;
        if (!fromQr) history.replaceState(null, '', location.pathname + '?product=' + encodeURIComponent(id));
        $('view-lobby').classList.add('hidden');
        $('view-detail').classList.remove('hidden');
        renderDetail();
        window.scrollTo(0, 0);
    }
    function goLobby() {
        currentId = null;
        history.replaceState(null, '', location.pathname);
        $('view-detail').classList.add('hidden');
        $('view-lobby').classList.remove('hidden');
        renderLobby();
        window.scrollTo(0, 0);
    }

    function checklistItems(p) {
        // [{key, name, qty, unit, bag, color}]
        if (isBaby(p)) {
            return (p.components || []).map((c, i) => ({
                key: 'c' + i, name: c.name, qty: parseInt(c.qty) || 0, unit: '개',
                bag: !isBigPart(c.name), color: c.color
            }));
        }
        const list = [{ key: 'mat', name: '매트 본품', qty: matQty, unit: '장', bag: false }];
        const scale = Math.ceil(matQty / (parseInt(p.defaultQty) || 6));
        (p.accessories || []).forEach((a, i) => {
            const base = parseInt(a.qty) || 0;
            list.push({ key: 'a' + i, name: a.name, qty: base ? base * scale : null, unit: '개', bag: true });
        });
        return list;
    }

    function itemHtml(it) {
        const on = checked.has(it.key);
        const c = it.color && it.color.bg ? `style="color:${esc(it.color.text)}"` : '';
        const q = it.qty === null
            ? `<span class="q check">수량 확인</span>`
            : `<span class="q">×${it.qty}<small>${it.unit}</small></span>`;
        return `<button class="item ${on ? 'on' : ''}" onclick="toggleCheck('${it.key}')" aria-pressed="${on}">
            <span class="ck">${ICON_CHECK}</span><span class="nm" ${on ? '' : c}>${esc(it.name)}</span>${q}
        </button>`;
    }

    function renderDetail() {
        const p = productsDb.find(x => x.id === currentId);
        if (!p) return goLobby();
        const baby = isBaby(p);
        const L = boxLetter(p);
        const sib = siblingOf(p);
        const items = checklistItems(p);
        const big = items.filter(i => !i.bag), bag = items.filter(i => i.bag);
        const done = items.filter(i => checked.has(i.key)).length;
        const all = items.length && done === items.length;
        const warns = warnLines(p);

        let h = `<div class="topbar">
            <button class="back" onclick="goLobby()"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round"><path d="m15 5-7 7 7 7"/></svg>전체 목록</button>
            ${isAdmin ? `<div class="btn-row"><button class="btn sm" onclick="openEditor(true)">✏️ 수정</button><button class="btn sm warn" onclick="deleteProduct()">삭제</button></div>` : ''}
        </div>
        <div class="card hero">
            <div class="rack"><small>랙 구역</small><b>${esc(p.zone || '-')}</b></div>
            <div><h1>${esc(p.name)}</h1><div class="code">${esc(p.code)}</div></div>
        </div>`;

        if (isSplitSize(p) && L) {
            const other = L === 'A' ? 'B' : 'A';
            h += `<div class="split"><b>🚨 2박스 분할 출고 제품</b>
                <p>이 화면은 <b style="display:inline;font-size:inherit">${L}박스</b> 구성이에요. ${other}박스도 따로 포장해야 해요.</p>
                ${sib ? `<button class="btn" onclick="openProduct('${sib.id}')">${other}박스 구성 보기 →</button>` : ''}
            </div>`;
        }

        // ① 박스
        h += `<div class="card boxcard"><div class="step-h"><span class="step-n">1</span>이 박스를 꺼내세요</div>`;
        if (!baby) {
            const max = parseInt(p.maxQty) || 12;
            h += `<div class="qty"><div class="lbl">주문 수량<small>최대 ${max}장까지 한 박스</small></div>
                <div class="stepper"><button onclick="changeQty(-1)" ${matQty <= 1 ? 'disabled' : ''} aria-label="줄이기">−</button><output>${matQty}</output><button onclick="changeQty(1)" ${matQty >= max ? 'disabled' : ''} aria-label="늘리기">+</button></div></div>`;
        }
        const boxName = baby ? (cleanBox(p.boxRecommended) || p.babyroomSize + ' 박스') : tpuBox(p, matQty);
        h += `<div class="boxname"><span class="ico">📦</span><div><b>${esc(boxName)}</b>${baby ? `<small>${esc(p.babyroomSize || '')} 세트</small>` : ''}</div></div></div>`;

        // 주의사항
        if (warns.length) {
            h += `<div class="caution"><h2>⚠️ 꼭 확인하세요</h2><ul>${warns.map(w => /^⭐/.test(w)
                ? `<li class="star">${esc(w)}</li>` : `<li>${esc(w)}</li>`).join('')}</ul></div>`;
        }

        // ② 체크리스트
        h += `<div class="card"><div class="step-h"><span class="step-n">2</span>담으면서 하나씩 누르세요</div>
            <div class="progress"><div class="bar"><i style="width:${items.length ? done / items.length * 100 : 0}%"></i></div><span class="num">${done} / ${items.length}</span></div>`;
        if (!items.length) h += `<div class="empty">등록된 구성품이 없어요</div>`;
        if (big.length) h += `<div class="sub-h">${baby ? '🧱 큰 부품 <small>· 박스에 바로</small>' : '🧱 매트 <small>· 박스에 바로</small>'}</div>${big.map(itemHtml).join('')}`;
        if (bag.length) h += `<div class="sub-h bag">🛍 ${baby ? '지퍼백에 넣을 부자재' : '함께 넣는 부자재'}</div>${bag.map(itemHtml).join('')}`;
        if (all) h += `<div class="done">✅ 모두 담았어요!<small>박스 봉합 후 출고하세요</small></div>`;
        if (done) h += `<button class="btn reset" onclick="checked.clear();renderDetail()">↺ 체크 초기화 (다음 주문)</button>`;
        h += `</div>`;

        if (p.photo) h += `<div class="card photo"><div class="step-h">📷 포장 완성 사진</div><img src="${esc(p.photo)}" alt="포장 예시 사진" loading="lazy"></div>`;

        if (isAdmin) {
            const url = location.href.split('?')[0] + '?product=' + encodeURIComponent(p.id);
            const qr = `https://api.qrserver.com/v1/create-qr-code/?size=300x300&margin=8&data=${encodeURIComponent(url)}`;
            h += `<div class="card"><div class="step-h">🔳 랙 부착용 QR</div>
                <div class="qr"><img src="${qr}" alt="QR 코드"><div style="min-width:0">
                <div style="font-size:14px">찍으면 바로 이 화면으로 열려요.</div>
                <div class="link">${esc(url)}</div>
                <div class="btn-row"><button class="btn sm" onclick="copyLink('${esc(url)}')">링크 복사</button><button class="btn sm primary" onclick="printLabel()">라벨 인쇄</button></div>
                </div></div></div>`;
        }
        $('view-detail').innerHTML = h;
    }

    function toggleCheck(key) {
        checked.has(key) ? checked.delete(key) : checked.add(key);
        if (navigator.vibrate) try { navigator.vibrate(15); } catch(e){}
        const y = window.scrollY; renderDetail(); window.scrollTo(0, y);
    }
    function changeQty(d) {
        const p = productsDb.find(x => x.id === currentId); if (!p) return;
        const max = parseInt(p.maxQty) || 12;
        matQty = Math.min(max, Math.max(1, matQty + d));
        checked.clear();
        const y = window.scrollY; renderDetail(); window.scrollTo(0, y);
    }
    function copyLink(u) {
        (navigator.clipboard ? navigator.clipboard.writeText(u) : Promise.reject()).then(() => toast('링크를 복사했어요'), () => toast(u));
    }
    function printLabel() {
        const p = productsDb.find(x => x.id === currentId); if (!p) return;
        const url = location.href.split('?')[0] + '?product=' + encodeURIComponent(p.id);
        const el = $('print-label');
        el.innerHTML = `<div class="z">랙 ${esc(p.zone)}</div><img alt="" src="https://api.qrserver.com/v1/create-qr-code/?size=400x400&margin=8&data=${encodeURIComponent(url)}"><div class="n">${esc(p.name)}</div><div class="c">${esc(p.code)}</div>`;
        const img = el.querySelector('img');
        const go = () => { document.body.classList.add('printing'); window.print(); setTimeout(() => document.body.classList.remove('printing'), 500); };
        img.complete ? go() : (img.onload = go, img.onerror = go);
    }

    // =============================================
    // 제품 편집 (관리자)
    // =============================================
    function toggleEditorType() {
        const t = $('input-type').value;
        $('ed-tpu').classList.toggle('hidden', t !== 'tpu-mat');
        $('ed-baby').classList.toggle('hidden', t !== 'babyroom');
    }
    function renderEdRows() {
        $('ed-acc').innerHTML = tmpAcc.map((a, i) => `<div class="row">
            <input type="text" value="${esc(a.name)}" placeholder="예: 고정 클립" oninput="tmpAcc[${i}].name=this.value">
            <input type="number" value="${esc(a.qty)}" oninput="tmpAcc[${i}].qty=parseInt(this.value)||0">
            <button class="btn sm warn" onclick="tmpAcc.splice(${i},1);renderEdRows()">삭제</button></div>`).join('') || '<p class="note">부자재 없음</p>';
        $('ed-comp').innerHTML = tmpComp.map((c, i) => {
            const ci = Math.max(0, COLOR_PALETTE.findIndex(x => c.color && x.text === c.color.text));
            return `<div class="row">
            <input type="text" value="${esc(c.name)}" placeholder="예: 750 가드" oninput="tmpComp[${i}].name=this.value">
            <input type="number" value="${esc(c.qty)}" oninput="tmpComp[${i}].qty=parseInt(this.value)||0">
            <button class="btn sm warn" onclick="tmpComp.splice(${i},1);renderEdRows()">삭제</button>
            <div style="display:flex;gap:5px;width:100%;padding:2px 0 6px">${COLOR_PALETTE.map((x, k) =>
                `<button class="sw ${k === ci ? 'sel' : ''}" title="${x.label}" style="background:${x.bg || '#fff'};border-color:${x.text}" onclick="tmpComp[${i}].color=COLOR_PALETTE[${k}];renderEdRows()"></button>`).join('')}</div></div>`;
        }).join('') || '<p class="note">구성품 없음</p>';
    }
    function openEditor(edit) {
        const p = edit ? productsDb.find(x => x.id === currentId) : null;
        $('editor-title').textContent = p ? '제품 수정' : '제품 추가';
        $('edit-original-id').value = p ? p.id : '';
        $('input-type').value = p ? (p.type || 'tpu-mat') : 'tpu-mat';
        $('input-code').value = p ? p.code : '';
        $('input-name').value = p ? p.name : '';
        $('input-zone').value = p ? p.zone : '';
        $('input-warning').value = p ? p.warning : '';
        $('input-photo').value = p ? (p.photo || '') : '';
        $('input-default-qty').value = p && !isBaby(p) ? p.defaultQty : 6;
        $('input-max-qty').value = p && !isBaby(p) ? (p.maxQty || 12) : 6;
        $('input-box-threshold').value = p && !isBaby(p) ? (p.boxThreshold || 2) : 2;
        $('input-box-small-name').value = p && !isBaby(p) ? (p.boxSmallName || '') : '2P 박스';
        $('input-box-large-name').value = p && !isBaby(p) ? (p.boxLargeName || '') : '6P 박스';
        $('input-babyroom-size').value = p && isBaby(p) ? (p.babyroomSize || '10P') : '10P';
        $('input-babyroom-box-name').value = p && isBaby(p) ? (p.boxRecommended || '') : '';
        tmpAcc = p && p.accessories ? JSON.parse(JSON.stringify(p.accessories)) : (p ? [] : [{ name: '전용 고정 클립', qty: 6 }]);
        tmpComp = p && p.components ? JSON.parse(JSON.stringify(p.components)) : (p ? [] : [
            { name: '640 가드', qty: 2, color: COLOR_PALETTE[0] }, { name: '750 도어', qty: 1, color: COLOR_PALETTE[0] },
            { name: '일자 커넥터', qty: 6, color: COLOR_PALETTE[1] }, { name: '코너 커넥터', qty: 4, color: COLOR_PALETTE[1] }]);
        toggleEditorType(); renderEdRows();
        $('editor').classList.remove('hidden');
    }
    function closeEditor() { $('editor').classList.add('hidden'); }
    function saveProduct() {
        const originalId = $('edit-original-id').value;
        const type = $('input-type').value;
        const code = $('input-code').value.trim(), name = $('input-name').value.trim();
        if (!code || !name) return toast('제품명과 바코드는 꼭 입력해 주세요');
        const d = { id: originalId || 'item-' + Date.now(), type, code, name, zone: $('input-zone').value.trim(), warning: $('input-warning').value.trim() };
        const photo = $('input-photo').value.trim(); if (photo) d.photo = photo;
        if (type === 'babyroom') {
            d.babyroomSize = $('input-babyroom-size').value;
            d.boxRecommended = $('input-babyroom-box-name').value.trim() || `${d.babyroomSize} 박스 사용`;
            d.components = tmpComp.filter(c => c.name.trim());
        } else {
            d.defaultQty = parseInt($('input-default-qty').value) || 6;
            d.maxQty = parseInt($('input-max-qty').value) || 12;
            d.boxThreshold = parseInt($('input-box-threshold').value) || 2;
            d.boxSmallName = $('input-box-small-name').value.trim();
            d.boxLargeName = $('input-box-large-name').value.trim();
            d.accessories = tmpAcc.filter(a => a.name.trim());
        }
        if (originalId) { const i = productsDb.findIndex(x => x.id === originalId); if (i > -1) productsDb[i] = d; toast('수정했어요 · index.html 저장을 잊지 마세요'); }
        else { productsDb.push(d); toast('새 제품을 추가했어요'); }
        saveProductsData(); closeEditor();
        if (originalId) { currentId = originalId; matQty = parseInt(d.defaultQty) || 1; checked.clear(); renderDetail(); }
        else goLobby();
    }
    function deleteProduct() {
        if (!confirm('이 제품 가이드를 삭제할까요?')) return;
        productsDb = productsDb.filter(x => x.id !== currentId);
        saveProductsData(); toast('삭제했어요'); goLobby();
    }

    // =============================================
    // index.html 저장 (기존 방식과 동일: 데이터 블록만 교체)
    // =============================================
    async function downloadUpdatedHtml() {
        try {
            toast('파일 만드는 중...');
            const response = await fetch(window.location.href.split('?')[0], { cache: 'no-store' });
            const htmlText = await response.text();
            const startMarker = "/* DATA_PLACEHOLDER" + "_START */";
            const endMarker = "/* DATA_PLACEHOLDER" + "_END */";
            const s = htmlText.indexOf(startMarker), e = htmlText.indexOf(endMarker);
            if (s === -1 || e === -1) return toast('데이터 위치 표시가 없어 저장할 수 없어요');
            const db = "\n    const initialProductsDb = " + JSON.stringify(productsDb, null, 6) + ";\n" +
                       "    const initialGroupsDb = " + JSON.stringify(groupsDb, null, 6) + ";\n    ";
            let out = htmlText.substring(0, s + startMarker.length) + db + htmlText.substring(e);
            out = out.replace(/const CLIENT_VERSION = "[^"]*";/, 'const CLIENT_VERSION = "' + Date.now() + '";');
            const a = document.createElement('a');
            a.href = URL.createObjectURL(new Blob([out], { type: 'text/html;charset=utf-8' }));
            a.download = 'index.html'; a.click();
            toast('index.html 저장 완료 → GitHub에 올려주세요');
        } catch (err) { toast('파일 만들기에 실패했어요'); }
    }

    let toastTimer;
    function toast(msg) {
        const t = $('toast'); t.textContent = msg; t.classList.add('show');
        clearTimeout(toastTimer); toastTimer = setTimeout(() => t.classList.remove('show'), 2600);
    }

    window.addEventListener('DOMContentLoaded', () => {
        loadProductsData();
        isAdmin = store.get('GGUMBI_ADMIN_MODE') === '1';
        applyAdmin();
        renderLobby();
        const key = new URLSearchParams(location.search).get('product');
        if (key) {
            const p = productsDb.find(x => x.id === key || x.code === key);
            if (p) openProduct(p.id, true);
        }
    });
</script>
</body>
</html>
