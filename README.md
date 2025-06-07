<!DOCTYPE html> 

<html lang=”id”> 

<head> 

    <meta charset=”UTF-8”> 

    <meta name=”viewport” content=”width=device-width, initial-scale=1.0”> 

    <title>Bank Sampah Karangtaruna ARAS Citambal</title> 

    <style> 

•	{ 

            Margin: 0; 

            Padding: 0; 

            Box-sizing: border-box; 

        } 

 

        Body { 

            Font-family: ‘Segoe UI’, Tahoma, Geneva, Verdana, sans-serif; 

            Background: linear-gradient(135deg, #4CAF50 0%, #2E7D32 100%); 

            Color: #333; 

            Min-height: 100vh; 

            Overflow-x: hidden; 

        } 

 

        .app-container { 

            Max-width: 414px; 

            Margin: 0 auto; 

            Background: #f8f9fa; 

            Min-height: 100vh; 

            Box-shadow: 0 0 20px rgba(0,0,0,0.1); 

            Position: relative; 

        } 

 

        .header { 

            Background: linear-gradient(135deg, #4CAF50 0%, #66BB6A 100%); 

            Color: white; 

            Padding: 20px; 

            Text-align: center; 

            Position: relative; 

            Overflow: hidden; 

        } 

 

        .header::before { 

            Content: ‘’; 

            Position: absolute; 

            Top: -50%; 

            Left: -50%; 

            Width: 200%; 

            Height: 200%; 

            Background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, transparent 70%); 

            Animation: rotate 8s linear infinite; 

        } 

 

        @keyframes rotate { 

            0% { transform: rotate(0deg); } 

            100% { transform: rotate(360deg); } 

        } 

 

        .logo-container { 

            Display: flex; 

            Align-items: center; 

            Justify-content: center; 

            Margin-bottom: 10px; 

            Position: relative; 

            z-index: 2; 

        } 

 

        .logo { 

            Font-size: 32px; 

            Margin-right: 10px; 

        } 

 

        .bank-name { 

            Font-size: 24px; 

            Font-weight: bold; 

            Line-height: 1.2; 

        } 

 

        .location { 

            Font-size: 14px; 

            Opacity: 0.9; 

            Margin-top: 5px; 

            Position: relative; 

            z-index: 2; 

        } 

 

        .balance-section { 

            Background: white; 

            Margin: -15px 20px 20px; 

            Padding: 25px; 

            Border-radius: 20px; 

            Box-shadow: 0 10px 30px rgba(76, 175, 80, 0.2); 

            Position: relative; 

            Overflow: hidden; 

        } 

 

        .balance-section::before { 

            Content: ‘’; 

            Position: absolute; 

            Top: 0; 

            Right: 0; 

            Width: 100px; 

            Height: 100px; 

            Background: radial-gradient(circle, rgba(76, 175, 80, 0.1) 0%, transparent 70%); 

            Border-radius: 50%; 

            Transform: translate(30px, -30px); 

        } 

 

        .member-info { 

            Display: flex; 

            Align-items: center; 

            Margin-bottom: 20px; 

        } 

 

        .member-avatar { 

            Width: 50px; 

            Height: 50px; 

            Background: linear-gradient(135deg, #4CAF50, #66BB6A); 

            Border-radius: 50%; 

            Display: flex; 

            Align-items: center; 

            Justify-content: center; 

            Font-size: 24px; 

            Margin-right: 15px; 

            Color: white; 

        } 

 

        .member-details h3 { 

            Font-size: 18px; 

            Color: #333; 

            Margin-bottom: 3px; 

        } 

 

        .member-id { 

            Font-size: 12px; 

            Color: #666; 

            Background: #e8f5e8; 

            Padding: 2px 8px; 

            Border-radius: 10px; 

            Display: inline-block; 

        } 

 

        .balance-display { 

            Text-align: center; 

            Margin-bottom: 20px; 

        } 

 

        .balance-label { 

            Font-size: 14px; 

            Color: #666; 

            Margin-bottom: 8px; 

        } 

 

        .balance-amount { 

            Font-size: 36px; 

            Font-weight: bold; 

            Color: #4CAF50; 

            Margin-bottom: 5px; 

        } 

 

        .balance-weight { 

            Font-size: 14px; 

            Color: #666; 

            Background: #f0f8f0; 

            Padding: 5px 12px; 

            Border-radius: 15px; 

            Display: inline-block; 

        } 

 

        .action-buttons { 

            Display: grid; 

            Grid-template-columns: 1fr 1fr; 

            Gap: 10px; 

            Margin-top: 20px; 

        } 

 

        .action-btn { 

            Background: linear-gradient(135deg, #4CAF50, #66BB6A); 

            Color: white; 

            Border: none; 

            Padding: 12px; 

            Border-radius: 12px; 

            Font-size: 14px; 

            Font-weight: 600; 

            Cursor: pointer; 

            Transition: all 0.3s ease; 

            Display: flex; 

            Align-items: center; 

            Justify-content: center; 

            Gap: 8px; 

        } 

 

        .action-btn:hover { 

            Transform: translateY(-2px); 

            Box-shadow: 0 5px 15px rgba(76, 175, 80, 0.3); 

        } 

 

        .action-btn.secondary { 

            Background: linear-gradient(135deg, #FF9800, #F57C00); 

        } 

 

        .menu-section { 

            Padding: 0 20px 20px; 

        } 

 

        .section-title { 

            Font-size: 18px; 

            Font-weight: bold; 

            Color: #333; 

            Margin: 20px 0 15px; 

            Display: flex; 

            Align-items: center; 

            Gap: 10px; 

        } 

 

        .menu-grid { 

            Display: grid; 

            Grid-template-columns: repeat(3, 1fr); 

            Gap: 15px; 

            Margin-bottom: 20px; 

        } 

 

        .menu-item { 

            Background: white; 

            Border-radius: 15px; 

            Padding: 20px 15px; 

            Text-align: center; 

            Box-shadow: 0 5px 15px rgba(0,0,0,0.08); 

            Cursor: pointer; 

            Transition: all 0.3s ease; 

            Border: 1px solid #e8f5e8; 

        } 

 

        .menu-item:hover { 

            Transform: translateY(-5px); 

            Box-shadow: 0 10px 25px rgba(0,0,0,0.15); 

        } 

 

        .menu-icon { 

            Width: 50px; 

            Height: 50px; 

            Margin: 0 auto 12px; 

            Border-radius: 50%; 

            Display: flex; 

            Align-items: center; 

            Justify-content: center; 

            Font-size: 24px; 

            Color: white; 

        } 

 

        .menu-icon.deposit { background: linear-gradient(135deg, #4CAF50, #66BB6A); } 

        .menu-icon.withdraw { background: linear-gradient(135deg, #2196F3, #42A5F5); } 

        .menu-icon.history { background: linear-gradient(135deg, #FF9800, #FFA726); } 

        .menu-icon.catalog { background: linear-gradient(135deg, #9C27B0, #BA68C8); } 

        .menu-icon.education { background: linear-gradient(135deg, #F44336, #EF5350); } 

        .menu-icon.community { background: linear-gradient(135deg, #795548, #8D6E63); } 

 

        .menu-text { 

            Font-size: 12px; 

            Color: #333; 

            Font-weight: 600; 

            Line-height: 1.3; 

        } 

 

        .stats-section { 

            Background: white; 

            Margin: 0 20px 20px; 

            Padding: 20px; 

            Border-radius: 15px; 

            Box-shadow: 0 5px 15px rgba(0,0,0,0.08); 

        } 

 

        .stats-grid { 

            Display: grid; 

            Grid-template-columns: repeat(3, 1fr); 

            Gap: 15px; 

        } 

 

        .stat-item { 

            Text-align: center; 

            Padding: 15px 10px; 

            Border-radius: 12px; 

            Background: #f8f9fa; 

        } 

 

        .stat-value { 

            Font-size: 20px; 

            Font-weight: bold; 

            Color: #4CAF50; 

            Margin-bottom: 5px; 

        } 

 

        .stat-label { 

            Font-size: 11px; 

            Color: #666; 

            Line-height: 1.3; 

        } 

 

        .activity-section { 

            Background: white; 

            Margin: 0 20px 80px; 

            Padding: 20px; 

            Border-radius: 15px; 

            Box-shadow: 0 5px 15px rgba(0,0,0,0.08); 

        } 

 

        .activity-item { 

            Display: flex; 

            Align-items: center; 

            Padding: 15px 0; 

            Border-bottom: 1px solid #f0f0f0; 

        } 

 

        .activity-item:last-child { 

            Border-bottom: none; 

        } 

 

        .activity-icon { 

            Width: 45px; 

            Height: 45px; 

            Border-radius: 50%; 

            Display: flex; 

            Align-items: center; 

            Justify-content: center; 

            Margin-right: 15px; 

            Font-size: 20px; 

            Color: white; 

        } 

 

        .activity-icon.deposit { background: linear-gradient(135deg, #4CAF50, #66BB6A); } 

        .activity-icon.withdraw { background: linear-gradient(135deg, #2196F3, #42A5F5); } 

        .activity-icon.bonus { background: linear-gradient(135deg, #FF9800, #FFA726); } 

 

        .activity-info { 

            Flex: 1; 

        } 

 

        .activity-title { 

            Font-weight: 600; 

            Color: #333; 

            Margin-bottom: 3px; 

            Font-size: 14px; 

        } 

 

        .activity-date { 

            Font-size: 12px; 

            Color: #666; 

        } 

 

        .activity-amount { 

            Font-weight: bold; 

            Font-size: 14px; 

        } 

 

        .activity-amount.positive { color: #4CAF50; } 

        .activity-amount.negative { color: #F44336; } 

 

        .bottom-nav { 

            Position: fixed; 

            Bottom: 0; 

            Left: 50%; 

            Transform: translateX(-50%); 

            Width: 100%; 

            Max-width: 414px; 

            Background: white; 

            Border-top: 1px solid #e0e0e0; 

            Display: flex; 

            Padding: 10px 0; 

            Box-shadow: 0 -5px 15px rgba(0,0,0,0.1); 

        } 

 

        .nav-item { 

            Flex: 1; 

            Text-align: center; 

            Padding: 10px; 

            Cursor: pointer; 

            Transition: all 0.3s ease; 

            Color: #666; 

        } 

 

        .nav-item.active { 

            Color: #4CAF50; 

        } 

 

        .nav-icon { 

            Font-size: 22px; 

            Margin-bottom: 5px; 

        } 

 

        .nav-text { 

            Font-size: 10px; 

            Font-weight: 600; 

        } 

 

        .floating-btn { 

            Position: fixed; 

            Bottom: 80px; 

            Right: 20px; 

            Width: 60px; 

            Height: 60px; 

            Background: linear-gradient(135deg, #4CAF50, #66BB6A); 

            Border-radius: 50%; 

            Display: flex; 

            Align-items: center; 

            Justify-content: center; 

            Color: white; 

            Font-size: 28px; 

            Cursor: pointer; 

            Box-shadow: 0 10px 25px rgba(76, 175, 80, 0.4); 

            Transition: all 0.3s ease; 

            Animation: pulse 2s infinite; 

        } 

 

        @keyframes pulse { 

            0% { box-shadow: 0 10px 25px rgba(76, 175, 80, 0.4); } 

            50% { box-shadow: 0 15px 35px rgba(76, 175, 80, 0.6); } 

            100% { box-shadow: 0 10px 25px rgba(76, 175, 80, 0.4); } 

        } 

 

        .notification-banner { 

            Background: linear-gradient(135deg, #E3F2FD, #BBDEFB); 

            Margin: 0 20px 20px; 

            Padding: 15px; 

            Border-radius: 12px; 

            Border-left: 4px solid #2196F3; 

            Display: flex; 

            Align-items: center; 

            Cursor: pointer; 

        } 

 

        .notification-icon { 

            Font-size: 24px; 

            Margin-right: 12px; 

            Color: #2196F3; 

        } 

 

        .notification-text { 

            Flex: 1; 

            Font-size: 13px; 

            Color: #333; 

        } 

 

        .achievement-badge { 

            Position: absolute; 

            Top: 10px; 

            Right: 10px; 

            Background: #FF9800; 

            Color: white; 

            Padding: 5px 10px; 

            Border-radius: 12px; 

            Font-size: 10px; 

            Font-weight: bold; 

            Animation: bounce 2s infinite; 

        } 

 

        @keyframes bounce { 

            0%, 20%, 50%, 80%, 100% { transform: translateY(0); } 

            40% { transform: translateY(-10px); } 

            60% { transform: translateY(-5px); } 

        } 

 

        @media (max-width: 375px) { 

            .menu-grid { 

                Grid-template-columns: repeat(2, 1fr); 

            } 

             

            .balance-amount { 

                Font-size: 32px; 

            } 

             

            .stats-grid { 

                Grid-template-columns: repeat(2, 1fr); 

            } 

        } 

 

        .modal { 

            Display: none; 

            Position: fixed; 

            Top: 0; 

            Left: 0; 

            Width: 100%; 

            Height: 100%; 

            Background: rgba(0,0,0,0.5); 

            z-index: 1000; 

            backdrop-filter: blur(5px); 

        } 

 

        .modal-content { 

            Position: absolute; 

            Top: 50%; 

            Left: 50%; 

            Transform: translate(-50%, -50%); 

            Background: white; 

            Padding: 30px; 

            Border-radius: 20px; 

            Width: 90%; 

            Max-width: 350px; 

            Text-align: center; 

            Box-shadow: 0 20px 40px rgba(0,0,0,0.3); 

        } 

 

        .modal-icon { 

            Font-size: 48px; 

            Margin-bottom: 15px; 

        } 

 

        .modal-title { 

            Font-size: 20px; 

            Font-weight: bold; 

            Margin-bottom: 10px; 

            Color: #333; 

        } 

 

        .modal-text { 

            Font-size: 14px; 

            Color: #666; 

            Margin-bottom: 20px; 

            Line-height: 1.5; 

        } 

 

        .modal-btn { 

            Background: linear-gradient(135deg, #4CAF50, #66BB6A); 

            Color: white; 

            Border: none; 

            Padding: 12px 30px; 

            Border-radius: 25px; 

            Font-size: 14px; 

            Font-weight: 600; 

            Cursor: pointer; 

            Transition: all 0.3s ease; 

        } 

 

        .modal-btn:hover { 

            Transform: translateY(-2px); 

            Box-shadow: 0 5px 15px rgba(76, 175, 80, 0.3); 

        } 

    </style> 

</head> 

<body> 

    <div class=”app-container”> 

        <!—Header  

        <div class=”header”> 

            <div class=”achievement-badge”>🏆 ®™ rung’s</div> 

            <div class=”logo-container”> 

                <div class=”logo”>♻️</div> 

                <div> 

                    <div class=”bank-name”>BANK SAMPAH ARAS</div> 

                    <div class=”location”> Dusun Citambal Desa Karanglayung Kecamatan Karangjaya Kabupaten Tasikmalaya Jawa Barat 46199</div> 

                </div> 

            </div> 

        </div> 

 

        <!—Balance Section  

        <div class=”balance-section”> 

            <div class=”member-info”> 

                <div class=”member-avatar”>👤</div> 

                <div class=”member-details”> 

                    <h3>Ajis Abdul Jabar</h3> 

                    <div class=”member-id”>ID: ARAS-001</div> 

                </div> 

            </div> 

             

            <div class=”balance-display”> 

                <div class=”balance-label”>Saldo Tabungan Sampah</div> 

                <div class=”balance-amount”>Rp 347.500</div> 

                <div class=”balance-weight”>Total: 89.2 kg</div> 

            </div> 

 

            <div class=”action-buttons”> 

                <button class=”action-btn” onclick=”showDeposit()”> 

                    ♻️ Setor Sampah 

                </button> 

                <button class=”action-btn secondary” onclick=”showWithdraw()”> 

                    💰 Tarik Saldo 

                </button> 

            </div> 

        </div> 

 

        <!—Notification Banner  

        <div class=”notification-banner” onclick=”showNotification()”> 

            <div class=”notification-icon”>📢</div> 

            <div class=”notification-text”> 

                <strong>Pengumuman:</strong> Jadwal pengambilan sampah Senin & Kamis jam 08:00 WIB 

            </div> 

        </div> 

 

        <!—Menu Section  

        <div class=”menu-section”> 

            <div class=”section-title”> 

                🏠 Layanan Bank Sampah 

            </div> 

            <div class=”menu-grid”> 

                <div class=”menu-item” onclick=”showDeposit()”> 

                    <div class=”menu-icon deposit”>♻️</div> 

                    <div class=”menu-text”>Setor Sampah</div> 

                </div> 

                <div class=”menu-item” onclick=”showWithdraw()”> 

                    <div class=”menu-icon withdraw”>💰</div> 

                    <div class=”menu-text”>Tarik Saldo</div> 

                </div> 

                <div class=”menu-item” onclick=”showHistory()”> 

                    <div class=”menu-icon history”>📊</div> 

                    <div class=”menu-text”>Riwayat Transaksi</div> 

                </div> 

                <div class=”menu-item” onclick=”showCatalog()”> 

                    <div class=”menu-icon catalog”>📋</div> 

                    <div class=”menu-text”>Katalog Sampah</div> 

                </div> 

                <div class=”menu-item” onclick=”showEducation()”> 

                    <div class=”menu-icon education”>📚</div> 

                    <div class=”menu-text”>Edukasi Lingkungan</div> 

                </div> 

                <div class=”menu-item” onclick=”showCommunity()”> 

                    <div class=”menu-icon community”>👥</div> 

                    <div class=”menu-text”>Komunitas</div> 

                </div> 

            </div> 

        </div> 

 

        <!—Statistics Section  

        <div class=”stats-section”> 

            <div class=”section-title”>📈 Statistik Bulan Ini</div> 

            <div class=”stats-grid”> 

                <div class=”stat-item”> 

                    <div class=”stat-value”>23.4</div> 

                    <div class=”stat-label”>kg Sampah Disetor</div> 

                </div> 

                <div class=”stat-item”> 

                    <div class=”stat-value”>78.500</div> 

                    <div class=”stat-label”>Rupiah Diperoleh</div> 

                </div> 

                <div class=”stat-item”> 

                    <div class=”stat-value”>12</div> 

                    <div class=”stat-label”>Transaksi</div> 

                </div> 

            </div> 

        </div> 

 

        <!—Activity Section  

        <div class=”activity-section”> 

            <div class=”section-title”>🕒 Aktivitas Terbaru</div> 

             

            <div class=”activity-item”> 

                <div class=”activity-icon deposit”>♻️</div> 

                <div class=”activity-info”> 

                    <div class=”activity-title”>Setor Sampah Plastik</div> 

                    <div class=”activity-date”>Hari ini, 14:30 – 2.5 kg</div> 

                </div> 

                <div class=”activity-amount positive”>+Rp 12.500</div> 

            </div> 

 

            <div class=”activ<!DOCTYPE html> 

<html lang=”id”> 

<head> 

    <meta charset=”UTF-8”> 

    <meta name=”viewport” content=”width=device-width, initial-scale=1.0”> 

    <title>Bank Sampah Karangtaruna ARAS Citambal</title> 

    <style> 

•	{ 

            Margin: 0; 

            Padding: 0; 

            Box-sizing: border-box; 

        } 

 

        Body { 

            Font-family: ‘Segoe UI’, Tahoma, Geneva, Verdana, sans-serif; 

            Background: linear-gradient(135deg, #4CAF50 0%, #2E7D32 100%); 

            Color: #333; 

            Min-height: 100vh; 

            Overflow-x: hidden; 

        } 

 

        .app-container { 

            Max-width: 414px; 

            Margin: 0 auto; 

            Background: #f8f9fa; 

            Min-height: 100vh; 

            Box-shadow: 0 0 20px rgba(0,0,0,0.1); 

            Position: relative; 

        } 

 

        .header { 

            Background: linear-gradient(135deg, #4CAF50 0%, #66BB6A 100%); 

            Color: white; 

            Padding: 20px; 

            Text-align: center; 

            Position: relative; 

            Overflow: hidden; 

        } 

 

        .header::before { 

            Content: ‘’; 

            Position: absolute; 

            Top: -50%; 

            Left: -50%; 

            Width: 200%; 

            Height: 200%; 

            Background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, transparent 70%); 

            Animation: rotate 8s linear infinite; 

        } 

 

        @keyframes rotate { 

            0% { transform: rotate(0deg); } 

            100% { transform: rotate(360deg); } 

        } 

 

        .logo-container { 

            Display: flex; 

            Align-items: center; 

            Justify-content: center; 

            Margin-bottom: 10px; 

            Position: relative; 

            z-index: 2; 

        } 

 

        .logo { 

            Font-size: 32px; 

            Margin-right: 10px; 

        } 

 

        .bank-name { 

            Font-size: 24px; 

            Font-weight: bold; 

            Line-height: 1.2; 

        } 

 

        .location { 

            Font-size: 14px; 

            Opacity: 0.9; 

            Margin-top: 5px; 

            Position: relative; 

            z-index: 2; 

        } 

 

        .balance-section { 

            Background: white; 

            Margin: -15px 20px 20px; 

            Padding: 25px; 

            Border-radius: 20px; 

            Box-shadow: 0 10px 30px rgba(76, 175, 80, 0.2); 

            Position: relative; 

            Overflow: hidden; 

        } 

 

        .balance-section::before { 

            Content: ‘’; 

            Position: absolute; 

            Top: 0; 

            Right: 0; 

            Width: 100px; 

            Height: 100px; 

            Background: radial-gradient(circle, rgba(76, 175, 80, 0.1) 0%, transparent 70%); 

            Border-radius: 50%; 

            Transform: translate(30px, -30px); 

        } 

 

        .member-info { 

            Display: flex; 

            Align-items: center; 

            Margin-bottom: 20px; 

        } 

 

        .member-avatar { 

            Width: 50px; 

            Height: 50px; 

            Background: linear-gradient(135deg, #4CAF50, #66BB6A); 

            Border-radius: 50%; 

            Display: flex; 

            Align-items: center; 

            Justify-content: center; 

            Font-size: 24px; 

            Margin-right: 15px; 

            Color: white; 

        } 

 

        .member-details h3 { 

            Font-size: 18px; 

            Color: #333; 

            Margin-bottom: 3px; 

        } 

 

        .member-id { 

            Font-size: 12px; 

            Color: #666; 

            Background: #e8f5e8; 

            Padding: 2px 8px; 

            Border-radius: 10px; 

            Display: inline-block; 

        } 

 

        .balance-display { 

            Text-align: center; 

            Margin-bottom: 20px; 

        } 

 

        .balance-label { 

            Font-size: 14px; 

            Color: #666; 

            Margin-bottom: 8px; 

        } 

 

        .balance-amount { 

            Font-size: 36px; 

            Font-weight: bold; 

            Color: #4CAF50; 

            Margin-bottom: 5px; 

        } 

 

        .balance-weight { 

            Font-size: 14px; 

            Color: #666; 

            Background: #f0f8f0; 

            Padding: 5px 12px; 

            Border-radius: 15px; 

            Display: inline-block; 

        } 

 

        .action-buttons { 

            Display: grid; 

            Grid-template-columns: 1fr 1fr; 

            Gap: 10px; 

            Margin-top: 20px; 

        } 

 

        .action-btn { 

            Background: linear-gradient(135deg, #4CAF50, #66BB6A); 

            Color: white; 

            Border: none; 

            Padding: 12px; 

            Border-radius: 12px; 

            Font-size: 14px; 

            Font-weight: 600; 

            Cursor: pointer; 

            Transition: all 0.3s ease; 

            Display: flex; 

            Align-items: center; 

            Justify-content: center; 

            Gap: 8px; 

        } 

 

        .action-btn:hover { 

            Transform: translateY(-2px); 

            Box-shadow: 0 5px 15px rgba(76, 175, 80, 0.3); 

        } 

 

        .action-btn.secondary { 

            Background: linear-gradient(135deg, #FF9800, #F57C00); 

        } 

 

        .menu-section { 

            Padding: 0 20px 20px; 

        } 

 

        .section-title { 

            Font-size: 18px; 

            Font-weight: bold; 

            Color: #333; 

            Margin: 20px 0 15px; 

            Display: flex; 

            Align-items: center; 

            Gap: 10px; 

        } 

 

        .menu-grid { 

            Display: grid; 

            Grid-template-columns: repeat(3, 1fr); 

            Gap: 15px; 

            Margin-bottom: 20px; 

        } 

 

        .menu-item { 

            Background: white; 

            Border-radius: 15px; 

            Padding: 20px 15px; 

            Text-align: center; 

            Box-shadow: 0 5px 15px rgba(0,0,0,0.08); 

            Cursor: pointer; 

            Transition: all 0.3s ease; 

            Border: 1px solid #e8f5e8; 

        } 

 

        .menu-item:hover { 

            Transform: translateY(-5px); 

            Box-shadow: 0 10px 25px rgba(0,0,0,0.15); 

        } 

 

        .menu-icon { 

            Width: 50px; 

            Height: 50px; 

            Margin: 0 auto 12px; 

            Border-radius: 50%; 

            Display: flex; 

            Align-items: center; 

            Justify-content: center; 

            Font-size: 24px; 

            Color: white; 

        } 

 

        .menu-icon.deposit { background: linear-gradient(135deg, #4CAF50, #66BB6A); } 

        .menu-icon.withdraw { background: linear-gradient(135deg, #2196F3, #42A5F5); } 

        .menu-icon.history { background: linear-gradient(135deg, #FF9800, #FFA726); } 

        .menu-icon.catalog { background: linear-gradient(135deg, #9C27B0, #BA68C8); } 

        .menu-icon.education { background: linear-gradient(135deg, #F44336, #EF5350); } 

        .menu-icon.community { background: linear-gradient(135deg, #795548, #8D6E63); } 

 

        .menu-text { 

            Font-size: 12px; 

            Color: #333; 

            Font-weight: 600; 

            Line-height: 1.3; 

        } 

 

        .stats-section { 

            Background: white; 

            Margin: 0 20px 20px; 

            Padding: 20px; 

            Border-radius: 15px; 

            Box-shadow: 0 5px 15px rgba(0,0,0,0.08); 

        } 

 

        .stats-grid { 

            Display: grid; 

            Grid-template-columns: repeat(3, 1fr); 

            Gap: 15px; 

        } 

 

        .stat-item { 

            Text-align: center; 

            Padding: 15px 10px; 

            Border-radius: 12px; 

            Background: #f8f9fa; 

        } 

 

        .stat-value { 

            Font-size: 20px; 

            Font-weight: bold; 

            Color: #4CAF50; 

            Margin-bottom: 5px; 

        } 

 

        .stat-label { 

            Font-size: 11px; 

            Color: #666; 

            Line-height: 1.3; 

        } 

 

        .activity-section { 

            Background: white; 

            Margin: 0 20px 80px; 

            Padding: 20px; 

            Border-radius: 15px; 

            Box-shadow: 0 5px 15px rgba(0,0,0,0.08); 

        } 

 

        .activity-item { 

            Display: flex; 

            Align-items: center; 

            Padding: 15px 0; 

            Border-bottom: 1px solid #f0f0f0; 

        } 

 

        .activity-item:last-child { 

            Border-bottom: none; 

        } 

 

        .activity-icon { 

            Width: 45px; 

            Height: 45px; 

            Border-radius: 50%; 

            Display: flex; 

            Align-items: center; 

            Justify-content: center; 

            Margin-right: 15px; 

            Font-size: 20px; 

            Color: white; 

        } 

 

        .activity-icon.deposit { background: linear-gradient(135deg, #4CAF50, #66BB6A); } 

        .activity-icon.withdraw { background: linear-gradient(135deg, #2196F3, #42A5F5); } 

        .activity-icon.bonus { background: linear-gradient(135deg, #FF9800, #FFA726); } 

 

        .activity-info { 

            Flex: 1; 

        } 

 

        .activity-title { 

            Font-weight: 600; 

            Color: #333; 

            Margin-bottom: 3px; 

            Font-size: 14px; 

        } 

 

        .activity-date { 

            Font-size: 12px; 

            Color: #666; 

        } 

 

        .activity-amount { 

            Font-weight: bold; 

            Font-size: 14px; 

        } 

 

        .activity-amount.positive { color: #4CAF50; } 

        .activity-amount.negative { color: #F44336; } 

 

        .bottom-nav { 

            Position: fixed; 

            Bottom: 0; 

            Left: 50%; 

            Transform: translateX(-50%); 

            Width: 100%; 

            Max-width: 414px; 

            Background: white; 

            Border-top: 1px solid #e0e0e0; 

            Display: flex; 

            Padding: 10px 0; 

            Box-shadow: 0 -5px 15px rgba(0,0,0,0.1); 

        } 

 

        .nav-item { 

            Flex: 1; 

            Text-align: center; 

            Padding: 10px; 

            Cursor: pointer; 

            Transition: all 0.3s ease; 

            Color: #666; 

        } 

 

        .nav-item.active { 

            Color: #4CAF50; 

        } 

 

        .nav-icon { 

            Font-size: 22px; 

            Margin-bottom: 5px; 

        } 

 

        .nav-text { 

            Font-size: 10px; 

            Font-weight: 600; 

        } 

 

        .floating-btn { 

            Position: fixed; 

            Bottom: 80px; 

            Right: 20px; 

            Width: 60px; 

            Height: 60px; 

            Background: linear-gradient(135deg, #4CAF50, #66BB6A); 

            Border-radius: 50%; 

            Display: flex; 

            Align-items: center; 

            Justify-content: center; 

            Color: white; 

            Font-size: 28px; 

            Cursor: pointer; 

            Box-shadow: 0 10px 25px rgba(76, 175, 80, 0.4); 

            Transition: all 0.3s ease; 

            Animation: pulse 2s infinite; 

        } 

 

        @keyframes pulse { 

            0% { box-shadow: 0 10px 25px rgba(76, 175, 80, 0.4); } 

            50% { box-shadow: 0 15px 35px rgba(76, 175, 80, 0.6); } 

            100% { box-shadow: 0 10px 25px rgba(76, 175, 80, 0.4); } 

        } 

 

        .notification-banner { 

            Background: linear-gradient(135deg, #E3F2FD, #BBDEFB); 

            Margin: 0 20px 20px; 

            Padding: 15px; 

            Border-radius: 12px; 

            Border-left: 4px solid #2196F3; 

            Display: flex; 

            Align-items: center; 

            Cursor: pointer; 

        } 

 

        .notification-icon { 

            Font-size: 24px; 

            Margin-right: 12px; 

            Color: #2196F3; 

        } 

 

        .notification-text { 

            Flex: 1; 

            Font-size: 13px; 

            Color: #333; 

        } 

 

        .achievement-badge { 

            Position: absolute; 

            Top: 10px; 

            Right: 10px; 

            Background: #FF9800; 

            Color: white; 

            Padding: 5px 10px; 

            Border-radius: 12px; 

            Font-size: 10px; 

            Font-weight: bold; 

            Animation: bounce 2s infinite; 

        } 

 

        @keyframes bounce { 

            0%, 20%, 50%, 80%, 100% { transform: translateY(0); } 

            40% { transform: translateY(-10px); } 

            60% { transform: translateY(-5px); } 

        } 

 

        @media (max-width: 375px) { 

            .menu-grid { 

                Grid-template-columns: repeat(2, 1fr); 

            } 

             

            .balance-amount { 

                Font-size: 32px; 

            } 

             

            .stats-grid { 

                Grid-template-columns: repeat(2, 1fr); 

            } 

        } 

 

        .modal { 

            Display: none; 

            Position: fixed; 

            Top: 0; 

            Left: 0; 

            Width: 100%; 

            Height: 100%; 

            Background: rgba(0,0,0,0.5); 

            z-index: 1000; 

            backdrop-filter: blur(5px); 

        } 

 

        .modal-content { 

            Position: absolute; 

            Top: 50%; 

            Left: 50%; 

            Transform: translate(-50%, -50%); 

            Background: white; 

            Padding: 30px; 

            Border-radius: 20px; 

            Width: 90%; 

            Max-width: 350px; 

            Text-align: center; 

            Box-shadow: 0 20px 40px rgba(0,0,0,0.3); 

        } 

 

        .modal-icon { 

            Font-size: 48px; 

            Margin-bottom: 15px; 

        } 

 

        .modal-title { 

            Font-size: 20px; 

            Font-weight: bold; 

            Margin-bottom: 10px; 

            Color: #333; 

        } 

 

        .modal-text { 

            Font-size: 14px; 

            Color: #666; 

            Margin-bottom: 20px; 

            Line-height: 1.5; 

        } 

 

        .modal-btn { 

            Background: linear-gradient(135deg, #4CAF50, #66BB6A); 

            Color: white; 

            Border: none; 

            Padding: 12px 30px; 

            Border-radius: 25px; 

            Font-size: 14px; 

            Font-weight: 600; 

            Cursor: pointer; 

            Transition: all 0.3s ease; 

        } 

 

        .modal-btn:hover { 

            Transform: translateY(-2px); 

            Box-shadow: 0 5px 15px rgba(76, 175, 80, 0.3); 

        } 

    </style> 

</head> 

<body> 

    <div class=”app-container”> 

        <!—Header  

        <div class=”header”> 

            <div class=”achievement-badge”>🏆 ®™ rung’s</div> 

            <div class=”logo-container”> 

                <div class=”logo”>♻️</div> 

                <div> 

                    <div class=”bank-name”>BANK SAMPAH ARAS</div> 

                    <div class=”location”> Dusun Citambal Desa Karanglayung Kecamatan Karangjaya Kabupaten Tasikmalaya Jawa Barat 46199</div> 

                </div> 

            </div> 

        </div> 

 

        <!—Balance Section  

        <div class=”balance-section”> 

            <div class=”member-info”> 

                <div class=”member-avatar”>👤</div> 

                <div class=”member-details”> 

                    <h3>Ajis Abdul Jabar</h3> 

                    <div class=”member-id”>ID: ARAS-001</div> 

                </div> 

            </div> 

             

            <div class=”balance-display”> 

                <div class=”balance-label”>Saldo Tabungan Sampah</div> 

                <div class=”balance-amount”>Rp 347.500</div> 

                <div class=”balance-weight”>Total: 89.2 kg</div> 

            </div> 

 

            <div class=”action-buttons”> 

                <button class=”action-btn” onclick=”showDeposit()”> 

                    ♻️ Setor Sampah 

                </button> 

                <button class=”action-btn secondary” onclick=”showWithdraw()”> 

                    💰 Tarik Saldo 

                </button> 

            </div> 

        </div> 

 

        <!—Notification Banner  

        <div class=”notification-banner” onclick=”showNotification()”> 

            <div class=”notification-icon”>📢</div> 

            <div class=”notification-text”> 

                <strong>Pengumuman:</strong> Jadwal pengambilan sampah Senin & Kamis jam 08:00 WIB 

            </div> 

        </div> 

 

        <!—Menu Section  

        <div class=”menu-section”> 

            <div class=”section-title”> 

                🏠 Layanan Bank Sampah 

            </div> 

            <div class=”menu-grid”> 

                <div class=”menu-item” onclick=”showDeposit()”> 

                    <div class=”menu-icon deposit”>♻️</div> 

                    <div class=”menu-text”>Setor Sampah</div> 

                </div> 

                <div class=”menu-item” onclick=”showWithdraw()”> 

                    <div class=”menu-icon withdraw”>💰</div> 

                    <div class=”menu-text”>Tarik Saldo</div> 

                </div> 

                <div class=”menu-item” onclick=”showHistory()”> 

                    <div class=”menu-icon history”>📊</div> 

                    <div class=”menu-text”>Riwayat Transaksi</div> 

                </div> 

                <div class=”menu-item” onclick=”showCatalog()”> 

                    <div class=”menu-icon catalog”>📋</div> 

                    <div class=”menu-text”>Katalog Sampah</div> 

                </div> 

                <div class=”menu-item” onclick=”showEducation()”> 

                    <div class=”menu-icon education”>📚</div> 

                    <div class=”menu-text”>Edukasi Lingkungan</div> 

                </div> 

                <div class=”menu-item” onclick=”showCommunity()”> 

                    <div class=”menu-icon community”>👥</div> 

                    <div class=”menu-text”>Komunitas</div> 

                </div> 

            </div> 

        </div> 

 

        <!—Statistics Section  

        <div class=”stats-section”> 

            <div class=”section-title”>📈 Statistik Bulan Ini</div> 

            <div class=”stats-grid”> 

                <div class=”stat-item”> 

                    <div class=”stat-value”>23.4</div> 

                    <div class=”stat-label”>kg Sampah Disetor</div> 

                </div> 

                <div class=”stat-item”> 

                    <div class=”stat-value”>78.500</div> 

                    <div class=”stat-label”>Rupiah Diperoleh</div> 

                </div> 

                <div class=”stat-item”> 

                    <div class=”stat-value”>12</div> 

                    <div class=”stat-label”>Transaksi</div> 

                </div> 

            </div> 

        </div> 

 

        <!—Activity Section  

        <div class=”activity-section”> 

            <div class=”section-title”>🕒 Aktivitas Terbaru</div> 

             

            <div class=”activity-item”> 

                <div class=”activity-icon deposit”>♻️</div> 

                <div class=”activity-info”> 

                    <div class=”activity-title”>Setor Sampah Plastik</div> 

                    <div class=”activity-date”>Hari ini, 14:30 – 2.5 kg</div> 

                </div> 

                <div class=”activity-amount positive”>+Rp 12.500</div> 

            </div> 

 

            <div class=”activity-item”> 

                <div class=”activity-icon bonus”>🎁</div> 

                <div class=”activity-info”> 

                    <div class=”activity-title”>Bonus Konsistensi</div> 

                    <div class=”activity-date”>Kemarin, 16:00</div> 

                </div> 

                <div class=”activity-amount positive”>+Rp 5.000</div> 

            </div> 

 

            <div class=”activity-item”> 

                <div class=”activity-icon deposit”>♻️</div> 

                <div class=”activity-info”> 

                    <div class=”activity-title”>Setor Sampah Kertas</div> 

                    <div class=”activity-date”>2 haity-item”> 

                <div class=”activity-icon bonus”>🎁</div> 

                <div class=”activity-info”> 

                    <div class=”activity-title”>Bonus Konsistensi</div> 

                    <div class=”activity-date”>Kemarin, 16:00</div> 

                </div> 

                <div class=”activity-amount positive”>+Rp 5.000</div> 

            </div> 

 

            <div class=”activity-item”> 

                <div class=”activity-icon deposit”>♻️</div> 

                <div class=”activity-info”> 

                    <div class=”activity-title”>Setor Sampah Kertas</div> 

                    <div class=”activity-date”>2 ha
