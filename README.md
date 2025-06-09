<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bank Sampah ARAS Citambal</title>
    <style>
        /* [SELURUH KODE CSS ANDA SAYA BIARKAN DI SINI, SUDAH SANGAT BAGUS] */
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; background: linear-gradient(135deg, #4CAF50 0%, #2E7D32 100%); color: #333; min-height: 100vh; overflow-x: hidden; }
        .app-container { max-width: 414px; margin: 0 auto; background: #f8f9fa; min-height: 100vh; box-shadow: 0 0 20px rgba(0,0,0,0.1); position: relative; }
        .header { background: linear-gradient(135deg, #4CAF50 0%, #66BB6A 100%); color: white; padding: 20px; text-align: center; position: relative; overflow: hidden; }
        .header::before { content: ''; position: absolute; top: -50%; left: -50%; width: 200%; height: 200%; background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, transparent 70%); animation: rotate 8s linear infinite; }
        @keyframes rotate { from { transform: rotate(0deg); } to { transform: rotate(360deg); } }
        .logo-container { display: flex; align-items: center; justify-content: center; margin-bottom: 10px; position: relative; z-index: 2; }
        .logo { font-size: 32px; margin-right: 10px; }
        .bank-name { font-size: 24px; font-weight: bold; line-height: 1.2; }
        .location { font-size: 14px; opacity: 0.9; margin-top: 5px; position: relative; z-index: 2; }
        .balance-section { background: white; margin: -15px 20px 20px; padding: 25px; border-radius: 20px; box-shadow: 0 10px 30px rgba(76, 175, 80, 0.2); position: relative; overflow: hidden; }
        .balance-section::before { content: ''; position: absolute; top: 0; right: 0; width: 100px; height: 100px; background: radial-gradient(circle, rgba(76, 175, 80, 0.1) 0%, transparent 70%); border-radius: 50%; transform: translate(30px, -30px); }
        .member-info { display: flex; align-items: center; margin-bottom: 20px; }
        .member-avatar { width: 50px; height: 50px; background: linear-gradient(135deg, #4CAF50, #66BB6A); border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 24px; margin-right: 15px; color: white; }
        .member-details h3 { font-size: 18px; color: #333; margin-bottom: 3px; }
        .member-id { font-size: 12px; color: #666; background: #e8f5e8; padding: 2px 8px; border-radius: 10px; display: inline-block; }
        .balance-display { text-align: center; margin-bottom: 20px; }
        .balance-label { font-size: 14px; color: #666; margin-bottom: 8px; }
        .balance-amount { font-size: 36px; font-weight: bold; color: #4CAF50; margin-bottom: 5px; }
        .balance-weight { font-size: 14px; color: #666; background: #f0f8f0; padding: 5px 12px; border-radius: 15px; display: inline-block; }
        .action-buttons { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; margin-top: 20px; }
        .action-btn { background: linear-gradient(135deg, #4CAF50, #66BB6A); color: white; border: none; padding: 12px; border-radius: 12px; font-size: 14px; font-weight: 600; cursor: pointer; transition: all 0.3s ease; display: flex; align-items: center; justify-content: center; gap: 8px; }
        .action-btn:hover { transform: translateY(-2px); box-shadow: 0 5px 15px rgba(76, 175, 80, 0.3); }
        .action-btn.secondary { background: linear-gradient(135deg, #FF9800, #F57C00); }
        .menu-section { padding: 0 20px 20px; }
        .section-title { font-size: 18px; font-weight: bold; color: #333; margin: 20px 0 15px; display: flex; align-items: center; gap: 10px; }
        .menu-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 15px; margin-bottom: 20px; }
        .menu-item { background: white; border-radius: 15px; padding: 20px 15px; text-align: center; box-shadow: 0 5px 15px rgba(0,0,0,0.08); cursor: pointer; transition: all 0.3s ease; border: 1px solid #e8f5e8; }
        .menu-item:hover { transform: translateY(-5px); box-shadow: 0 10px 25px rgba(0,0,0,0.15); }
        .menu-icon { width: 50px; height: 50px; margin: 0 auto 12px; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 24px; color: white; }
        .menu-icon.deposit { background: linear-gradient(135deg, #4CAF50, #66BB6A); }
        .menu-icon.withdraw { background: linear-gradient(135deg, #2196F3, #42A5F5); }
        .menu-icon.history { background: linear-gradient(135deg, #FF9800, #FFA726); }
        .menu-icon.catalog { background: linear-gradient(135deg, #9C27B0, #BA68C8); }
        .menu-icon.education { background: linear-gradient(135deg, #F44336, #EF5350); }
        .menu-icon.community { background: linear-gradient(135deg, #795548, #8D6E63); }
        .menu-text { font-size: 12px; color: #333; font-weight: 600; line-height: 1.3; }
        .stats-section { background: white; margin: 0 20px 20px; padding: 20px; border-radius: 15px; box-shadow: 0 5px 15px rgba(0,0,0,0.08); }
        .stats-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 15px; }
        .stat-item { text-align: center; padding: 15px 10px; border-radius: 12px; background: #f8f9fa; }
        .stat-value { font-size: 20px; font-weight: bold; color: #4CAF50; margin-bottom: 5px; }
        .stat-label { font-size: 11px; color: #666; line-height: 1.3; }
        .activity-section { background: white; margin: 0 20px 80px; padding: 20px; border-radius: 15px; box-shadow: 0 5px 15px rgba(0,0,0,0.08); }
        .activity-item { display: flex; align-items: center; padding: 15px 0; border-bottom: 1px solid #f0f0f0; }
        .activity-item:last-child { border-bottom: none; }
        .activity-icon { width: 45px; height: 45px; border-radius: 50%; display: flex; align-items: center; justify-content: center; margin-right: 15px; font-size: 20px; color: white; }
        .activity-icon.deposit { background: linear-gradient(135deg, #4CAF50, #66BB6A); }
        .activity-icon.withdraw { background: linear-gradient(135deg, #2196F3, #42A5F5); }
        .activity-icon.bonus { background: linear-gradient(135deg, #FF9800, #FFA726); }
        .activity-info { flex: 1; }
        .activity-title { font-weight: 600; color: #333; margin-bottom: 3px; font-size: 14px; }
        .activity-date { font-size: 12px; color: #666; }
        .activity-amount { font-weight: bold; font-size: 14px; }
        .activity-amount.positive { color: #4CAF50; }
        .activity-amount.negative { color: #F44336; }
        .bottom-nav { position: fixed; bottom: 0; left: 50%; transform: translateX(-50%); width: 100%; max-width: 414px; background: white; border-top: 1px solid #e0e0e0; display: flex; padding: 10px 0; box-shadow: 0 -5px 15px rgba(0,0,0,0.1); }
        .nav-item { flex: 1; text-align: center; padding: 10px; cursor: pointer; transition: all 0.3s ease; color: #666; }
        .nav-item.active { color: #4CAF50; }
        .nav-icon { font-size: 22px; margin-bottom: 5px; }
        .nav-text { font-size: 10px; font-weight: 600; }
        .floating-btn { position: fixed; bottom: 80px; right: 20px; width: 60px; height: 60px; background: linear-gradient(135deg, #4CAF50, #66BB6A); border-radius: 50%; display: flex; align-items: center; justify-content: center; color: white; font-size: 28px; cursor: pointer; box-shadow: 0 10px 25px rgba(76, 175, 80, 0.4); transition: all 0.3s ease; animation: pulse 2s infinite; z-index: 99; }
        @keyframes pulse { 0% { box-shadow: 0 10px 25px rgba(76, 175, 80, 0.4); } 50% { box-shadow: 0 15px 35px rgba(76, 175, 80, 0.6); } 100% { box-shadow: 0 10px 25px rgba(76, 175, 80, 0.4); } }
        .notification-banner { background: linear-gradient(135deg, #E3F2FD, #BBDEFB); margin: 0 20px 20px; padding: 15px; border-radius: 12px; border-left: 4px solid #2196F3; display: flex; align-items: center; cursor: pointer; }
        .notification-icon { font-size: 24px; margin-right: 12px; color: #2196F3; }
        .notification-text { flex: 1; font-size: 13px; color: #333; }
        .achievement-badge { position: absolute; top: 10px; right: 10px; background: #FF9800; color: white; padding: 5px 10px; border-radius: 12px; font-size: 10px; font-weight: bold; animation: bounce 2s infinite; }
        @keyframes bounce { 0%, 20%, 50%, 80%, 100% { transform: translateY(0); } 40% { transform: translateY(-10px); } 60% { transform: translateY(-5px); } }
        @media (max-width: 375px) { .menu-grid { grid-template-columns: repeat(2, 1fr); } .balance-amount { font-size: 32px; } .stats-grid { grid-template-columns: repeat(2, 1fr); } }
        .modal { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.5); z-index: 1000; backdrop-filter: blur(5px); }
        .modal-content { position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%); background: white; padding: 30px; border-radius: 20px; width: 90%; max-width: 350px; text-align: center; box-shadow: 0 20px 40px rgba(0,0,0,0.3); }
        .modal-icon { font-size: 48px; margin-bottom: 15px; }
        .modal-title { font-size: 20px; font-weight: bold; margin-bottom: 10px; color: #333; }
        .modal-text { font-size: 14px; color: #666; margin-bottom: 20px; line-height: 1.5; white-space: pre-wrap; }
        .modal-btn { background: linear-gradient(135deg, #4CAF50, #66BB6A); color: white; border: none; padding: 12px 30px; border-radius: 25px; font-size: 14px; font-weight: 600; cursor: pointer; transition: all 0.3s ease; }
        .modal-btn:hover { transform: translateY(-2px); box-shadow: 0 5px 15px rgba(76, 175, 80, 0.3); }
    </style>
</head>
<body>
    <div class="app-container">
        <!-- [SELURUH KODE HTML ANDA SAYA BIARKAN DI SINI, SUDAH SANGAT BAGUS] -->
        <div class="header"> <div class="achievement-badge">🏆 ®™ rung's</div> <div class="logo-container"> <div class="logo">♻️</div> <div> <div class="bank-name">BANK SAMPAH ARAS</div> <div class="location">Karangtaruna Dusun Citambal</div> </div> </div> </div>
        <div class="balance-section"> <div class="member-info"> <div class="member-avatar">👤</div> <div class="member-details"> <h3>Ajis Abdul Jabar</h3> <div class="member-id">ID: ARAS-001</div> </div> </div> <div class="balance-display"> <div class="balance-label">Saldo Tabungan Sampah</div> <div class="balance-amount">Rp 347.500</div> <div class="balance-weight">Total: 89.2 kg</div> </div> <div class="action-buttons"> <button class="action-btn" onclick="showDeposit()"> ♻️ Setor Sampah </button> <button class="action-btn secondary" onclick="showWithdraw()"> 💰 Tarik Saldo </button> </div> </div>
        <div class="notification-banner" onclick="showNotification()"> <div class="notification-icon">📢</div> <div class="notification-text"> <strong>Pengumuman:</strong> Jadwal pengambilan sampah Senin & Kamis jam 08:00 WIB </div> </div>
        <div class="menu-section"> <div class="section-title"> 🏠 Layanan Bank Sampah </div> <div class="menu-grid"> <div class="menu-item" onclick="showDeposit()"> <div class="menu-icon deposit">♻️</div> <div class="menu-text">Setor Sampah</div> </div> <div class="menu-item" onclick="showWithdraw()"> <div class="menu-icon withdraw">💰</div> <div class="menu-text">Tarik Saldo</div> </div> <div class="menu-item" onclick="showHistory()"> <div class="menu-icon history">📊</div> <div class="menu-text">Riwayat Transaksi</div> </div> <div class="menu-item" onclick="showCatalog()"> <div class="menu-icon catalog">📋</div> <div class="menu-text">Katalog Sampah</div> </div> <div class="menu-item" onclick="showEducation()"> <div class="menu-icon education">📚</div> <div class="menu-text">Edukasi Lingkungan</div> </div> <div class="menu-item" onclick="showCommunity()"> <div class="menu-icon community">👥</div> <div class="menu-text">Komunitas</div> </div> </div> </div>
        <div class="stats-section"> <div class="section-title">📈 Statistik Bulan Ini</div> <div class="stats-grid"> <div class="stat-item"> <div class="stat-value">23.4</div> <div class="stat-label">kg Sampah Disetor</div> </div> <div class="stat-item"> <div class="stat-value">78.500</div> <div class="stat-label">Rupiah Diperoleh</div> </div> <div class="stat-item"> <div class="stat-value">12</div> <div class="stat-label">Transaksi</div> </div> </div> </div>
        <div class="activity-section"> <div class="section-title">🕒 Aktivitas Terbaru</div> <div class="activity-item"> <div class="activity-icon deposit">♻️</div> <div class="activity-info"> <div class="activity-title">Setor Sampah Plastik</div> <div class="activity-date">Hari ini, 14:30 - 2.5 kg</div> </div> <div class="activity-amount positive">+Rp 12.500</div> </div> <div class="activity-item"> <div class="activity-icon bonus">🎁</div> <div class="activity-info"> <div class="activity-title">Bonus Konsistensi</div> <div class="activity-date">Kemarin, 16:00</div> </div> <div class="activity-amount positive">+Rp 5.000</div> </div> <div class="activity-item"> <div class="activity-icon deposit">♻️</div> <div class="activity-info"> <div class="activity-title">Setor Sampah Kertas</div> <div class="activity-date">2 hari lalu, 09:15 - 4.2 kg</div> </div> <div class="activity-amount positive">+Rp 8.400</div> </div> <div class="activity-item"> <div class="activity-icon withdraw">💰</div> <div class="activity-info"> <div class="activity-title">Penarikan Saldo</div> <div class="activity-date">1 minggu lalu, 11:20</div> </div> <div class="activity-amount negative">-Rp 50.000</div> </div> <div class="activity-item"> <div class="activity-icon deposit">♻️</div> <div class="activity-info"> <div class="activity-title">Setor Sampah Botol</div> <div class="activity-date">1 minggu lalu, 08:45 - 1.8 kg</div> </div> <div class="activity-amount positive">+Rp 9.000</div> </div> </div>
        <div class="floating-btn" onclick="showQuickDeposit()"> ♻️ </div>
        <div class="bottom-nav"> <div class="nav-item active" onclick="showHome()"> <div class="nav-icon">🏠</div> <div class="nav-text">Beranda</div> </div> <div class="nav-item" onclick="showTransactions()"> <div class="nav-icon">📊</div> <div class="nav-text">Transaksi</div> </div> <div class="nav-item" onclick="showScan()"> <div class="nav-icon">📷</div> <div class="nav-text">Scan</div> </div> <div class="nav-item" onclick="showRewards()"> <div class="nav-icon">🎁</div> <div class="nav-text">Reward</div> </div> <div class="nav-item" onclick="showProfile()"> <div class="nav-icon">👤</div> <div class="nav-text">Profil</div> </div> </div>
    </div>
    <div id="modal" class="modal"> <div class="modal-content"> <div class="modal-icon" id="modalIcon">♻️</div> <div class="modal-title" id="modalTitle">Judul Modal</div> <div class="modal-text" id="modalText">Teks modal</div> <button class="modal-btn" onclick="closeModal()">Tutup</button> </div> </div>

    <script>
        // =========================================================
        // JAVASCRIPT LENGKAP DENGAN FUNGSI YANG DIPERBAIKI
        // =========================================================

        const modal = document.getElementById('modal');
        const modalIcon = document.getElementById('modalIcon');
        const modalTitle = document.getElementById('modalTitle');
        const modalText = document.getElementById('modalText');

        // Data Management (Sudah bagus!)
        let currentBalance = 347500;
        let wasteCategories = [
            { name: "Plastik", price: 5000, unit: "kg", icon: "🥤" },
            { name: "Kertas", price: 2000, unit: "kg", icon: "📄" },
            { name: "Botol Kaca", price: 3000, unit: "kg", icon: "🍾" },
            { name: "Kaleng", price: 8000, unit: "kg", icon: "🥫" },
            { name: "Kardus", price: 1500, unit: "kg", icon: "📦" },
            { name: "Besi", price: 12000, unit: "kg", icon: "🔩" }
        ];

        // --- FUNGSI BARU UNTUK MEMBUAT NOTIFIKASI TOAST ---
        function showToast(message) {
            const toast = document.createElement('div');
            toast.textContent = message;
            // Styling untuk toast
            toast.style.position = 'fixed';
            toast.style.bottom = '90px';
            toast.style.left = '50%';
            toast.style.transform = 'translateX(-50%)';
            toast.style.background = 'rgba(0, 0, 0, 0.75)';
            toast.style.color = 'white';
            toast.style.padding = '12px 20px';
            toast.style.borderRadius = '25px';
            toast.style.zIndex = '2000';
            toast.style.fontSize = '14px';
            toast.style.opacity = '0';
            toast.style.transition = 'opacity 0.5s, bottom 0.5s';

            document.body.appendChild(toast);

            // Animasikan masuk
            setTimeout(() => {
                toast.style.opacity = '1';
                toast.style.bottom = '100px';
            }, 10);

            // Animasikan keluar dan hapus
            setTimeout(() => {
                toast.style.opacity = '0';
                toast.style.bottom = '90px';
                setTimeout(() => {
                    document.body.removeChild(toast);
                }, 500); // Tunggu animasi selesai sebelum dihapus
            }, 3000); // Notifikasi akan hilang setelah 3 detik
        }

        // --- FUNGSI MODAL (Pop-up) ---
        function showModal(icon, title, text) {
            modalIcon.textContent = icon;
            modalTitle.textContent = title;
            modalText.textContent = text;
            modal.style.display = 'flex';
        }

        function closeModal() {
            modal.style.display = 'none';
        }

        // --- FUNGSI NAVIGASI BAWAH (Sekarang berfungsi) ---
        function showHome() {
            setActiveNav(0);
            showToast('Anda sudah di Beranda');
        }

        function showTransactions() {
            setActiveNav(1);
            showModal('📊', 'Riwayat Transaksi', 'Halaman ini akan menampilkan semua riwayat transaksi setor dan tarik saldo Anda.');
        }

        function showScan() {
            setActiveNav(2);
            showModal('📷', 'Scan QR Code', 'Fitur ini akan membuka kamera untuk memindai QR Code sampah atau ID nasabah.');
        }

        function showRewards() {
            setActiveNav(3);
            showModal('🎁', 'Program Reward', 'Kumpulkan poin dari setiap setoran untuk ditukarkan dengan hadiah menarik!');
        }

        function showProfile() {
            setActiveNav(4);
            showModal('👤', 'Profil Saya', 'Di sini Anda dapat melihat dan mengubah data diri, serta mengatur rekening bank.');
        }

        function setActiveNav(index) {
            const navItems = document.querySelectorAll('.nav-item');
            navItems.forEach((item, i) => {
                item.classList.toggle('active', i === index);
            });
        }

        // --- FUNGSI FITUR UTAMA (Kode Anda yang sudah bagus) ---
        function showDeposit() {
            showModal(
                '♻️',
                'Setor Sampah',
                'Fitur untuk menyetor sampah ke Bank Sampah ARAS.\n\nPastikan sampah sudah dipilah sesuai kategori:\n• Plastik: Rp 5.000/kg\n• Kertas: Rp 2.000/kg\n• Botol: Rp 3.000/kg\n• Kaleng: Rp 8.000/kg\n\nJadwal penyetoran: Senin & Kamis jam 08:00-16:00'
            );
        }

        function showWithdraw() {
            showModal(
                '💰',
                'Tarik Saldo',
                `Saldo tersedia: Rp ${currentBalance.toLocaleString('id-ID')}\n\nMinimal penarikan: Rp 25.000\nBiaya admin: Rp 2.500\n\nSaldo dapat ditarik tunai atau transfer ke rekening bank yang terdaftar.`
            );
        }

        function showHistory() {
            showModal(
                '📊',
                'Riwayat Transaksi',
                'Melihat semua transaksi penyetoran dan penarikan sampah.\n\nData mencakup:\n• Tanggal dan waktu\n• Jenis sampah\n• Berat sampah\n• Nilai rupiah\n• Status transaksi\n\nData tersimpan hingga 2 tahun terakhir.'
            );
        }

        function showCatalog() {
            let catalogText = 'Daftar Harga Sampah Bank Sampah ARAS:\n\n';
            wasteCategories.forEach(category => {
                catalogText += `${category.icon} ${category.name}: Rp ${category.price.toLocaleString('id-ID')}/${category.unit}\n`;
            });
            catalogText += '\n*Harga dapat berubah sewaktu-waktu\n**Sampah harus dalam kondisi bersih';
            
            showModal('📋', 'Katalog Harga Sampah', catalogText);
        }

        function showEducation() {
            showModal(
                '📚',
                'Edukasi Lingkungan',
                'Program edukasi Bank Sampah ARAS:\n\n🌱 Workshop Pengolahan Sampah\n🌱 Pelatihan Kompos Organik\n🌱 Sosialisasi 3R (Reduce, Reuse, Recycle)\n🌱 Kampanye Lingkungan Bersih\n🌱 Kelas Daur Ulang Kreatif\n\nJadwal: Setiap Sabtu jam 14:00-16:00'
            );
        }

        function showCommunity() {
            showModal(
                '👥',
                'Komunitas ARAS',
                'Bergabung dengan komunitas peduli lingkungan:\n\n👨‍👩‍👧‍👦 Member Aktif: 127 keluarga\n🏆 ®™ rung\'s: 23 member\n🌟 Reward Points: Program poin\n📱 Grup WhatsApp: Diskusi & info\n🎉 Event Bulanan: Gotong royong\n\nBersama wujudkan cita-cita.'
            );
        }
        
        // --- FUNGSI TAMBAHAN (Sekarang berfungsi) ---
        function showNotification(){
            showModal(
                '📢',
                'Pengumuman Penting',
                'Jadwal pengambilan sampah untuk minggu ini adalah pada hari Senin & Kamis, mulai pukul 08:00 WIB. Mohon pastikan sampah sudah siap di depan rumah.'
            );
        }

        function showQuickDeposit(){
            showModal(
                '♻️',
                'Setor Sampah Cepat',
                'Fitur ini akan membuka kamera untuk memindai jenis sampah dan secara otomatis mencatat beratnya. Fitur masih dalam pengembangan.'
            );
        }

    </script>
</body>
</html>
