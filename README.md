[gemini-code-1789217679670.html](https://github.com/user-attachments/files/32143887/gemini-code-1789217679670.html)[Uplo<!DOCTYPE html>
<html lang="zh-TW" class="h-full bg-gray-50">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>警政鼠 - 同業交流與單位評價平台</title>
  
  <!-- Tailwind CSS -->
  <script src="https://cdn.tailwindcss.com"></script>
  <script>
    tailwind.config = {
      theme: {
        extend: {
          colors: {
            jp: {
              bg: '#FAFAFA',
              card: '#FFFFFF',
              border: '#E5E7EB',
              borderLight: '#F3F4F6',
              textMain: '#1F2937',
              textMuted: '#6B7280',
              textLight: '#9CA3AF',
              accent: '#374151',
              hover: '#F9FAFB'
            }
          }
        }
      }
    }
  </script>
  
  <style>
    body {
      background-color: #FAFAFA;
      color: #1F2937;
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", "PingFang TC", "Microsoft JhengHei", sans-serif;
    }
    ::-webkit-scrollbar { width: 6px; height: 6px; }
    ::-webkit-scrollbar-track { background: transparent; }
    ::-webkit-scrollbar-thumb { background: #E5E7EB; border-radius: 9999px; }
    ::-webkit-scrollbar-thumb:hover { background: #D1D5DB; }
    .jp-card {
      background-color: #FFFFFF;
      border: 1px solid #E5E7EB;
      border-radius: 0.75rem;
      transition: all 0.2s;
    }
    .jp-card:hover { border-color: #D1D5DB; }
    .jp-button-primary {
      background-color: #1F2937;
      color: #FFFFFF;
      border-radius: 0.5rem;
      transition: background-color 0.15s, transform 0.15s;
    }
    .jp-button-primary:hover { background-color: #374151; }
    .jp-button-primary:active { transform: scale(0.98); }
    .jp-button-secondary {
      background-color: #FFFFFF;
      color: #374151;
      border: 1px solid #E5E7EB;
      border-radius: 0.5rem;
      transition: background-color 0.15s, border-color 0.15s;
    }
    .jp-button-secondary:hover { background-color: #F9FAFB; border-color: #D1D5DB; }
    .jp-tag {
      background-color: #F3F4F6;
      color: #4B5563;
      font-size: 0.75rem;
      padding: 0.25rem 0.625rem;
      border-radius: 0.375rem;
    }
    .fade-in { animation: fadeIn 0.25s ease-out forwards; }
    @keyframes fadeIn { from { opacity: 0; transform: translateY(4px); } to { opacity: 1; transform: translateY(0); } }
    .hidden-tab { display: none !important; }
  </style>
</head>
<body class="h-full flex flex-col md:flex-row antialiased select-none text-gray-800">

  <!-- Desktop Fixed Left Sidebar -->
  <aside class="hidden md:flex md:w-64 bg-white border-r border-gray-200 flex-col justify-between h-screen sticky top-0 flex-shrink-0 z-30">
    <div class="p-6">
      <div class="flex items-center space-x-3 cursor-pointer group mb-10" onclick="switchTab('home')">
        <svg class="w-10 h-10 transition-transform duration-200 group-hover:scale-105" viewBox="0 0 100 100" fill="none">
          <circle cx="28" cy="38" r="16" fill="#E5E7EB" stroke="#4B5563" stroke-width="3"/>
          <circle cx="28" cy="38" r="9" fill="#F3F4F6"/>
          <circle cx="72" cy="38" r="16" fill="#E5E7EB" stroke="#4B5563" stroke-width="3"/>
          <circle cx="72" cy="38" r="9" fill="#F3F4F6"/>
          <ellipse cx="50" cy="58" rx="30" ry="26" fill="#F9FAFB" stroke="#4B5563" stroke-width="3"/>
          <ellipse cx="40" cy="56" rx="2.5" ry="3.5" fill="#374151"/>
          <ellipse cx="60" cy="56" rx="2.5" ry="3.5" fill="#374151"/>
          <ellipse cx="50" cy="65" rx="3.5" ry="2.5" fill="#4B5563"/>
        </svg>
        <div>
          <h1 class="font-bold text-xl tracking-wider text-gray-900 leading-none">警政鼠</h1>
          <p class="text-[10px] text-gray-400 mt-1 tracking-wider">同業交流 × 單位評價</p>
        </div>
      </div>
      <nav class="space-y-1">
        <button id="nav-desktop-forum" onclick="switchTab('forum')" class="nav-item w-full flex items-center px-3.5 py-3 text-sm font-medium rounded-lg text-gray-700 hover:bg-gray-100">討論區與評價</button>
        <button id="nav-desktop-admin" onclick="switchTab('admin')" class="nav-item w-full flex items-center px-3.5 py-3 text-sm font-medium rounded-lg text-gray-700 hover:bg-gray-100">管理審核後台</button>
      </nav>
    </div>
  </aside>

  <!-- Main Scrollable Content Area -->
  <main class="flex-1 overflow-y-auto min-h-screen pb-16 flex flex-col justify-between">
    <div class="max-w-4xl w-full mx-auto px-4 sm:px-6 py-6 md:py-10">

      <!-- SECTION: HOME -->
      <section id="tab-home" class="fade-in space-y-12">
        <div class="text-center py-16 space-y-6">
          <h2 class="text-3xl font-bold tracking-wider text-gray-900">歡迎來到警政鼠</h2>
          <p class="text-gray-500">匿名同業交流社群 × 單位星等評價</p>
          <button onclick="switchTab('forum')" class="jp-button-primary px-5 py-2.5 text-sm font-medium inline-block mx-auto">進入討論區</button>
        </div>
      </section>

      <!-- SECTION: FORUM -->
      <section id="tab-forum" class="hidden-tab fade-in space-y-8">
        <div class="flex items-center justify-between">
          <h2 class="text-xl font-bold text-gray-900 tracking-wide">討論區與單位評價</h2>
          <button onclick="openAddUnitModal()" class="jp-button-primary px-3.5 py-2 text-xs font-medium">新增派出所/單位</button>
        </div>

        <div class="flex border-b border-gray-200 text-sm font-medium">
          <button id="subtab-btn-units" onclick="switchForumSubtab('units')" class="py-2.5 px-4 text-gray-900 border-b-2 border-gray-800 font-bold">單位評價列表</button>
          <button id="subtab-btn-threads" onclick="switchForumSubtab('threads')" class="py-2.5 px-4 text-gray-500 border-b-2 border-transparent hover:text-gray-800">匿名討論主題</button>
        </div>

        <!-- UNITS LIST -->
        <div id="forum-subtab-units" class="space-y-4">
          <div id="unit-cards-container" class="grid grid-cols-1 md:grid-cols-2 gap-4"></div>
        </div>

        <!-- THREADS LIST -->
        <div id="forum-subtab-threads" class="hidden-tab space-y-4">
          <div class="flex justify-between items-center">
            <span class="text-xs text-gray-500">此區內容公開討論，自由選擇匿名或署名</span>
            <button onclick="openNewThreadModal()" class="jp-button-primary px-3.5 py-1.5 text-xs">發起討論</button>
          </div>
          <div id="threads-container" class="space-y-3"></div>
        </div>
      </section>

      <!-- SECTION: ADMIN PANEL -->
      <section id="tab-admin" class="hidden-tab fade-in space-y-6">
        <div class="bg-gray-100 p-4 rounded-xl border border-gray-200 flex justify-between items-center">
          <h2 class="text-base font-bold text-gray-800">創始人審核後台 (待審核清單)</h2>
          <button onclick="logoutAdmin()" class="bg-red-50 text-red-600 border border-red-200 hover:bg-red-100 px-3 py-1.5 text-xs rounded-lg">登出</button>
        </div>
        <div id="admin-pending-reviews-list" class="space-y-3"></div>
      </section>

      <!-- ================= MODALS ================= -->
      <!-- ADMIN LOGIN MODAL -->
      <div id="admin-login-modal" class="fixed inset-0 z-50 bg-black/40 backdrop-blur-sm hidden flex items-center justify-center p-4">
        <div class="bg-white max-w-sm w-full rounded-2xl border border-gray-200 p-6 space-y-5 shadow-lg">
          <h3 class="text-base font-bold text-center">創始人身分驗證</h3>
          <input type="password" id="admin-password-input" placeholder="預設密碼：admin888" class="w-full p-2.5 bg-gray-50 border border-gray-200 rounded-lg text-sm">
          <div class="flex justify-end space-x-2">
            <button onclick="closeAdminLoginModal()" class="jp-button-secondary px-4 py-2 text-xs">取消</button>
            <button onclick="verifyAdminPassword()" class="jp-button-primary px-4 py-2 text-xs">登入</button>
          </div>
        </div>
      </div>

      <!-- UNIT DETAIL MODAL -->
      <div id="unit-detail-modal" class="fixed inset-0 z-50 bg-black/30 backdrop-blur-sm hidden flex items-center justify-center p-4">
        <div class="bg-white max-w-2xl w-full rounded-2xl border border-gray-200 p-6 max-h-[90vh] overflow-y-auto space-y-6">
          <div class="flex justify-between items-start border-b border-gray-100 pb-4">
            <h3 id="modal-unit-name" class="text-xl font-bold text-gray-900">單位名稱</h3>
            <button onclick="closeUnitDetailModal()" class="text-gray-400 hover:text-gray-600">✕</button>
          </div>
          <div class="bg-gray-50 p-4 rounded-xl flex items-center justify-between">
            <div class="flex space-x-3 items-center">
              <span id="modal-unit-stars-graphic" class="text-lg text-gray-700 tracking-widest">★★★★☆</span>
              <span id="modal-unit-score" class="text-2xl font-bold text-gray-900">4.0</span>
            </div>
            <button onclick="openAddReviewModal()" class="jp-button-primary px-4 py-2 text-xs font-medium">給予評價 / 留言</button>
          </div>
          <div id="modal-unit-reviews-list" class="space-y-3"></div>
        </div>
      </div>

      <!-- ADD REVIEW MODAL (加上了身分選擇功能) -->
      <div id="add-review-modal" class="fixed inset-0 z-50 bg-black/30 backdrop-blur-sm hidden flex items-center justify-center p-4">
        <div class="bg-white max-w-md w-full rounded-xl border border-gray-200 p-6 space-y-5">
          <div class="flex justify-between items-center border-b border-gray-100 pb-3">
            <h3 id="add-review-unit-title" class="text-base font-bold text-gray-900">發表評價</h3>
            <button onclick="closeAddReviewModal()" class="text-gray-400">✕</button>
          </div>

          <!-- 身分選擇區塊 (新增) -->
          <div class="space-y-2 bg-gray-50 p-3 rounded-lg border border-gray-100">
            <label class="block text-xs font-bold text-gray-700">發布身分</label>
            <div class="flex items-center space-x-4 mt-1">
              <label class="inline-flex items-center cursor-pointer">
                <input type="radio" name="reviewIdentity" value="anonymous" checked class="form-radio h-4 w-4" onchange="document.getElementById('reviewCustomNameInput').classList.add('hidden')">
                <span class="ml-1.5 text-sm text-gray-700">1. 匿名</span>
              </label>
              <label class="inline-flex items-center cursor-pointer">
                <input type="radio" name="reviewIdentity" value="custom" class="form-radio h-4 w-4" onchange="document.getElementById('reviewCustomNameInput').classList.remove('hidden'); document.getElementById('reviewCustomNameInput').focus();">
                <span class="ml-1.5 text-sm text-gray-700">2. 名稱：</span>
              </label>
              <input type="text" id="reviewCustomNameInput" placeholder="(請填寫名稱)" class="hidden w-32 p-1.5 bg-white border border-gray-300 rounded text-xs focus:outline-none focus:border-gray-500">
            </div>
          </div>

          <div class="space-y-2">
            <label class="block text-xs font-medium text-gray-700">綜合星等評分</label>
            <div class="flex items-center space-x-2" id="star-picker">
              <button onclick="setReviewRating(1)" class="star-btn text-2xl text-gray-300">★</button>
              <button onclick="setReviewRating(2)" class="star-btn text-2xl text-gray-300">★</button>
              <button onclick="setReviewRating(3)" class="star-btn text-2xl text-gray-300">★</button>
              <button onclick="setReviewRating(4)" class="star-btn text-gray-700 text-2xl">★</button>
              <button onclick="setReviewRating(5)" class="star-btn text-2xl text-gray-300">★</button>
              <span id="rating-number-display" class="text-sm font-bold ml-2">4.0</span>
            </div>
          </div>
          <div class="space-y-2">
            <label class="block text-xs font-medium text-gray-700">文字評論（選填）</label>
            <textarea id="review-text-input" rows="3" placeholder="分享真實工作環境心得..." class="w-full p-3 bg-gray-50 border border-gray-200 rounded-lg text-sm resize-none focus:outline-none focus:border-gray-400"></textarea>
          </div>
          <div class="flex justify-end space-x-2">
            <button onclick="closeAddReviewModal()" class="jp-button-secondary px-4 py-2 text-xs">取消</button>
            <button onclick="submitReview()" class="jp-button-primary px-4 py-2 text-xs">送出評價 (需審核)</button>
          </div>
        </div>
      </div>

      <!-- NEW THREAD MODAL (加上了身分選擇功能) -->
      <div id="new-thread-modal" class="fixed inset-0 z-50 bg-black/30 backdrop-blur-sm hidden flex items-center justify-center p-4">
        <div class="bg-white max-w-lg w-full rounded-xl border border-gray-200 p-6 space-y-4">
          <div class="flex justify-between items-center border-b border-gray-100 pb-3">
            <h3 class="text-base font-bold text-gray-900">發起討論</h3>
            <button onclick="closeNewThreadModal()" class="text-gray-400">✕</button>
          </div>

          <!-- 身分選擇區塊 (新增) -->
          <div class="space-y-2 bg-gray-50 p-3 rounded-lg border border-gray-100">
            <label class="block text-xs font-bold text-gray-700">發布身分</label>
            <div class="flex items-center space-x-4 mt-1">
              <label class="inline-flex items-center cursor-pointer">
                <input type="radio" name="threadIdentity" value="anonymous" checked class="form-radio h-4 w-4" onchange="document.getElementById('threadCustomNameInput').classList.add('hidden')">
                <span class="ml-1.5 text-sm text-gray-700">1. 匿名</span>
              </label>
              <label class="inline-flex items-center cursor-pointer">
                <input type="radio" name="threadIdentity" value="custom" class="form-radio h-4 w-4" onchange="document.getElementById('threadCustomNameInput').classList.remove('hidden'); document.getElementById('threadCustomNameInput').focus();">
                <span class="ml-1.5 text-sm text-gray-700">2. 名稱：</span>
              </label>
              <input type="text" id="threadCustomNameInput" placeholder="(請填寫名稱)" class="hidden w-32 p-1.5 bg-white border border-gray-300 rounded text-xs focus:outline-none focus:border-gray-500">
            </div>
          </div>

          <div class="space-y-3">
            <div>
              <label class="block text-xs font-medium text-gray-700 mb-1">標題</label>
              <input type="text" id="thread-title-input" class="w-full p-2.5 bg-gray-50 border border-gray-200 rounded-lg text-sm focus:outline-none focus:border-gray-400">
            </div>
            <div>
              <label class="block text-xs font-medium text-gray-700 mb-1">內文</label>
              <textarea id="thread-content-input" rows="4" class="w-full p-2.5 bg-gray-50 border border-gray-200 rounded-lg text-sm focus:outline-none focus:border-gray-400 resize-none"></textarea>
            </div>
          </div>
          <div class="flex justify-end space-x-2 pt-2">
            <button onclick="closeNewThreadModal()" class="jp-button-secondary px-4 py-2 text-xs">取消</button>
            <button onclick="submitNewThread()" class="jp-button-primary px-4 py-2 text-xs">發表文章</button>
          </div>
        </div>
      </div>

      <!-- ADD UNIT MODAL (簡化版) -->
      <div id="add-unit-modal" class="fixed inset-0 z-50 bg-black/30 backdrop-blur-sm hidden flex items-center justify-center p-4">
        <div class="bg-white max-w-md w-full rounded-xl p-6 space-y-4">
          <h3 class="font-bold">申請新增單位</h3>
          <input type="text" id="add-unit-region-input" placeholder="地區 (例: 台北市)" class="w-full p-2 border rounded text-sm">
          <input type="text" id="add-unit-name-input" placeholder="名稱 (例: 中山分局)" class="w-full p-2 border rounded text-sm">
          <div class="flex justify-end space-x-2"><button onclick="closeAddUnitModal()" class="p-2 text-xs">取消</button><button onclick="submitNewUnit()" class="jp-button-primary p-2 text-xs">送出申請</button></div>
        </div>
      </div>

      <!-- Toast Notification Alert -->
      <div id="toast" class="fixed bottom-6 right-6 z-50 bg-gray-900 text-white text-xs px-4 py-3 rounded-lg shadow-lg hidden flex items-center space-x-2">
        <span id="toast-message">訊息</span>
      </div>
    </div>
  </main>

  <script>
    // 狀態管理
    const state = {
      isAdminAuthenticated: false,
      adminPassword: 'admin888',
      activeUnitId: null,
      selectedRating: 4,
      units: [
        { id: 'u1', name: '信義分局 三張犁派出所', region: '台北市', ratingSum: 16, ratingCount: 4, reviews: [{id:'r1', author:'學長A', rating:4, text:'氣氛不錯', date:'昨天'}] }
      ],
      threads: [
        { id: 't1', title: '有學長待過中正一分局嗎？', content: '請問勤務會不會很重？', author: '阿明', date: '2天前', replies: 3 }
      ],
      pendingSubmissions: []
    };

    function getStarGraphic(score) {
      let str = ''; for (let i = 1; i <= 5; i++) str += i <= Math.round(score) ? '★' : '☆'; return str;
    }

    // 切換 Tab
    function switchTab(tabId) {
      if (tabId === 'admin' && !state.isAdminAuthenticated) { openAdminLoginModal(); return; }
      ['home', 'forum', 'admin'].forEach(t => {
        const el = document.getElementById(`tab-${t}`);
        if (el) el.classList.toggle('hidden-tab', t !== tabId);
      });
      if (tabId === 'forum') renderForumUnits();
      if (tabId === 'admin') renderAdminPanel();
    }
    
    function switchForumSubtab(subtab) {
      document.getElementById('forum-subtab-units').classList.toggle('hidden-tab', subtab !== 'units');
      document.getElementById('forum-subtab-threads').classList.toggle('hidden-tab', subtab !== 'threads');
      if (subtab === 'units') renderForumUnits();
      else renderForumThreads();
    }

    // 渲染函數
    function renderForumUnits() {
      const c = document.getElementById('unit-cards-container');
      c.innerHTML = state.units.map(u => {
        const avg = u.ratingCount > 0 ? (u.ratingSum / u.ratingCount).toFixed(1) : '0.0';
        return `
          <div onclick="openUnitDetailModal('${u.id}')" class="jp-card p-5 cursor-pointer">
            <span class="jp-tag">${u.region}</span>
            <h3 class="font-bold text-base mt-2">${u.name}</h3>
            <div class="text-sm mt-1 text-gray-700">${getStarGraphic(avg)} <span class="font-bold">${avg}</span> (${u.ratingCount}評分)</div>
          </div>
        `;
      }).join('');
    }

    function renderForumThreads() {
      document.getElementById('threads-container').innerHTML = state.threads.map(t => `
        <div class="jp-card p-4 space-y-2">
          <h4 class="font-bold text-gray-900">${t.title}</h4>
          <p class="text-xs text-gray-600">${t.content}</p>
          <div class="text-[11px] text-gray-400 border-t pt-2 mt-2">發布者：${t.author} · ${t.date}</div>
        </div>
      `).join('');
    }

    function renderAdminPanel() {
      const c = document.getElementById('admin-pending-reviews-list');
      if (state.pendingSubmissions.length === 0) { c.innerHTML = '<p class="text-sm text-gray-400">無待審核項目</p>'; return; }
      c.innerHTML = state.pendingSubmissions.map(item => `
        <div class="jp-card p-4">
          <div class="text-xs font-bold text-blue-600 mb-1">[待審核評論] ${item.unitName} - 來自：${item.author}</div>
          <p class="text-sm">評分：${item.rating}星 | 內容：${item.text}</p>
          <div class="mt-3 flex space-x-2">
            <button onclick="approveSubmission('${item.id}')" class="jp-button-primary px-3 py-1 text-xs">通過</button>
            <button onclick="rejectSubmission('${item.id}')" class="jp-button-secondary px-3 py-1 text-xs">拒絕</button>
          </div>
        </div>
      `).join('');
    }

    // Modal 邏輯
    function openUnitDetailModal(id) {
      state.activeUnitId = id;
      const u = state.units.find(x => x.id === id);
      const avg = u.ratingCount > 0 ? (u.ratingSum / u.ratingCount).toFixed(1) : '0.0';
      document.getElementById('modal-unit-name').innerText = u.name;
      document.getElementById('modal-unit-stars-graphic').innerText = getStarGraphic(avg);
      document.getElementById('modal-unit-score').innerText = avg;
      document.getElementById('modal-unit-reviews-list').innerHTML = u.reviews.map(r => `
        <div class="bg-gray-50 p-3 rounded text-sm">
          <div class="flex justify-between font-bold text-xs text-gray-700 mb-1">
            <span>${r.author}</span><span class="text-gray-400">${r.date}</span>
          </div>
          <div class="text-xs">${getStarGraphic(r.rating)}</div>
          <p class="mt-1">${r.text}</p>
        </div>
      `).join('');
      document.getElementById('unit-detail-modal').classList.remove('hidden');
    }
    function closeUnitDetailModal() { document.getElementById('unit-detail-modal').classList.add('hidden'); }

    // 【核心新增功能】取得使用者選擇的身分名稱
    function getAuthorName(type) {
      const radio = document.querySelector(`input[name="${type}Identity"]:checked`);
      if (radio && radio.value === 'custom') {
        const name = document.getElementById(`${type}CustomNameInput`).value.trim();
        return name !== '' ? name : '匿名同仁'; // 如果選了名稱卻沒打字，預設匿名
      }
      return '匿名同仁'; // 選項1預設
    }

    function openAddReviewModal() {
      document.querySelector('input[name="reviewIdentity"][value="anonymous"]').checked = true;
      document.getElementById('reviewCustomNameInput').classList.add('hidden');
      document.getElementById('reviewCustomNameInput').value = '';
      document.getElementById('review-text-input').value = '';
      setReviewRating(4);
      document.getElementById('add-review-modal').classList.remove('hidden');
    }
    function closeAddReviewModal() { document.getElementById('add-review-modal').classList.add('hidden'); }
    function setReviewRating(r) {
      state.selectedRating = r;
      document.getElementById('rating-number-display').innerText = r.toFixed(1);
      const btns = document.querySelectorAll('#star-picker .star-btn');
      btns.forEach((b, i) => { b.className = `star-btn text-2xl ${i < r ? 'text-gray-700' : 'text-gray-300'}` });
    }

    // 送出評價 (加入作者名稱)
    function submitReview() {
      const u = state.units.find(x => x.id === state.activeUnitId);
      const txt = document.getElementById('review-text-input').value.trim();
      const authorName = getAuthorName('review'); // <--- 讀取身分

      u.ratingSum += state.selectedRating;
      u.ratingCount += 1;
      
      if (txt) {
        state.pendingSubmissions.push({
          id: 'ps_'+Date.now(), type: 'review', unitId: u.id, unitName: u.name,
          rating: state.selectedRating, text: txt, author: authorName // <--- 存入資料庫
        });
        showToast('評論已送出，待審核後公開');
      } else {
        showToast('星等已紀錄！');
      }
      closeAddReviewModal(); openUnitDetailModal(u.id); renderForumUnits();
    }

    function openNewThreadModal() {
      document.querySelector('input[name="threadIdentity"][value="anonymous"]').checked = true;
      document.getElementById('threadCustomNameInput').classList.add('hidden');
      document.getElementById('threadCustomNameInput').value = '';
      document.getElementById('thread-title-input').value = '';
      document.getElementById('thread-content-input').value = '';
      document.getElementById('new-thread-modal').classList.remove('hidden');
    }
    function closeNewThreadModal() { document.getElementById('new-thread-modal').classList.add('hidden'); }
    
    // 送出討論 (加入作者名稱)
    function submitNewThread() {
      const title = document.getElementById('thread-title-input').value;
      const content = document.getElementById('thread-content-input').value;
      const authorName = getAuthorName('thread'); // <--- 讀取身分

      if(!title) return showToast('請填寫標題');
      state.threads.unshift({ id: 't_'+Date.now(), title, content, author: authorName, date: '剛剛', replies: 0 }); // <--- 存入資料庫
      closeNewThreadModal(); renderForumThreads(); showToast('討論已發布！');
    }

    // 審核功能
    function approveSubmission(id) {
      const idx = state.pendingSubmissions.findIndex(p => p.id === id);
      const item = state.pendingSubmissions[idx];
      const u = state.units.find(x => x.id === item.unitId);
      u.reviews.unshift({ id: 'r_'+Date.now(), author: item.author, rating: item.rating, text: item.text, date: '剛剛' });
      state.pendingSubmissions.splice(idx, 1);
      renderAdminPanel(); showToast('審核通過');
    }
    function rejectSubmission(id) {
      state.pendingSubmissions = state.pendingSubmissions.filter(p => p.id !== id);
      renderAdminPanel(); showToast('已拒絕');
    }

    // 登入登出與工具
    function openAdminLoginModal() { document.getElementById('admin-login-modal').classList.remove('hidden'); }
    function closeAdminLoginModal() { document.getElementById('admin-login-modal').classList.add('hidden'); }
    function verifyAdminPassword() {
      if(document.getElementById('admin-password-input').value === state.adminPassword) {
        state.isAdminAuthenticated = true; closeAdminLoginModal(); switchTab('admin'); showToast('進入管理後台');
      } else { showToast('密碼錯誤'); }
    }
    function logoutAdmin() { state.isAdminAuthenticated = false; switchTab('home'); showToast('已登出'); }
    function showToast(msg) {
      const t = document.getElementById('toast');
      document.getElementById('toast-message').innerText = msg;
      t.classList.remove('hidden'); setTimeout(() => t.classList.add('hidden'), 2500);
    }
    
    // 單位新增 Modal
    function openAddUnitModal() { document.getElementById('add-unit-modal').classList.remove('hidden'); }
    function closeAddUnitModal() { document.getElementById('add-unit-modal').classList.add('hidden'); }
    function submitNewUnit() { showToast('單位新增申請已送出'); closeAddUnitModal(); }

    // 初始化
    window.onload = () => switchTab('home');
  </script>
</body>
</html>ading gemini-code-1789217679670.html…]()
