<!DOCTYPE html>
<html lang="en" data-theme="light">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>MyMoney by AKASH BJ — Personal Tracker</title>
  <meta name="description" content="Smart personal finance tracker with AI Money Coach" />
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800;900&family=JetBrains+Mono:wght@400;600;700&display=swap" rel="stylesheet" />
  <link rel="stylesheet" href="style.css" />
</head>
<body>

  <!-- Ambient background -->
  <div class="ambient-bg">
    <div class="ambient-orb orb-1"></div>
    <div class="ambient-orb orb-2"></div>
    <div class="ambient-orb orb-3"></div>
  </div>

  <div class="app-shell">

    <!-- ══════════════════════════════════════
         HEADER
    ══════════════════════════════════════ -->
    <header class="app-header">
      <div class="header-brand">
        <div class="brand-logo">
          <span class="logo-letter">M</span>
          <div class="logo-pulse"></div>
        </div>
        <div class="brand-text">
          <h1 class="brand-name">MyMoney</h1>
          <p class="brand-sub">by AKASH BJ &nbsp;·&nbsp; Personal Tracker</p>
        </div>
      </div>
      <div class="header-actions">
        <button class="icon-btn" id="themeToggle" title="Toggle theme" aria-label="Toggle theme">
          <svg class="icon-sun" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="5"/><line x1="12" y1="1" x2="12" y2="3"/><line x1="12" y1="21" x2="12" y2="23"/><line x1="4.22" y1="4.22" x2="5.64" y2="5.64"/><line x1="18.36" y1="18.36" x2="19.78" y2="19.78"/><line x1="1" y1="12" x2="3" y2="12"/><line x1="21" y1="12" x2="23" y2="12"/><line x1="4.22" y1="19.78" x2="5.64" y2="18.36"/><line x1="18.36" y1="5.64" x2="19.78" y2="4.22"/></svg>
          <svg class="icon-moon" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" style="display:none"><path d="M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z"/></svg>
        </button>
        <button class="icon-btn" id="exportBtn" title="Export data" aria-label="Export data">
          <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"/><polyline points="7 10 12 15 17 10"/><line x1="12" y1="15" x2="12" y2="3"/></svg>
        </button>
        <button class="icon-btn danger" id="clearAllBtn" title="Clear all data" aria-label="Clear all data">
          <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="3 6 5 6 21 6"/><path d="M19 6l-1 14a2 2 0 0 1-2 2H8a2 2 0 0 1-2-2L5 6"/><path d="M10 11v6"/><path d="M14 11v6"/></svg>
        </button>
      </div>
    </header>

    <!-- ══════════════════════════════════════
         BALANCE CARD
    ══════════════════════════════════════ -->
    <section class="section-balance">
      <div class="balance-card">
        <div class="balance-top">
          <div class="balance-left">
            <p class="balance-label">Total Balance</p>
            <div class="balance-amount" id="balanceAmount">₹0.00</div>
            <div class="balance-change" id="balanceChange"></div>
          </div>
          <div class="balance-ring" id="balanceRing">
            <svg viewBox="0 0 36 36" class="ring-svg">
              <path class="ring-bg-path" d="M18 2.0845 a 15.9155 15.9155 0 0 1 0 31.831 a 15.9155 15.9155 0 0 1 0 -31.831"/>
              <path class="ring-fill-path" id="ringFill" stroke-dasharray="0, 100" d="M18 2.0845 a 15.9155 15.9155 0 0 1 0 31.831 a 15.9155 15.9155 0 0 1 0 -31.831"/>
            </svg>
            <div class="ring-label">
              <span class="ring-pct" id="ringPct">0%</span>
              <span class="ring-sub">saved</span>
            </div>
          </div>
        </div>
        <div class="balance-stats">
          <div class="bstat income-stat">
            <div class="bstat-icon inc-icon">
              <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><line x1="12" y1="19" x2="12" y2="5"/><polyline points="5 12 12 5 19 12"/></svg>
            </div>
            <div>
              <p class="bstat-label">Income</p>
              <p class="bstat-value inc-val" id="totalIncome">₹0.00</p>
            </div>
          </div>
          <div class="bstat-sep"></div>
          <div class="bstat expense-stat">
            <div class="bstat-icon exp-icon">
              <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><line x1="12" y1="5" x2="12" y2="19"/><polyline points="19 12 12 19 5 12"/></svg>
            </div>
            <div>
              <p class="bstat-label">Expenses</p>
              <p class="bstat-value exp-val" id="totalExpense">₹0.00</p>
            </div>
          </div>
          <div class="bstat-sep"></div>
          <div class="bstat neutral-stat">
            <div class="bstat-icon cnt-icon">
              <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/><polyline points="14 2 14 8 20 8"/></svg>
            </div>
            <div>
              <p class="bstat-label">Records</p>
              <p class="bstat-value" id="txCount">0</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- ══════════════════════════════════════
         AI MONEY COACH  🤖
    ══════════════════════════════════════ -->
    <section class="section-coach">
      <div class="coach-card" id="coachCard">

        <!-- Scanline overlay for premium feel -->
        <div class="coach-scanlines"></div>

        <!-- Header -->
        <div class="coach-header">
          <div class="coach-avatar-wrap">
            <div class="coach-avatar">🤖</div>
            <div class="coach-online-dot"></div>
          </div>
          <div class="coach-title-block">
            <h2 class="coach-title">AI Money Coach</h2>
            <p class="coach-subtitle">Powered by your data &nbsp;·&nbsp; 100% private</p>
          </div>
          <button class="coach-refresh" id="coachRefresh" title="Refresh insights">
            <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><polyline points="1 4 1 10 7 10"/><path d="M3.51 15a9 9 0 1 0 .49-3.29"/></svg>
          </button>
        </div>

        <!-- Insight cards -->
        <div class="coach-insights" id="coachInsights">
          <div class="coach-empty-state">
            <div class="coach-empty-emoji">📊</div>
            <p class="coach-empty-text">Add transactions to unlock your<br/>personalized financial insights</p>
          </div>
        </div>

        <!-- Divider -->
        <div class="coach-divider"></div>

        <!-- Ask input -->
        <div class="coach-ask">
          <div class="coach-ask-label">Ask your coach</div>
          <div class="coach-ask-row">
            <input
              type="text"
              id="coachInput"
              class="coach-input"
              placeholder="e.g. How can I save more money?"
              maxlength="120"
            />
            <button class="coach-send" id="coachSend">
              <svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><line x1="22" y1="2" x2="11" y2="13"/><polygon points="22 2 15 22 11 13 2 9 22 2"/></svg>
            </button>
          </div>
          <!-- Quick prompts -->
          <div class="quick-prompts" id="quickPrompts">
            <button class="qp-btn" onclick="askCoach('How much did I spend this month?')">📅 This month</button>
            <button class="qp-btn" onclick="askCoach('What is my top expense category?')">🏆 Top category</button>
            <button class="qp-btn" onclick="askCoach('Am I saving enough?')">💰 Am I saving?</button>
            <button class="qp-btn" onclick="askCoach('Give me tips to reduce expenses')">💡 Save tips</button>
          </div>
          <!-- Chat thread -->
          <div class="coach-chat" id="coachChat" style="display:none;"></div>
        </div>

      </div>
    </section>

    <!-- ══════════════════════════════════════
         ADD TRANSACTION
    ══════════════════════════════════════ -->
    <section class="section-form">
      <div class="form-card">

        <div class="form-card-header">
          <h2 class="form-title">Add Transaction</h2>
          <div class="type-toggle">
            <button class="toggle-btn active" id="btnIncome" onclick="setType('income')">
              <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><line x1="12" y1="19" x2="12" y2="5"/><polyline points="5 12 12 5 19 12"/></svg>
              Income
            </button>
            <button class="toggle-btn" id="btnExpense" onclick="setType('expense')">
              <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><line x1="12" y1="5" x2="12" y2="19"/><polyline points="19 12 12 19 5 12"/></svg>
              Expense
            </button>
          </div>
        </div>

        <div class="form-grid">
          <div class="field field-full">
            <label class="field-label" for="desc">Description</label>
            <div class="field-wrap">
              <svg class="field-ico" width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M11 4H4a2 2 0 0 0-2 2v14a2 2 0 0 0 2 2h14a2 2 0 0 0 2-2v-7"/><path d="M18.5 2.5a2.121 2.121 0 0 1 3 3L12 15l-4 1 1-4 9.5-9.5z"/></svg>
              <input type="text" id="desc" class="field-input" placeholder="e.g. Salary, Swiggy order, Uber ride…" maxlength="60" autocomplete="off" />
            </div>
          </div>

          <div class="field">
            <label class="field-label" for="amount">Amount (₹)</label>
            <div class="field-wrap">
              <svg class="field-ico" width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><line x1="12" y1="1" x2="12" y2="23"/><path d="M17 5H9.5a3.5 3.5 0 0 0 0 7h5a3.5 3.5 0 0 1 0 7H6"/></svg>
              <input type="number" id="amount" class="field-input" placeholder="0.00" min="0.01" step="0.01" />
            </div>
          </div>

          <div class="field">
            <label class="field-label" for="category">Category</label>
            <div class="field-wrap field-sel-wrap">
              <svg class="field-ico" width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M20.59 13.41l-7.17 7.17a2 2 0 0 1-2.83 0L2 12V2h10l8.59 8.59a2 2 0 0 1 0 2.82z"/><line x1="7" y1="7" x2="7.01" y2="7"/></svg>
              <select id="category" class="field-input field-sel">
                <optgroup label="Expenses">
                  <option value="Food">🍔 Food &amp; Dining</option>
                  <option value="Transport">🚌 Transport</option>
                  <option value="Shopping">🛍️ Shopping</option>
                  <option value="Bills">💡 Bills &amp; Utilities</option>
                  <option value="Health">💊 Health</option>
                  <option value="Entertainment">🎬 Entertainment</option>
                  <option value="Rent">🏠 Rent</option>
                  <option value="Education">📚 Education</option>
                  <option value="Subscriptions">📺 Subscriptions</option>
                </optgroup>
                <optgroup label="Income">
                  <option value="Salary">💼 Salary</option>
                  <option value="Freelance">💻 Freelance</option>
                  <option value="Investment">📈 Investment</option>
                  <option value="Gift">🎁 Gift</option>
                  <option value="Business">🏢 Business</option>
                  <option value="Refund">↩️ Refund</option>
                </optgroup>
                <optgroup label="Other">
                  <option value="General">📦 General</option>
                  <option value="Other">💳 Other</option>
                </optgroup>
              </select>
            </div>
          </div>

          <div class="field">
            <label class="field-label" for="txDate">Date</label>
            <div class="field-wrap">
              <svg class="field-ico" width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="3" y="4" width="18" height="18" rx="2" ry="2"/><line x1="16" y1="2" x2="16" y2="6"/><line x1="8" y1="2" x2="8" y2="6"/><line x1="3" y1="10" x2="21" y2="10"/></svg>
              <input type="date" id="txDate" class="field-input" />
            </div>
          </div>

          <div class="field field-full">
            <label class="field-label" for="note">Note <span class="field-opt">(optional)</span></label>
            <div class="field-wrap">
              <svg class="field-ico" width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"/></svg>
              <input type="text" id="note" class="field-input" placeholder="Any extra detail…" maxlength="80" />
            </div>
          </div>
        </div>

        <div class="form-error" id="formError"></div>

        <button class="submit-btn" id="submitBtn" onclick="addTransaction()">
          <svg width="17" height="17" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><line x1="12" y1="5" x2="12" y2="19"/><line x1="5" y1="12" x2="19" y2="12"/></svg>
          <span id="submitLabel">Add Income</span>
        </button>

      </div>
    </section>

    <!-- ══════════════════════════════════════
         TRANSACTION LIST
    ══════════════════════════════════════ -->
    <section class="section-list">
      <div class="list-controls-bar">
        <div class="list-title-row">
          <h2 class="list-heading">Transactions</h2>
          <span class="list-count-badge" id="listCountBadge">0</span>
        </div>
        <div class="list-tools">
          <div class="search-box">
            <svg class="search-ico" width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="11" cy="11" r="8"/><line x1="21" y1="21" x2="16.65" y2="16.65"/></svg>
            <input type="text" id="searchInput" class="search-field" placeholder="Search…" />
          </div>
          <select id="filterType" class="ctrl-select" onchange="renderTransactions()">
            <option value="all">All</option>
            <option value="income">Income</option>
            <option value="expense">Expense</option>
          </select>
          <select id="sortOrder" class="ctrl-select" onchange="renderTransactions()">
            <option value="newest">Newest</option>
            <option value="oldest">Oldest</option>
            <option value="highest">Highest</option>
            <option value="lowest">Lowest</option>
          </select>
        </div>
      </div>

      <!-- Sparkline mini chart -->
      <div class="mini-chart-wrap">
        <canvas id="miniChart" class="mini-chart-canvas" height="60"></canvas>
      </div>

      <div class="tx-list" id="txList"></div>
    </section>

    <!-- FOOTER -->
    <footer class="app-footer">
      <p>Made with <span class="heart">♥</span> by <strong>AKASH BJ</strong></p>
      <p class="footer-note">All data stored locally on your device · No server · No tracking</p>
    </footer>

  </div><!-- /app-shell -->

  <!-- TOAST -->
  <div class="toast" id="toast"></div>

  <!-- EXPORT MODAL -->
  <div class="modal-backdrop" id="exportModal">
    <div class="modal-box">
      <div class="modal-head">
        <h3 class="modal-title">Export Data</h3>
        <button class="modal-close" onclick="closeModal('exportModal')">✕</button>
      </div>
      <p class="modal-desc">Download your full transaction history.</p>
      <div class="modal-btns">
        <button class="mbtn primary" onclick="exportCSV()">📊 Download CSV</button>
        <button class="mbtn secondary" onclick="exportJSON()">&#123;&#125; Download JSON</button>
      </div>
    </div>
  </div>

  <script src="script.js"></script>
</body>
</html>
