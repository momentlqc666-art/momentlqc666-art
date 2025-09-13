<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Student Finance Manager</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <style>
    /* ===== Base Styles ===== */
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      margin: 0;
      background: #0f2027;
      background: linear-gradient(135deg, #0f2027, #203a43, #2c5364);
      color: #f1f1f1;
    }

    h2 {
      font-size: 24px;
      margin-bottom: 15px;
      display: flex;
      align-items: center;
      gap: 10px;
    }

    /* ===== Sidebar ===== */
    .sidebar {
      width: 240px;
      background: #111827;
      height: 100vh;
      position: fixed;
      top: 0;
      left: 0;
      padding: 20px 0;
      transition: width 0.3s;
      overflow: hidden;
    }
    .sidebar.collapsed {
      width: 70px;
    }
    .sidebar h1 {
      color: #4CAF50;
      text-align: center;
      margin: 0 0 20px 0;
      font-size: 20px;
    }
    .sidebar ul {
      list-style: none;
      padding: 0;
    }
    .sidebar ul li {
      padding: 15px 20px;
      cursor: pointer;
      display: flex;
      align-items: center;
      gap: 10px;
      transition: 0.3s;
      color: #ddd;
    }
    .sidebar ul li:hover, .sidebar ul li.active {
      background: #1f2937;
      color: #4CAF50;
    }
    .sidebar ul li i {
      font-size: 18px;
    }

    /* ===== Content ===== */
    .content {
      margin-left: 240px;
      padding: 20px;
      transition: margin-left 0.3s;
    }
    .sidebar.collapsed ~ .content {
      margin-left: 70px;
    }

    /* ===== Cards ===== */
    .card {
      background: #1f2937;
      border-radius: 15px;
      padding: 20px;
      box-shadow: 0 6px 15px rgba(0,0,0,0.5);
      margin: 15px 0;
    }

    /* ===== Inputs ===== */
    .form-input, .form-select {
      padding: 10px;
      border-radius: 12px;
      border: none;
      margin: 5px;
      outline: none;
      transition: all 0.3s;
      background: #374151;
      color: #fff;
    }
    .form-input:focus, .form-select:focus {
      border: 2px solid #4CAF50;
    }

    .btn-add {
      background: linear-gradient(135deg, #4CAF50, #2e7d32);
      border: none;
      padding: 10px 15px;
      color: white;
      font-weight: bold;
      border-radius: 12px;
      cursor: pointer;
      transition: 0.3s;
    }
    .btn-add:hover {
      transform: scale(1.05);
      background: linear-gradient(135deg, #43a047, #1b5e20);
    }

    /* ===== Tables ===== */
    table {
      width: 100%;
      border-collapse: collapse;
      margin-top: 15px;
      border-radius: 10px;
      overflow: hidden;
    }
    th, td {
      padding: 12px;
      text-align: center;
    }
    thead {
      background: #374151;
      color: #4CAF50;
    }
    tbody tr:nth-child(even) {
      background: #2c3e50;
    }

    .badge {
      padding: 5px 10px;
      border-radius: 8px;
      font-size: 12px;
    }
    .income {
      background: #388e3c;
      color: #fff;
    }
    .expense {
      background: #d32f2f;
      color: #fff;
    }

    /* ===== Progress Bars ===== */
    .progress-bar {
      background: #374151;
      border-radius: 12px;
      overflow: hidden;
      height: 12px;
      margin-top: 8px;
    }
    .progress {
      background: linear-gradient(90deg, #4CAF50, #81c784);
      height: 100%;
      transition: width 0.5s ease;
    }

    /* ===== Grid Layouts ===== */
    .budget-cards, .goal-cards, .tips-grid {
      display: flex;
      flex-wrap: wrap;
      gap: 15px;
    }
    .budget-card, .goal-card, .tip-card {
      flex: 1;
      min-width: 220px;
      background: #1f2937;
      border-radius: 15px;
      padding: 20px;
      box-shadow: 0 6px 15px rgba(0,0,0,0.5);
      transition: 0.3s;
    }
    .budget-card:hover, .goal-card:hover, .tip-card:hover {
      transform: translateY(-5px);
    }

  </style>
</head>
<body>

  <!-- Sidebar -->
  <div class="sidebar" id="sidebar">
    <h1>💰 Finance</h1>
    <ul>
      <li class="active" onclick="openTab('dashboard')"><i class="fas fa-chart-line"></i><span>Dashboard</span></li>
      <li onclick="openTab('transactions')"><i class="fas fa-money-bill-wave"></i><span>Transactions</span></li>
      <li onclick="openTab('budget')"><i class="fas fa-thumbtack"></i><span>Budget Planner</span></li>
      <li onclick="openTab('savings')"><i class="fas fa-lightbulb"></i><span>Savings Goals</span></li>
      <li onclick="openTab('tips')"><i class="fas fa-book-open"></i><span>Finance Tips</span></li>
    </ul>
  </div>

  <!-- Content -->
  <div class="content">
    <!-- Dashboard -->
    <div class="tab-content" id="dashboard">
      <h2><i class="fas fa-chart-line"></i> Dashboard</h2>
      <div class="budget-cards">
        <div class="card"><h3>Total Income</h3><p>$1200</p></div>
        <div class="card"><h3>Total Expenses</h3><p>$650</p></div>
        <div class="card"><h3>Balance</h3><p>$550</p></div>
      </div>
    </div>

    <!-- Transactions -->
    <div class="tab-content" id="transactions" style="display:none;">
      <h2><i class="fas fa-money-bill-wave"></i> Transactions</h2>
      <div class="transaction-form">
        <input type="text" placeholder="Enter Description" class="form-input">
        <input type="number" placeholder="Enter Amount" class="form-input">
        <select class="form-select">
          <option>Income</option>
          <option>Expense</option>
        </select>
        <button class="btn-add">+ Add</button>
      </div>
      <table>
        <thead>
          <tr><th>Description</th><th>Amount</th><th>Type</th><th>Date</th></tr>
        </thead>
        <tbody>
          <tr><td>Scholarship</td><td>+ $500</td><td><span class="badge income">Income</span></td><td>Sept 13</td></tr>
          <tr><td>Books</td><td>- $60</td><td><span class="badge expense">Expense</span></td><td>Sept 12</td></tr>
        </tbody>
      </table>
    </div>

    <!-- Budget Planner -->
    <div class="tab-content" id="budget" style="display:none;">
      <h2><i class="fas fa-thumbtack"></i> Budget Planner</h2>
      <div class="budget-form">
        <input type="text" placeholder="Category (Food, Rent...)" class="form-input">
        <input type="number" placeholder="Budget Amount" class="form-input">
        <button class="btn-add">+ Set Budget</button>
      </div>
      <div class="budget-cards">
        <div class="budget-card"><h3>🍔 Food</h3><p>Planned: $200 | Spent: $120</p><div class="progress-bar"><div class="progress" style="width:60%"></div></div></div>
        <div class="budget-card"><h3>🚍 Transport</h3><p>Planned: $100 | Spent: $30</p><div class="progress-bar"><div class="progress" style="width:30%"></div></div></div>
      </div>
    </div>

    <!-- Savings Goals -->
    <div class="tab-content" id="savings" style="display:none;">
      <h2><i class="fas fa-lightbulb"></i> Savings Goals</h2>
      <div class="goal-form">
        <input type="text" placeholder="Goal (Laptop, Trip...)" class="form-input">
        <input type="number" placeholder="Target Amount" class="form-input">
        <button class="btn-add">+ Add Goal</button>
      </div>
      <div class="goal-cards">
        <div class="goal-card"><h3>💻 Laptop</h3><p>Target: $1200 | Saved: $400</p><div class="progress-bar"><div class="progress" style="width:33%"></div></div></div>
        <div class="goal-card"><h3>🌍 Trip</h3><p>Target: $2000 | Saved: $600</p><div class="progress-bar"><div class="progress" style="width:30%"></div></div></div>
      </div>
    </div>

    <!-- Finance Tips -->
    <div class="tab-content" id="tips" style="display:none;">
      <h2><i class="fas fa-book-open"></i> Finance Tips</h2>
      <div class="tips-grid">
        <div class="tip-card"><h3>📊 Create a Budget</h3><p>Track income and expenses monthly.</p></div>
        <div class="tip-card"><h3>💳 Avoid Debt</h3><p>Don’t overspend using loans or credit.</p></div>
        <div class="tip-card"><h3>📈 Save Early</h3><p>Start saving at least 10% monthly.</p></div>
        <div class="tip-card"><h3>🎯 Set Goals</h3><p>Work towards clear savings goals.</p></div>
        <div class="tip-card"><h3>📱 Use Apps</h3><p>Apps make tracking easier & automatic.</p></div>
        <div class="tip-card"><h3>🍕 Smart Spending</h3><p>Cook meals instead of eating out.</p></div>
        <div class="tip-card"><h3>🛒 Shop Smart</h3><p>Buy in bulk to save more.</p></div>
      </div>
    </div>
  </div>

  <script>
    function openTab(tabName) {
      document.querySelectorAll('.tab-content').forEach(t => t.style.display = 'none');
      document.getElementById(tabName).style.display = 'block';
      document.querySelectorAll('.sidebar ul li').forEach(li => li.classList.remove('active'));
      event.target.closest('li').classList.add('active');
    }
  </script>
</body>
</html>
