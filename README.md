<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bank Sampah ARAS Citambal</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #4CAF50 0%, #2E7D32 100%);
            color: #333;
            min-height: 100vh;
            overflow-x: hidden;
        }

        .app-container {
            max-width: 414px;
            margin: 0 auto;
            background: #f8f9fa;
            min-height: 100vh;
            box-shadow: 0 0 20px rgba(0,0,0,0.1);
            position: relative;
        }

        .header {
            background: linear-gradient(135deg, #4CAF50 0%, #66BB6A 100%);
            color: white;
            padding: 20px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .header::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, transparent 70%);
            animation: rotate 8s linear infinite;
        }

        @keyframes rotate {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .logo-container {
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 10px;
            position: relative;
            z-index: 2;
        }

        .logo {
            font-size: 32px;
            margin-right: 10px;
        }

        .bank-name {
            font-size: 24px;
            font-weight: bold;
            line-height: 1.2;
        }

        .location {
            font-size: 14px;
            opacity: 0.9;
            margin-top: 5px;
            position: relative;
            z-index: 2;
        }

        .balance-section {
            background: white;
            margin: -15px 20px 20px;
            padding: 25px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(76, 175, 80, 0.2);
            position: relative;
            overflow: hidden;
        }

        .balance-section::before {
            content: '';
            position: absolute;
            top: 0;
            right: 0;
            width: 100px;
            height: 100px;
            background: radial-gradient(circle, rgba(76, 175, 80, 0.1) 0%, transparent 70%);
            border-radius: 50%;
            transform: translate(30px, -30px);
        }

        .member-info {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
        }

        .member-avatar {
            width: 50px;
            height: 50px;
            background: linear-gradient(135deg, #4CAF50, #66BB6A);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 24px;
            margin-right: 15px;
            color: white;
        }

        .member-details h3 {
            font-size: 18px;
            color: #333;
            margin-bottom: 3px;
        }

        .member-id {
            font-size: 12px;
            color: #666;
            background: #e8f5e8;
            padding: 2px 8px;
            border-radius: 10px;
            display: inline-block;
        }

        .balance-display {
            text-align: center;
            margin-bottom: 20px;
        }

        .balance-label {
            font-size: 14px;
            color: #666;
            margin-bottom: 8px;
        }

        .balance-amount {
            font-size: 36px;
            font-weight: bold;
            color: #4CAF50;
            margin-bottom: 5px;
        }

        .balance-weight {
            font-size: 14px;
            color: #666;
            background: #f0f8f0;
            padding: 5px 12px;
            border-radius: 15px;
            display: inline-block;
        }

        .action-buttons {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 10px;
            margin-top: 20px;
        }

        .action-btn {
            background: linear-gradient(135deg, #4CAF50, #66BB6A);
            color: white;
            border: none;
            padding: 12px;
            border-radius: 12px;
            font-size: 14px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
        }

        .action-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(76, 175, 80, 0.3);
        }

        .action-btn.secondary {
            background: linear-gradient(135deg, #FF9800, #F57C00);
        }

        .menu-section {
            padding: 0 20px 20px;
        }

        .section-title {
            font-size: 18px;
            font-weight: bold;
            color: #333;
            margin: 20px 0 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .menu-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 15px;
            margin-bottom: 20px;
        }

        .menu-item {
            background: white;
            border-radius: 15px;
            padding: 20px 15px;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0,0,0,0.08);
            cursor: pointer;
            transition: all 0.3s ease;
            border: 1px solid #e8f5e8;
        }

        .menu-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.15);
        }

        .menu-icon {
            width: 50px;
            height: 50px;
            margin: 0 auto 12px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 24px;
            color: white;
        }

        .menu-icon.deposit { background: linear-gradient(135deg, #4CAF50, #66BB6A); }
        .menu-icon.withdraw { background: linear-gradient(135deg, #2196F3, #42A5F5); }
        .menu-icon.history { background: linear-gradient(135deg, #FF9800, #FFA726); }
        .menu-icon.catalog { background: linear-gradient(135deg, #9C27B0, #BA68C8); }
        .menu-icon.education { background: linear-gradient(135deg, #F44336, #EF5350); }
        .menu-icon.community { background: linear-gradient(135deg, #795548, #8D6E63); }

        .menu-text {
            font-size: 12px;
            color: #333;
            font-weight: 600;
            line-height: 1.3;
        }

        .stats-section {
            background: white;
            margin: 0 20px 20px;
            padding: 20px;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.08);
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 15px;
        }

        .stat-item {
            text-align: center;
            padding: 15px 10px;
            border-radius: 12px;
            background: #f8f9fa;
        }

        .stat-value {
            font-size: 20px;
            font-weight: bold;
            color: #4CAF50;
            margin-bottom: 5px;
        }

        .stat-label {
            font-size: 11px;
            color: #666;
            line-height: 1.3;
        }

        .activity-section {
            background: white;
            margin: 0 20px 80px;
            padding: 20px;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.08);
        }

        .activity-item {
            display: flex;
            align-items: center;
            padding: 15px 0;
            border-bottom: 1px solid #f0f0f0;
        }

        .activity-item:last-child {
            border-bottom: none;
        }

        .activity-icon {
            width: 45px;
            height: 45px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-right: 15px;
            font-size: 20px;
            color: white;
        }

        .activity-icon.deposit { background: linear-gradient(135deg, #4CAF50, #66BB6A); }
        .activity-icon.withdraw { background: linear-gradient(135deg, #2196F3, #42A5F5); }
        .activity-icon.bonus { background: linear-gradient(135deg, #FF9800, #FFA726); }

        .activity-info {
            flex: 1;
        }

        .activity-title {
            font-weight: 600;
            color: #333;
            margin-bottom: 3px;
            font-size: 14px;
        }

        .activity-date {
            font-size: 12px;
            color: #666;
        }

        .activity-amount {
            font-weight: bold;
            font-size: 14px;
        }

        .activity-amount.positive { color: #4CAF50; }
        .activity-amount.negative { color: #F44336; }

        .bottom-nav {
            position: fixed;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 100%;
            max-width: 414px;
            background: white;
            border-top: 1px solid #e0e0e0;
            display: flex;
            padding: 10px 0;
            box-shadow: 0 -5px 15px rgba(0,0,0,0.1);
        }

        .nav-item {
            flex: 1;
            text-align: center;
            padding: 10px;
            cursor: pointer;
            transition: all 0.3s ease;
            color: #666;
        }

        .nav-item.active {
            color: #4CAF50;
        }

        .nav-icon {
            font-size: 22px;
            margin-bottom: 5px;
        }

        .nav-text {
            font-size: 10px;
            font-weight: 600;
        }

        .floating-btn {
            position: fixed;
            bottom: 80px;
            right: 20px;
            width: 60px;
            height: 60px;
            background: linear-gradient(135deg, #4CAF50, #66BB6A);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 28px;
            cursor: pointer;
            box-shadow: 0 10px 25px rgba(76, 175, 80, 0.4);
            transition: all 0.3s ease;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0% { box-shadow: 0 10px 25px rgba(76, 175, 80, 0.4); }
            50% { box-shadow: 0 15px 35px rgba(76, 175, 80, 0.6); }
            100% { box-shadow: 0 10px 25px rgba(76, 175, 80, 0.4); }
        }

        .notification-banner {
            background: linear-gradient(135deg, #E3F2FD, #BBDEFB);
            margin: 0 20px 20px;
            padding: 15px;
            border-radius: 12px;
            border-left: 4px solid #2196F3;
            display: flex;
            align-items: center;
            cursor: pointer;
        }

        .notification-icon {
            font-size: 24px;
            margin-right: 12px;
            color: #2196F3;
        }

        .notification-text {
            flex: 1;
            font-size: 13px;
            color: #333;
        }

        .achievement-badge {
            position: absolute;
            top: 10px;
            right: 10px;
            background: #FF9800;
            color: white;
            padding: 5px 10px;
            border-radius: 12px;
            font-size: 10px;
            font-weight: bold;
            animation: bounce 2s infinite;
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% { transform: translateY(0); }
            40% { transform: translateY(-10px); }
            60% { transform: translateY(-5px); }
        }

        @media (max-width: 375px) {
            .menu-grid {
                grid-template-columns: repeat(2, 1fr);
            }
            
            .balance-amount {
                font-size: 32px;
            }
            
            .stats-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.5);
            z-index: 1000;
            backdrop-filter: blur(5px);
        }

        .modal-content {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background: white;
            padding: 30px;
            border-radius: 20px;
            width: 90%;
            max-width: 350px;
            text-align: center;
            box-shadow: 0 20px 40px rgba(0,0,0,0.3);
        }

        .modal-icon {
            font-size: 48px;
            margin-bottom: 15px;
        }

        .modal-title {
            font-size: 20px;
            font-weight: bold;
            margin-bottom: 10px;
            color: #333;
        }

        .modal-text {
            font-size: 14px;
            color: #666;
            margin-bottom: 20px;
            line-height: 1.5;
        }

        .modal-btn {
            background: linear-gradient(135deg, #4CAF50, #66BB6A);
            color: white;
            border: none;
            padding: 12px 30px;
            border-radius: 25px;
            font-size: 14px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .modal-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(76, 175, 80, 0.3);
        }
    </style>
</head>
<body>
    <div class="app-container">
        <!-- Header -->
        <div class="header">
            <div class="achievement-badge">🏆 ECO HERO</div>
            <div class="logo-container">
                <div class="logo">♻️</div>
                <div>
                    <div class="bank-name">BANK SAMPAH ARAS</div>
                    <div class="location">Karangtaruna Dusun Citambal</div>
                </div>
            </div>
        </div>

        <!-- Balance Section -->
        <div class="balance-section">
            <div class="member-info">
                <div class="member-avatar">👤</div>
                <div class="member-details">
                    <h3>Budi Santoso</h3>
                    <div class="member-id">ID: ARAS-001</div>
                </div>
            </div>
            
            <div class="balance-display">
                <div class="balance-label">Saldo Tabungan Sampah</div>
                <div class="balance-amount">Rp 347.500</div>
                <div class="balance-weight">Total: 89.2 kg</div>
            </div>

            <div class="action-buttons">
                <button class="action-btn" onclick="showDeposit()">
                    ♻️ Setor Sampah
                </button>
                <button class="action-btn secondary" onclick="showWithdraw()">
                    💰 Tarik Saldo
                </button>
            </div>
        </div>

        <!-- Notification Banner -->
        <div class="notification-banner" onclick="showNotification()">
            <div class="notification-icon">📢</div>
            <div class="notification-text">
                <strong>Pengumuman:</strong> Jadwal pengambilan sampah Senin & Kamis jam 08:00 WIB
            </div>
        </div>

        <!-- Menu Section -->
        <div class="menu-section">
            <div class="section-title">
                🏠 Layanan Bank Sampah
            </div>
            <div class="menu-grid">
                <div class="menu-item" onclick="showDeposit()">
                    <div class="menu-icon deposit">♻️</div>
                    <div class="menu-text">Setor Sampah</div>
                </div>
                <div class="menu-item" onclick="showWithdraw()">
                    <div class="menu-icon withdraw">💰</div>
                    <div class="menu-text">Tarik Saldo</div>
                </div>
                <div class="menu-item" onclick="showHistory()">
                    <div class="menu-icon history">📊</div>
                    <div class="menu-text">Riwayat Transaksi</div>
                </div>
                <div class="menu-item" onclick="showCatalog()">
                    <div class="menu-icon catalog">📋</div>
                    <div class="menu-text">Katalog Sampah</div>
                </div>
                <div class="menu-item" onclick="showEducation()">
                    <div class="menu-icon education">📚</div>
                    <div class="menu-text">Edukasi Lingkungan</div>
                </div>
                <div class="menu-item" onclick="showCommunity()">
                    <div class="menu-icon community">👥</div>
                    <div class="menu-text">Komunitas</div>
                </div>
            </div>
        </div>

        <!-- Statistics Section -->
        <div class="stats-section">
            <div class="section-title">📈 Statistik Bulan Ini</div>
            <div class="stats-grid">
                <div class="stat-item">
                    <div class="stat-value">23.4</div>
                    <div class="stat-label">kg Sampah Disetor</div>
                </div>
                <div class="stat-item">
                    <div class="stat-value">78.500</div>
                    <div class="stat-label">Rupiah Diperoleh</div>
                </div>
                <div class="stat-item">
                    <div class="stat-value">12</div>
                    <div class="stat-label">Transaksi</div>
                </div>
            </div>
        </div>

        <!-- Activity Section -->
        <div class="activity-section">
            <div class="section-title">🕒 Aktivitas Terbaru</div>
            
            <div class="activity-item">
                <div class="activity-icon deposit">♻️</div>
                <div class="activity-info">
                    <div class="activity-title">Setor Sampah Plastik</div>
                    <div class="activity-date">Hari ini, 14:30 - 2.5 kg</div>
                </div>
                <div class="activity-amount positive">+Rp 12.500</div>
            </div>

            <div class="activity-item">
                <div class="activity-icon bonus">🎁</div>
                <div class="activity-info">
                    <div class="activity-title">Bonus Konsistensi</div>
                    <div class="activity-date">Kemarin, 16:00</div>
                </div>
                <div class="activity-amount positive">+Rp 5.000</div>
            </div>

            <div class="activity-item">
                <div class="activity-icon deposit">♻️</div>
                <div class="activity-info">
                    <div class="activity-title">Setor Sampah Kertas</div>
                    <div class="activity-date">2 hari lalu, 09:15 - 4.2 kg</div>
                </div>
                <div class="activity-amount positive">+Rp 8.400</div>
            </div>

            <div class="activity-item">
                <div class="activity-icon withdraw">💰</div>
                <div class="activity-info">
                    <div class="activity-title">Penarikan Saldo</div>
                    <div class="activity-date">1 minggu lalu, 11:20</div>
                </div>
                <div class="activity-amount negative">-Rp 50.000</div>
            </div>

            <div class="activity-item">
                <div class="activity-icon deposit">♻️</div>
                <div class="activity-info">
                    <di<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bank Sampah ARAS Citambal</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #4CAF50 0%, #2E7D32 100%);
            color: #333;
            min-height: 100vh;
            overflow-x: hidden;
        }

        .app-container {
            max-width: 414px;
            margin: 0 auto;
            background: #f8f9fa;
            min-height: 100vh;
            box-shadow: 0 0 20px rgba(0,0,0,0.1);
            position: relative;
        }

        .header {
            background: linear-gradient(135deg, #4CAF50 0%, #66BB6A 100%);
            color: white;
            padding: 20px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .header::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, transparent 70%);
            animation: rotate 8s linear infinite;
        }

        @keyframes rotate {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .logo-container {
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 10px;
            position: relative;
            z-index: 2;
        }

        .logo {
            font-size: 32px;
            margin-right: 10px;
        }

        .bank-name {
            font-size: 24px;
            font-weight: bold;
            line-height: 1.2;
        }

        .location {
            font-size: 14px;
            opacity: 0.9;
            margin-top: 5px;
            position: relative;
            z-index: 2;
        }

        .balance-section {
            background: white;
            margin: -15px 20px 20px;
            padding: 25px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(76, 175, 80, 0.2);
            position: relative;
            overflow: hidden;
        }

        .balance-section::before {
            content: '';
            position: absolute;
            top: 0;
            right: 0;
            width: 100px;
            height: 100px;
            background: radial-gradient(circle, rgba(76, 175, 80, 0.1) 0%, transparent 70%);
            border-radius: 50%;
            transform: translate(30px, -30px);
        }

        .member-info {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
        }

        .member-avatar {
            width: 50px;
            height: 50px;
            background: linear-gradient(135deg, #4CAF50, #66BB6A);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 24px;
            margin-right: 15px;
            color: white;
        }

        .member-details h3 {
            font-size: 18px;
            color: #333;
            margin-bottom: 3px;
        }

        .member-id {
            font-size: 12px;
            color: #666;
            background: #e8f5e8;
            padding: 2px 8px;
            border-radius: 10px;
            display: inline-block;
        }

        .balance-display {
            text-align: center;
            margin-bottom: 20px;
        }

        .balance-label {
            font-size: 14px;
            color: #666;
            margin-bottom: 8px;
        }

        .balance-amount {
            font-size: 36px;
            font-weight: bold;
            color: #4CAF50;
            margin-bottom: 5px;
        }

        .balance-weight {
            font-size: 14px;
            color: #666;
            background: #f0f8f0;
            padding: 5px 12px;
            border-radius: 15px;
            display: inline-block;
        }

        .action-buttons {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 10px;
            margin-top: 20px;
        }

        .action-btn {
            background: linear-gradient(135deg, #4CAF50, #66BB6A);
            color: white;
            border: none;
            padding: 12px;
            border-radius: 12px;
            font-size: 14px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
        }

        .action-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(76, 175, 80, 0.3);
        }

        .action-btn.secondary {
            background: linear-gradient(135deg, #FF9800, #F57C00);
        }

        .menu-section {
            padding: 0 20px 20px;
        }

        .section-title {
            font-size: 18px;
            font-weight: bold;
            color: #333;
            margin: 20px 0 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .menu-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 15px;
            margin-bottom: 20px;
        }

        .menu-item {
            background: white;
            border-radius: 15px;
            padding: 20px 15px;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0,0,0,0.08);
            cursor: pointer;
            transition: all 0.3s ease;
            border: 1px solid #e8f5e8;
        }

        .menu-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.15);
        }

        .menu-icon {
            width: 50px;
            height: 50px;
            margin: 0 auto 12px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 24px;
            color: white;
        }

        .menu-icon.deposit { background: linear-gradient(135deg, #4CAF50, #66BB6A); }
        .menu-icon.withdraw { background: linear-gradient(135deg, #2196F3, #42A5F5); }
        .menu-icon.history { background: linear-gradient(135deg, #FF9800, #FFA726); }
        .menu-icon.catalog { background: linear-gradient(135deg, #9C27B0, #BA68C8); }
        .menu-icon.education { background: linear-gradient(135deg, #F44336, #EF5350); }
        .menu-icon.community { background: linear-gradient(135deg, #795548, #8D6E63); }

        .menu-text {
            font-size: 12px;
            color: #333;
            font-weight: 600;
            line-height: 1.3;
        }

        .stats-section {
            background: white;
            margin: 0 20px 20px;
            padding: 20px;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.08);
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 15px;
        }

        .stat-item {
            text-align: center;
            padding: 15px 10px;
            border-radius: 12px;
            background: #f8f9fa;
        }

        .stat-value {
            font-size: 20px;
            font-weight: bold;
            color: #4CAF50;
            margin-bottom: 5px;
        }

        .stat-label {
            font-size: 11px;
            color: #666;
            line-height: 1.3;
        }

        .activity-section {
            background: white;
            margin: 0 20px 80px;
            padding: 20px;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.08);
        }

        .activity-item {
            display: flex;
            align-items: center;
            padding: 15px 0;
            border-bottom: 1px solid #f0f0f0;
        }

        .activity-item:last-child {
            border-bottom: none;
        }

        .activity-icon {
            width: 45px;
            height: 45px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-right: 15px;
            font-size: 20px;
            color: white;
        }

        .activity-icon.deposit { background: linear-gradient(135deg, #4CAF50, #66BB6A); }
        .activity-icon.withdraw { background: linear-gradient(135deg, #2196F3, #42A5F5); }
        .activity-icon.bonus { background: linear-gradient(135deg, #FF9800, #FFA726); }

        .activity-info {
            flex: 1;
        }

        .activity-title {
            font-weight: 600;
            color: #333;
            margin-bottom: 3px;
            font-size: 14px;
        }

        .activity-date {
            font-size: 12px;
            color: #666;
        }

        .activity-amount {
            font-weight: bold;
            font-size: 14px;
        }

        .activity-amount.positive { color: #4CAF50; }
        .activity-amount.negative { color: #F44336; }

        .bottom-nav {
            position: fixed;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 100%;
            max-width: 414px;
            background: white;
            border-top: 1px solid #e0e0e0;
            display: flex;
            padding: 10px 0;
            box-shadow: 0 -5px 15px rgba(0,0,0,0.1);
        }

        .nav-item {
            flex: 1;
            text-align: center;
            padding: 10px;
            cursor: pointer;
            transition: all 0.3s ease;
            color: #666;
        }

        .nav-item.active {
            color: #4CAF50;
        }

        .nav-icon {
            font-size: 22px;
            margin-bottom: 5px;
        }

        .nav-text {
            font-size: 10px;
            font-weight: 600;
        }

        .floating-btn {
            position: fixed;
            bottom: 80px;
            right: 20px;
            width: 60px;
            height: 60px;
            background: linear-gradient(135deg, #4CAF50, #66BB6A);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 28px;
            cursor: pointer;
            box-shadow: 0 10px 25px rgba(76, 175, 80, 0.4);
            transition: all 0.3s ease;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0% { box-shadow: 0 10px 25px rgba(76, 175, 80, 0.4); }
            50% { box-shadow: 0 15px 35px rgba(76, 175, 80, 0.6); }
            100% { box-shadow: 0 10px 25px rgba(76, 175, 80, 0.4); }
        }

        .notification-banner {
            background: linear-gradient(135deg, #E3F2FD, #BBDEFB);
            margin: 0 20px 20px;
            padding: 15px;
            border-radius: 12px;
            border-left: 4px solid #2196F3;
            display: flex;
            align-items: center;
            cursor: pointer;
        }

        .notification-icon {
            font-size: 24px;
            margin-right: 12px;
            color: #2196F3;
        }

        .notification-text {
            flex: 1;
            font-size: 13px;
            color: #333;
        }

        .achievement-badge {
            position: absolute;
            top: 10px;
            right: 10px;
            background: #FF9800;
            color: white;
            padding: 5px 10px;
            border-radius: 12px;
            font-size: 10px;
            font-weight: bold;
            animation: bounce 2s infinite;
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% { transform: translateY(0); }
            40% { transform: translateY(-10px); }
            60% { transform: translateY(-5px); }
        }

        @media (max-width: 375px) {
            .menu-grid {
                grid-template-columns: repeat(2, 1fr);
            }
            
            .balance-amount {
                font-size: 32px;
            }
            
            .stats-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.5);
            z-index: 1000;
            backdrop-filter: blur(5px);
        }

        .modal-content {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background: white;
            padding: 30px;
            border-radius: 20px;
            width: 90%;
            max-width: 350px;
            text-align: center;
            box-shadow: 0 20px 40px rgba(0,0,0,0.3);
        }

        .modal-icon {
            font-size: 48px;
            margin-bottom: 15px;
        }

        .modal-title {
            font-size: 20px;
            font-weight: bold;
            margin-bottom: 10px;
            color: #333;
        }

        .modal-text {
            font-size: 14px;
            color: #666;
            margin-bottom: 20px;
            line-height: 1.5;
        }

        .modal-btn {
            background: linear-gradient(135deg, #4CAF50, #66BB6A);
            color: white;
            border: none;
            padding: 12px 30px;
            border-radius: 25px;
            font-size: 14px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .modal-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(76, 175, 80, 0.3);
        }
    </style>
</head>
<body>
    <div class="app-container">
        <!-- Header -->
        <div class="header">
            <div class="achievement-badge">🏆 ECO HERO</div>
            <div class="logo-container">
                <div class="logo">♻️</div>
                <div>
                    <div class="bank-name">BANK SAMPAH ARAS</div>
                    <div class="location">Karangtaruna Dusun Citambal</div>
                </div>
            </div>
        </div>

        <!-- Balance Section -->
        <div class="balance-section">
            <div class="member-info">
                <div class="member-avatar">👤</div>
                <div class="member-details">
                    <h3>Budi Santoso</h3>
                    <div class="member-id">ID: ARAS-001</div>
                </div>
            </div>
            
            <div class="balance-display">
                <div class="balance-label">Saldo Tabungan Sampah</div>
                <div class="balance-amount">Rp 347.500</div>
                <div class="balance-weight">Total: 89.2 kg</div>
            </div>

            <div class="action-buttons">
                <button class="action-btn" onclick="showDeposit()">
                    ♻️ Setor Sampah
                </button>
                <button class="action-btn secondary" onclick="showWithdraw()">
                    💰 Tarik Saldo
                </button>
            </div>
        </div>

        <!-- Notification Banner -->
        <div class="notification-banner" onclick="showNotification()">
            <div class="notification-icon">📢</div>
            <div class="notification-text">
                <strong>Pengumuman:</strong> Jadwal pengambilan sampah Senin & Kamis jam 08:00 WIB
            </div>
        </div>

        <!-- Menu Section -->
        <div class="menu-section">
            <div class="section-title">
                🏠 Layanan Bank Sampah
            </div>
            <div class="menu-grid">
                <div class="menu-item" onclick="showDeposit()">
                    <div class="menu-icon deposit">♻️</div>
                    <div class="menu-text">Setor Sampah</div>
                </div>
                <div class="menu-item" onclick="showWithdraw()">
                    <div class="menu-icon withdraw">💰</div>
                    <div class="menu-text">Tarik Saldo</div>
                </div>
                <div class="menu-item" onclick="showHistory()">
                    <div class="menu-icon history">📊</div>
                    <div class="menu-text">Riwayat Transaksi</div>
                </div>
                <div class="menu-item" onclick="showCatalog()">
                    <div class="menu-icon catalog">📋</div>
                    <div class="menu-text">Katalog Sampah</div>
                </div>
                <div class="menu-item" onclick="showEducation()">
                    <div class="menu-icon education">📚</div>
                    <div class="menu-text">Edukasi Lingkungan</div>
                </div>
                <div class="menu-item" onclick="showCommunity()">
                    <div class="menu-icon community">👥</div>
                    <div class="menu-text">Komunitas</div>
                </div>
            </div>
        </div>

        <!-- Statistics Section -->
        <div class="stats-section">
            <div class="section-title">📈 Statistik Bulan Ini</div>
            <div class="stats-grid">
                <div class="stat-item">
                    <div class="stat-value">23.4</div>
                    <div class="stat-label">kg Sampah Disetor</div>
                </div>
                <div class="stat-item">
                    <div class="stat-value">78.500</div>
                    <div class="stat-label">Rupiah Diperoleh</div>
                </div>
                <div class="stat-item">
                    <div class="stat-value">12</div>
                    <div class="stat-label">Transaksi</div>
                </div>
            </div>
        </div>

        <!-- Activity Section -->
        <div class="activity-section">
            <div class="section-title">🕒 Aktivitas Terbaru</div>
            
            <div class="activity-item">
                <div class="activity-icon deposit">♻️</div>
                <div class="activity-info">
                    <div class="activity-title">Setor Sampah Plastik</div>
                    <div class="activity-date">Hari ini, 14:30 - 2.5 kg</div>
                </div>
                <div class="activity-amount positive">+Rp 12.500</div>
            </div>

            <div class="activity-item">
                <div class="activity-icon bonus">🎁</div>
                <div class="activity-info">
                    <div class="activity-title">Bonus Konsistensi</div>
                    <div class="activity-date">Kemarin, 16:00</div>
                </div>
                <div class="activity-amount positive">+Rp 5.000</div>
            </div>

            <div class="activity-item">
                <div class="activity-icon deposit">♻️</div>
                <div class="activity-info">
                    <div class="activity-title">Setor Sampah Kertas</div>
                    <div class="activity-date">2 hari lalu, 09:15 - 4.2 kg</div>
                </div>
                <div class="activity-amount positive">+Rp 8.400</div>
            </div>

            <div class="activity-item">
                <div class="activity-icon withdraw">💰</div>
                <div class="activity-info">
                    <div class="activity-title">Penarikan Saldo</div>
                    <div class="activity-date">1 minggu lalu, 11:20</div>
                </div>
                <div class="activity-amount negative">-Rp 50.000</div>
            </div>

            <div class="activity-item">
                <div class="activity-icon deposit">♻️</div>
                <div class="activity-info">
                    <di
