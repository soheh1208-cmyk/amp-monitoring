<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AMP Operation Monitoring V3.1 - Synchronized Engine</title>
    <!-- Web App Manifest -->
    <link rel="manifest" href="manifest.json">
    <meta name="theme-color" content="#0a192f">
    <meta name="description" content="Sistem Monitoring Operasional PT Ardina Mulya Perkasa">
    
    <!-- FontAwesome Icons -->
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet">
    <!-- Supabase JS Client v2 -->
    <script src="https://cdn.jsdelivr.net/npm/@supabase/supabase-js@2"></script>
    <script src="https://unpkg.com/html5-qrcode"></script>

    <style>
        :root {
            --navy-primary: #0a192f;
            --navy-header: #112240;
            --blue-accent: #1e3a8a;
            --gold-accent: #d97706;
            --light-bg: #f3f4f6;
            --white: #ffffff;
            --text-main: #1f2937;
            --text-muted: #6b7280;
            --success: #10b981;
            --danger: #ef4444;
            --warning: #f59e0b;
        }

        * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; }
        body { background-color: var(--light-bg); color: var(--text-main); display: flex; justify-content: center; }

        .app-container {
            width: 100%;
            max-width: 480px;
            background: var(--white);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            box-shadow: 0 0 20px rgba(0,0,0,0.15);
            position: relative;
            padding-bottom: 70px;
        }

        .app-header {
            background: linear-gradient(135deg, var(--navy-primary), var(--blue-accent));
            color: var(--white);
            padding: 14px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            border-bottom: 3px solid var(--gold-accent);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .brand-box { display: flex; align-items: center; gap: 10px; }
        .logo-svg { width: 36px; height: 36px; }
        .brand-text h1 { font-size: 13px; font-weight: 700; color: #fff; }
        .brand-text p { font-size: 8.5px; color: var(--gold-accent); font-weight: 600; text-transform: uppercase; }

        .user-badge {
            background: rgba(255,255,255,0.15);
            padding: 4px 8px;
            border-radius: 12px;
            font-size: 11px;
            color: #fff;
            display: flex;
            align-items: center;
            gap: 5px;
        }

        .sync-badge {
            background: var(--gold-accent);
            color: var(--navy-primary);
            font-weight: bold;
            padding: 3px 8px;
            border-radius: 10px;
            font-size: 10px;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 4px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.2);
        }

        /* TAMPILAN ASLI AUTH LOGIN SCREEN (KEMBALI KE SEMULA) */
        .auth-overlay {
            position: fixed;
            top: 0; left: 0; right: 0; bottom: 0;
            background: rgba(10, 25, 47, 0.95);
            z-index: 9999;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 20px;
        }

        .auth-card-asli {
            background: #ffffff;
            width: 100%;
            max-width: 360px;
            border-radius: 16px;
            padding: 24px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.5);
            text-align: center;
        }

        .screen-panel { display: none; padding: 14px; animation: fadeIn 0.2s ease-in-out; }
        .screen-panel.active { display: block; }

        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }

        .card {
            background: var(--white);
            border-radius: 12px;
            padding: 14px;
            margin-bottom: 14px;
            border: 1px solid #e5e7eb;
            box-shadow: 0 2px 4px rgba(0,0,0,0.03);
        }

        .card-title {
            font-size: 13px;
            font-weight: 700;
            color: var(--navy-primary);
            margin-bottom: 10px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            border-bottom: 2px solid #f3f4f6;
            padding-bottom: 8px;
        }

        .modules-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 10px;
            margin-top: 8px;
        }

        .module-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            background: #f8fafc;
            border: 1px solid #e2e8f0;
            border-radius: 10px;
            padding: 10px 4px;
            cursor: pointer;
            transition: all 0.2s;
            text-align: center;
        }

        .module-item:hover { background: #e2e8f0; transform: translateY(-2px); }
        .module-icon {
            width: 36px;
            height: 36px;
            border-radius: 8px;
            background: var(--navy-primary);
            color: var(--gold-accent);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 15px;
            margin-bottom: 4px;
        }

        .module-label { font-size: 9px; font-weight: 600; color: var(--navy-primary); line-height: 1.2; }

        .camera-box {
            width: 100%;
            height: 190px;
            background: #000;
            border-radius: 12px;
            position: relative;
            overflow: hidden;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 10px;
        }

        #webcam, #photo-preview { width: 100%; height: 100%; object-fit: cover; }
        .camera-overlay {
            position: absolute;
            border: 2px dashed rgba(255,255,255,0.7);
            border-radius: 50%;
            width: 120px;
            height: 150px;
            pointer-events: none;
        }

        .digital-clock-box {
            background: var(--navy-primary);
            color: var(--gold-accent);
            text-align: center;
            padding: 8px;
            border-radius: 8px;
            font-size: 18px;
            font-weight: 800;
            letter-spacing: 2px;
            margin-bottom: 10px;
            border: 1px solid var(--gold-accent);
        }

        .btn {
            width: 100%;
            padding: 9px 12px;
            border: none;
            border-radius: 8px;
            font-weight: 700;
            font-size: 11.5px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 6px;
            margin-bottom: 6px;
            transition: 0.2s;
        }

        .btn-primary { background: var(--navy-primary); color: var(--white); }
        .btn-success { background: var(--success); color: var(--white); }
        .btn-warning { background: var(--gold-accent); color: var(--white); }
        .btn-danger { background: var(--danger); color: var(--white); }
        .btn-outline { background: transparent; border: 1px solid var(--navy-primary); color: var(--navy-primary); }

        .form-group { margin-bottom: 10px; text-align: left; }
        .form-group label { display: block; font-size: 11px; font-weight: 600; margin-bottom: 4px; color: var(--text-main); }
        .form-control { width: 100%; padding: 8px 10px; border: 1px solid #cbd5e1; border-radius: 6px; font-size: 11px; outline: none; }

        .badge { padding: 3px 6px; border-radius: 4px; font-size: 9px; font-weight: bold; color: #fff; }
        .badge-in { background: var(--success); }
        .badge-out { background: var(--danger); }
        .badge-warning { background: var(--warning); color: #000; }

        .log-list { list-style: none; }
        .log-item {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 8px 10px;
            border-bottom: 1px solid #e2e8f0;
            font-size: 10px;
        }
        .log-thumb { width: 38px; height: 38px; border-radius: 6px; object-fit: cover; border: 1px solid #cbd5e1; }

        .bottom-nav {
            position: fixed;
            bottom: 0;
            width: 100%;
            max-width: 480px;
            height: 60px;
            background: var(--navy-primary);
            display: flex;
            justify-content: space-around;
            align-items: center;
            border-top: 2px solid var(--gold-accent);
            z-index: 200;
        }

        .nav-link {
            display: flex;
            flex-direction: column;
            align-items: center;
            color: #94a3b8;
            text-decoration: none;
            font-size: 9.5px;
            cursor: pointer;
        }
        .nav-link i { font-size: 17px; margin-bottom: 2px; }
        .nav-link.active { color: var(--gold-accent); font-weight: bold; }
    </style>
</head>
<body>

<div class="app-container">

    <!-- MODAL AUTH LOGIN SLIDE ASLI SEMULA -->
    <div id="auth-modal-overlay" class="auth-overlay">
        <!-- FORM LOGIN ASLI -->
        <div id="login-box-asli" class="auth-card-asli">
            <svg class="logo-svg" viewBox="0 0 200 200" style="width:60px; height:60px; margin-bottom:6px;">
                <polygon points="100,10 120,70 180,40 140,90 190,130 130,130 140,190 95,145 60,190 65,130 10,130 55,90 20,40 75,70" fill="#1e3a8a" stroke="#ffffff" stroke-width="3"/>
                <rect x="55" y="75" width="90" height="45" rx="8" fill="#00a8ff"/>
                <text x="100" y="107" font-family="Arial" font-weight="900" font-size="30" fill="#ffffff" text-anchor="middle">AMP</text>
            </svg>
            <h2 style="font-size:15px; font-weight:bold; color:var(--navy-primary);">PT ARDINA MULYA PERKASA</h2>
            <p style="font-size:9.5px; color:var(--gold-accent); font-weight:bold; margin-bottom:14px;">AMP Operation Monitoring V3.1</p>

            <div class="form-group">
                <label>ID Karyawan / NIP</label>
                <input type="text" id="login-id" class="form-control" placeholder="Contoh: TAD001, KOR001, AMP001">
            </div>

            <div class="form-group">
                <label>PIN Keamanan (6 Digit)</label>
                <input type="password" id="login-pin" class="form-control" placeholder="Masukkan 6 Digit PIN">
            </div>

            <button class="btn btn-primary" onclick="processLogin()"><i class="fas fa-sign-in-alt"></i> MASUK SYSTEM</button>
            <button class="btn btn-outline" onclick="switchAuthSubView('register')"><i class="fas fa-user-plus"></i> DAFTAR AKUN BARU</button>
            <button class="btn btn-outline" onclick="switchAuthSubView('reset-pin')" style="border:none; color:var(--text-muted); font-size:10px;"><i class="fas fa-key"></i> Lupa / Ganti PIN</button>

            <div style="margin-top:10px; background:#f8fafc; padding:8px; border-radius:8px; font-size:8.5px; color:var(--text-muted); text-align:left;">
                <strong>Akun Uji Coba:</strong><br>
                • <code>AMP001</code> / PIN <code>123456</code> (M. Soheh)<br>
                • <code>KOR001</code> / PIN <code>123456</code> (Korlap)<br>
                • <code>TAD001</code> / PIN <code>123456</code> (TAD)
            </div>
        </div>

        <!-- FORM REGISTER ASLI -->
        <div id="register-box-asli" class="auth-card-asli" style="display:none;">
            <h3 style="font-size:13px; margin-bottom:12px; color:var(--navy-primary);"><i class="fas fa-user-plus"></i> Pendaftaran Karyawan Baru</h3>
            <div class="form-group"><label>Nama Lengkap</label><input type="text" id="reg-name" class="form-control" placeholder="Nama Karyawan"></div>
            <div class="form-group"><label>ID Karyawan Baru (NIP)</label><input type="text" id="reg-id" class="form-control" placeholder="ID (Contoh: TAD002)"></div>
            <div class="form-group">
                <label>Peran / Role</label>
                <select id="reg-role" class="form-control">
                    <option value="TAD">Staf Operasional (TAD)</option>
                    <option value="Korlap">Koordinator Lapangan (Korlap)</option>
                    <option value="HeadOfOp">Head of Operation / Admin</option>
                </select>
            </div>
            <div class="form-group"><label>Penempatan Site</label><input type="text" id="reg-site" class="form-control" placeholder="Contoh: PLN Unit Gambir"></div>
            <div class="form-group"><label>PIN 6 Digit</label><input type="password" id="reg-pin" class="form-control" placeholder="PIN Angka"></div>
            <button class="btn btn-success" onclick="processRegister()"><i class="fas fa-save"></i> SIMPAN AKUN BARU</button>
            <button class="btn btn-outline" onclick="switchAuthSubView('login')"><i class="fas fa-arrow-left"></i> KEMBALI KE LOGIN</button>
        </div>

        <!-- FORM RESET PIN ASLI -->
        <div id="reset-box-asli" class="auth-card-asli" style="display:none;">
            <h3 style="font-size:13px; margin-bottom:12px; color:var(--navy-primary);"><i class="fas fa-key"></i> Reset / Ganti PIN</h3>
            <div class="form-group"><label>ID Karyawan</label><input type="text" id="reset-id" class="form-control" placeholder="ID Karyawan"></div>
            <div class="form-group"><label>PIN Lama (Default: 123456)</label><input type="password" id="reset-old-pin" class="form-control"></div>
            <div class="form-group"><label>PIN Baru 6 Digit</label><input type="password" id="reset-new-pin" class="form-control"></div>
            <button class="btn btn-warning" onclick="processResetPIN()"><i class="fas fa-sync-alt"></i> PERBARUI PIN</button>
            <button class="btn btn-outline" onclick="switchAuthSubView('login')"><i class="fas fa-arrow-left"></i> KEMBALI</button>
        </div>
    </div>

    <!-- MAIN APP WRAPPER -->
    <div id="main-app" style="display:block;">

        <div class="app-header">
            <div class="brand-box">
                <svg class="logo-svg" viewBox="0 0 200 200">
                    <polygon points="100,10 120,70 180,40 140,90 190,130 130,130 140,190 95,145 60,190 65,130 10,130 55,90 20,40 75,70" fill="#1e3a8a" stroke="#ffffff" stroke-width="3"/>
                    <rect x="55" y="75" width="90" height="45" rx="8" fill="#00a8ff"/>
                    <text x="100" y="107" font-family="Arial" font-weight="900" font-size="30" fill="#ffffff" text-anchor="middle">AMP</text>
                </svg>
                <div class="brand-text">
                    <h1>PT. ARDINA MULYA PERKASA</h1>
                    <p>Facility Service Specialist</p>
                </div>
            </div>
            
            <div style="display:flex; align-items:center; gap:6px;">
                <div class="sync-badge" onclick="showModule(13)" title="Buka Pusat Sinkronisasi Supabase">
                    <i class="fas fa-database" id="sync-icon"></i> <span id="sync-badge-text">Sync</span>
                </div>
                <div class="user-badge">
                    <i class="fas fa-user-circle"></i>
                    <span id="header-user-id">AMP001</span>
                    <i class="fas fa-sign-out-alt" onclick="logout()" style="margin-left:6px; cursor:pointer;" title="Keluar"></i>
                </div>
            </div>
        </div>

        <!-- MODUL 1: DASHBOARD (INPUT FILTER & OUTPUT REKAP) -->
        <div id="mod-1" class="screen-panel active">
            <div class="card" style="background: linear-gradient(135deg, #0a192f, #1e3a8a); color: #fff;">
                <div style="display:flex; justify-content:space-between; align-items:center;">
                    <div>
                        <h2 id="dash-user-name" style="font-size:15px;">M. Soheh</h2>
                        <p id="dash-user-role" style="font-size:10px; color:#d97706;">Head of Operation / Admin</p>
                        <p id="dash-user-site" style="font-size:9px; opacity:0.8; margin-top:4px;"><i class="fas fa-building"></i> Site: Pusat / All Sites</p>
                    </div>
                    <i class="fas fa-id-badge fa-3x" style="color:#d97706; opacity:0.5;"></i>
                </div>
            </div>

            <div class="card">
                <div class="card-title"><i class="fas fa-download"></i> Output & Download Rekap Sistem</div>
                <div style="display:grid; grid-template-columns:1fr 1fr; gap:8px;">
                    <button class="btn btn-success" onclick="exportToExcel()"><i class="fas fa-file-excel"></i> Rekap Absensi (.CSV)</button>
                    <button class="btn btn-primary" onclick="exportMCPToCSV()"><i class="fas fa-file-csv"></i> Rekap MCP (.CSV)</button>
                    <button class="btn btn-warning" onclick="exportCutiToCSV()"><i class="fas fa-file-alt"></i> Rekap Izin/Cuti (.CSV)</button>
                    <button class="btn btn-danger" onclick="exportMRToCSV()"><i class="fas fa-file-invoice"></i> Rekap MR (.CSV)</button>
                </div>
            </div>

            <div class="card">
                <div class="card-title"><i class="fas fa-th-large"></i> 13 Modul Terintegrasi</div>
                <div class="modules-grid">
                    <div class="module-item" onclick="showModule(1)"><div class="module-icon"><i class="fas fa-chart-line"></i></div><div class="module-label">Dashboard</div></div>
                    <div class="module-item" onclick="showModule(2)"><div class="module-icon"><i class="fas fa-user"></i></div><div class="module-label">Profil</div></div>
                    <div class="module-item" onclick="showModule(3)"><div class="module-icon"><i class="fas fa-camera"></i></div><div class="module-label">Absensi</div></div>
                    <div class="module-item" onclick="showModule(4)" style="border: 1px solid var(--gold-accent); background: #fef3c7;"><div class="module-icon" style="background:var(--gold-accent); color:#fff;"><i class="fas fa-file-invoice-dollar"></i></div><div class="module-label" style="font-weight:700;">MR (Req)</div></div>
                    <div class="module-item" onclick="showModule(5)"><div class="module-icon"><i class="fas fa-file-signature"></i></div><div class="module-label">Izin & Cuti</div></div>
                    <div class="module-item" onclick="showModule(6)"><div class="module-icon"><i class="fas fa-broom"></i></div><div class="module-label">MCP Cleaning</div></div>
                    <div class="module-item" onclick="showModule(7)"><div class="module-icon"><i class="fas fa-restroom"></i></div><div class="module-label">Cheklis Area</div></div>
                    <div class="module-item" onclick="showModule(8)"><div class="module-icon"><i class="fas fa-hard-hat"></i></div><div class="module-label">High Risk K3</div></div>
                    <div class="module-item" onclick="showModule(9)"><div class="module-icon"><i class="fas fa-users"></i></div><div class="module-label">Data Tim</div></div>
                    <div class="module-item" onclick="showModule(10)"><div class="module-icon"><i class="fas fa-tools"></i></div><div class="module-label">Equipment</div></div>
                    <div class="module-item" onclick="showModule(11)"><div class="module-icon"><i class="fas fa-exclamation-triangle"></i></div><div class="module-label">Outstanding</div></div>
                    <div class="module-item" onclick="showModule(12)"><div class="module-icon"><i class="fas fa-bullhorn"></i></div><div class="module-label">KPI & News</div></div>
                    <div class="module-item" onclick="showModule(13)" style="background:#e0f2fe; border:1px solid #0284c7;"><div class="module-icon" style="background:#0284c7; color:#fff;"><i class="fas fa-database"></i></div><div class="module-label" style="color:#0369a1; font-weight:bold;">Modul Sync</div></div>
                </div>
            </div>
        </div>

        <!-- MODUL 2: PROFIL -->
        <div id="mod-2" class="screen-panel">
            <div class="card">
                <div class="card-title"><i class="fas fa-id-card"></i> Identitas & Digital ID Card</div>
                <div style="text-align:center; padding:10px;">
                    <div style="width:70px; height:70px; border-radius:50%; background:var(--navy-primary); color:var(--gold-accent); display:flex; align-items:center; justify-content:center; font-size:28px; margin:0 auto 10px;">
                        <i class="fas fa-user"></i>
                    </div>
                    <h3 id="prof-name">M. Soheh</h3>
                    <p id="prof-id" style="font-size:11px; color:var(--text-muted);">ID: AMP001</p>
                    <p id="prof-role-tag" style="font-size:10px; color:var(--gold-accent); font-weight:bold; margin-top:2px;">PT ARDINA MULYA PERKASA</p>
                </div>
            </div>

            <div class="card">
                <div class="card-title"><i class="fas fa-key"></i> Input Ganti PIN Keamanan</div>
                <div class="form-group"><label>PIN Lama</label><input type="password" id="prof-old-pin" class="form-control"></div>
                <div class="form-group"><label>PIN Baru 6 Digit</label><input type="password" id="prof-new-pin" class="form-control"></div>
                <button class="btn btn-warning" onclick="changeOwnPIN()"><i class="fas fa-save"></i> UPDATE PIN SAYA</button>
            </div>
        </div>

        <!-- MODUL 3: ABSENSI -->
        <div id="mod-3" class="screen-panel">
            <div class="card">
                <div class="card-title"><i class="fas fa-clock"></i> Absensi Snapshot Real-Time</div>
                <div class="digital-clock-box" id="live-clock">00:00:00 WIB</div>

                <div class="camera-box">
                    <video id="webcam" autoplay playsinline style="display:none;"></video>
                    <img id="photo-preview" src="" style="display:none;" />
                    <div id="camera-placeholder" style="color:#fff; text-align:center;">
                        <i class="fas fa-camera fa-2x" style="margin-bottom:8px; color:var(--gold-accent);"></i>
                        <p style="font-size:10px;">Snapshot Foto Wajah Karyawan</p>
                    </div>
                    <div class="camera-overlay"></div>
                </div>

                <button class="btn btn-outline" onclick="startWebcam()"><i class="fas fa-video"></i> 1. Aktifkan Kamera Live</button>
                <button class="btn btn-primary" onclick="takeSnapshot()"><i class="fas fa-circle"></i> 2. Ambil Snapshot Selfie</button>
                <input type="file" id="file-photo" accept="image/*" capture="user" class="form-control" onchange="loadPhotoFromFile(event)">

                <div style="margin-top:10px;" class="form-group">
                    <button class="btn btn-warning" onclick="getRealtimeGPS()"><i class="fas fa-map-marked-alt"></i> Tarik GPS Real-Time (Google Maps)</button>
                    <input type="text" id="gps-coords" class="form-control" placeholder="Koordinat GPS & Alamat Google Maps..." readonly style="background:#f1f5f9; text-align:center; font-weight:bold;">
                    <div id="gmaps-link-box" style="margin-top:4px; text-align:center;"></div>
                </div>

                <div style="display:flex; gap:8px; margin-top:10px;">
                    <button class="btn btn-success" onclick="saveAttendance('IN')"><i class="fas fa-sign-in-alt"></i> CHECK-IN (IN)</button>
                    <button class="btn btn-danger" onclick="saveAttendance('OUT')"><i class="fas fa-sign-out-alt"></i> CHECK-OUT (OUT)</button>
                </div>
            </div>

            <div class="card">
                <div class="card-title"><i class="fas fa-history"></i> Output Log Absensi Terpusat</div>
                <ul id="attendance-log" class="log-list"></ul>
            </div>
        </div>

        <!-- MODUL 4: REVISI - FITUR MR (MARKET REQUEST) -->
        <div id="mod-4" class="screen-panel">
            <div class="card">
                <div class="card-title" style="color:var(--gold-accent);"><i class="fas fa-file-invoice-dollar"></i> Input MR (Market Request)</div>
                
                <div class="form-group">
                    <label>Nomor Permintaan (Auto-Generated)</label>
                    <input type="text" id="mr-number" class="form-control" style="background:#f1f5f9; font-weight:bold;" readonly>
                </div>

                <div class="form-group">
                    <label>Kategori Kebutuhan Lapangan</label>
                    <select id="mr-category" class="form-control">
                        <option>Pengadaan Alat / Peralatan Operasional</option>
                        <option>Bahan Kebersihan / Konsumabel (Chemical, dll)</option>
                        <option>Personil Tambahan (Extra Mobile Crew)</option>
                        <option>Perbaikan Sarana & Prasaran Site</option>
                        <option>Lain-lain / Mendesak</option>
                    </select>
                </div>

                <div class="form-group">
                    <label>Rincian Kebutuhan</label>
                    <textarea id="mr-details" class="form-control" placeholder="Tulis rincian barang, jumlah, dan alasan kebutuhan secara detail..." style="height:70px;"></textarea>
                </div>

                <div class="form-group">
                    <label>Estimasi Biaya / Jumlah Kebutuhan (Rp)</label>
                    <input type="text" id="mr-cost" class="form-control" placeholder="Contoh: Rp 450.000 atau 5 Pcs">
                </div>

                <div class="form-group">
                    <label>Tingkat Prioritas</label>
                    <select id="mr-priority" class="form-control">
                        <option value="BIASA">Biasa (Bisa Ditunda)</option>
                        <option value="SEGERA">Segera (Dikerjakan Minggu Ini)</option>
                        <option value="DARURAT">Darurat (Butuh Segera Hari Ini!)</option>
                    </select>
                </div>

                <div class="form-group">
                    <label>Lampiran Dokumen / Bukti / Nota (Opsional)</label>
                    <input type="file" id="mr-file" class="form-control" onchange="loadMRFile(event)">
                </div>

                <button class="btn btn-warning" onclick="submitMarketRequest()"><i class="fas fa-paper-plane"></i> KIRIM PERMINTAAN MR</button>
            </div>

            <div class="card">
                <div class="card-title"><i class="fas fa-clipboard-list"></i> Riwayat & Approval MR Lapangan</div>
                <div style="font-size:10px; background:#f8fafc; padding:8px; border-radius:6px; margin-bottom:10px; border-left:3px solid var(--gold-accent);">
                    <strong>Alur Persetujuan (Approval Tracking):</strong><br>
                    Draft $\rightarrow$ Diajukan $\rightarrow$ Diperiksa Korlap $\rightarrow$ Disetujui Admin/Pusat.
                </div>
                <ul id="mr-log-list" class="log-list"></ul>
            </div>
        </div>

        <!-- MODUL 5: IZIN & CUTI -->
        <div id="mod-5" class="screen-panel">
            <div class="card">
                <div class="card-title"><i class="fas fa-file-signature"></i> Input Form Pengajuan Cuti / Izin</div>
                <div class="form-group">
                    <label>Jenis Izin</label>
                    <select id="leave-type" class="form-control">
                        <option>Cuti Tahunan</option>
                        <option>Izin Sakit (Lampirkan Surat Dokter)</option>
                        <option>Izin Keperluan Mendesak</option>
                    </select>
                </div>
                <div class="form-group"><label>Alasan Pengajuan</label><textarea id="leave-reason" class="form-control" placeholder="Uraikan alasan..."></textarea></div>
                <div class="form-group"><label>Upload Dokumen Lampiran (Surat Dokter / Bukti PDF/JPG)</label><input type="file" id="leave-file" class="form-control"></div>
                <button class="btn btn-primary" onclick="submitLeaveRequest()"><i class="fas fa-paper-plane"></i> Kirim Pengajuan</button>
            </div>
            <div class="card">
                <div class="card-title"><i class="fas fa-tasks"></i> Output Status & Tiered Approval Cuti</div>
                <ul id="leave-log-list" class="log-list"></ul>
            </div>
        </div>

        <!-- MODUL 6: MCP CLEANING -->
        <div id="mod-6" class="screen-panel">
            <div class="card">
                <div class="card-title"><i class="fas fa-broom"></i> Input MCP - 5 Basic Cleaning</div>
                <label style="display:block; font-size:11px; margin-bottom:6px;"><input type="checkbox" id="mcp-1"> 1. Sweeping (Sapu Koridor & Ruangan)</label>
                <label style="display:block; font-size:11px; margin-bottom:6px;"><input type="checkbox" id="mcp-2"> 2. Mopping (Pengepelan Disinfektan)</label>
                <label style="display:block; font-size:11px; margin-bottom:6px;"><input type="checkbox" id="mcp-3"> 3. Dry Buffing (Pengkilapan Vinyl/Marmer)</label>
                <label style="display:block; font-size:11px; margin-bottom:6px;"><input type="checkbox" id="mcp-4"> 4. Dusting (Lap Debu Furnitur/Meja)</label>
                <label style="display:block; font-size:11px; margin-bottom:6px;"><input type="checkbox" id="mcp-5"> 5. Glass Cleaning (Pembersihan Kaca)</label>
                <div class="form-group" style="margin-top:8px;"><label>Upload Foto Bukti Hasil Pekerjaan MCP</label><input type="file" class="form-control"></div>
                <button class="btn btn-success" onclick="saveMCPProgress()"><i class="fas fa-save"></i> Submit Work Progress MCP</button>
            </div>
            <div class="card">
                <div class="card-title"><i class="fas fa-chart-pie"></i> Output Laporan MCP Kebersihan Harian</div>
                <ul id="mcp-log-list" class="log-list"></ul>
            </div>
        </div>

        <!-- MODUL 7: CHEKLIS AREA -->
        <div id="mod-7" class="screen-panel">
            <div class="card">
                <div class="card-title"><i class="fas fa-restroom"></i> Input Inspeksi Toilet & Ruangan</div>
                <div class="form-group"><label>Pilih Unit Area</label><select class="form-control"><option>Toilet Utama Lantai 1</option><option>Ruang Kerja VIP</option></select></div>
                <label style="display:block; font-size:11px; margin-bottom:4px;"><input type="checkbox" checked> Closet & Urinal Bebas Kerak/Bau</label>
                <label style="display:block; font-size:11px; margin-bottom:4px;"><input type="checkbox" checked> Wastafel & Cermin Bersih Kering</label>
                <div class="form-group" style="margin-top:6px;"><label>Upload Kondisi Area</label><input type="file" class="form-control"></div>
                <button class="btn btn-primary" onclick="alert('Cheklis inspeksi disubmit!')"><i class="fas fa-check-circle"></i> Submit Inspection</button>
            </div>
        </div>

        <!-- MODUL 8: HIGH RISK K3 -->
        <div id="mod-8" class="screen-panel">
            <div class="card" style="border-left:4px solid var(--danger);">
                <div class="card-title" style="color:var(--danger);"><i class="fas fa-exclamation-triangle"></i> Input Work Permit High Risk K3</div>
                <div class="form-group">
                    <label>Kategori Pekerjaan Berisiko</label>
                    <select class="form-control"><option>Pekerjaan Ketinggian / Gondola</option><option>Listrik Tegangan Tinggi (Substation)</option></select>
                </div>
                <label style="display:block; font-size:11px; margin-bottom:4px;"><input type="checkbox"> Full Body Harness & Lanyard Verified</label>
                <div class="form-group" style="margin-top:6px;"><label>Upload File Sertifikat K3 / APD</label><input type="file" class="form-control"></div>
                <button class="btn btn-danger" onclick="alert('Work Permit K3 terkirim!')"><i class="fas fa-shield-alt"></i> Ajukan High Risk Permit</button>
            </div>
        </div>

        <!-- MODUL 9: DATA TIM -->
        <div id="mod-9" class="screen-panel">
            <div class="card">
                <div class="card-title"><i class="fas fa-users"></i> Input Tambah Personil Tim</div>
                <div class="form-group"><label>Upload Batch Import Data Karyawan (.CSV)</label><input type="file" class="form-control"></div>
                <button class="btn btn-primary" onclick="alert('Import data tim berhasil!')"><i class="fas fa-upload"></i> Import Batch Data</button>
            </div>
            <div class="card">
                <div class="card-title"><i class="fas fa-address-book"></i> Output Direktori Karyawan Terdaftar</div>
                <ul id="user-directory-list" class="log-list"></ul>
            </div>
        </div>

        <!-- MODUL 10: EQUIPMENT -->
        <div id="mod-10" class="screen-panel">
            <div class="card">
                <div class="card-title"><i class="fas fa-tools"></i> Input Laporan Mesin / Equipment</div>
                <div class="form-group"><label>Nama Peralatan / Mesin</label><select class="form-control"><option>Floor Polisher Machine #01</option><option>Ride-on Scrubber #02</option></select></div>
                <div class="form-group"><label>Status Kondisi</label><select class="form-control"><option>Baik / Operasional</option><option>Perlu Maintenance (Rusak)</option></select></div>
                <div class="form-group"><label>Upload Foto Kondisi Mesin</label><input type="file" class="form-control"></div>
                <button class="btn btn-primary" onclick="alert('Laporan kondisi mesin tersimpan!')"><i class="fas fa-save"></i> Submit Log Equipment</button>
            </div>
        </div>

        <!-- MODUL 11: OUTSTANDING -->
        <div id="mod-11" class="screen-panel">
            <div class="card">
                <div class="card-title"><i class="fas fa-exclamation-circle"></i> Input Tiket Komplain Klien / Site</div>
                <div class="form-group"><label>Rincian Temuan / Komplain</label><textarea class="form-control" placeholder="Tuliskan temuan..."></textarea></div>
                <div class="form-group"><label>Upload Foto Bukti Temuan Lapangan</label><input type="file" class="form-control"></div>
                <button class="btn btn-warning" onclick="alert('Tiket komplain dibuat!')"><i class="fas fa-plus-circle"></i> Buat Tiket Komplain</button>
            </div>
        </div>

        <!-- MODUL 12: KPI & BULLETIN -->
        <div id="mod-12" class="screen-panel">
            <div class="card">
                <div class="card-title"><i class="fas fa-bullhorn"></i> Input Pengumuman & KPI Assessment</div>
                <div class="form-group"><label>Judul Pengumuman</label><input type="text" class="form-control" placeholder="Judul..."></div>
                <div class="form-group"><label>Upload File Edaran (.PDF/Gambar)</label><input type="file" class="form-control"></div>
                <button class="btn btn-primary" onclick="alert('Pengumuman dipublikasikan!')"><i class="fas fa-paper-plane"></i> Publish Bulletin</button>
            </div>
        </div>

        <!-- MODUL 13: PUSAT SINKRONISASI SUPABASE -->
        <div id="mod-13" class="screen-panel">
            <div class="card" style="border-top:3px solid var(--gold-accent);">
                <div class="card-title"><i class="fas fa-database" style="color:var(--gold-accent);"></i> Integrasi Database Supabase</div>
                <div class="form-group">
                    <label>Supabase Project URL</label>
                    <input type="text" id="cfg-url" class="form-control" placeholder="https://xyzcompany.supabase.co">
                </div>
                <div class="form-group">
                    <label>Supabase Anon Key (Public Key)</label>
                    <input type="password" id="cfg-key" class="form-control" placeholder="eyJhbGciOiJIUzI1Ni...">
                </div>
                <div style="display:flex; gap:6px;">
                    <button class="btn btn-primary" onclick="saveSupabaseConfig()"><i class="fas fa-save"></i> Simpan Kredensial</button>
                    <button class="btn btn-success" onclick="testSupabaseConnection()"><i class="fas fa-plug"></i> Tes Koneksi</button>
                </div>
            </div>

            <div class="card">
                <div class="card-title"><i class="fas fa-sync"></i> Push Offline Queue ke Supabase</div>
                <p style="font-size:10px; color:var(--text-muted); margin-bottom:8px;">Data absensi, MCP, dan Market Request yang tersimpan di HP dapat didorong sekaligus ke server terpusat.</p>
                <button class="btn btn-warning" onclick="syncAllToSupabase()"><i class="fas fa-cloud-upload-alt"></i> SINKRONKAN SEMUA DATA SEKARANG</button>
            </div>

            <div class="card">
                <div class="card-title"><i class="fas fa-terminal"></i> Log Monitor Sinkronisasi</div>
                <div id="sync-log" style="background:#0f172a; color:#38bdf8; font-family:monospace; font-size:10px; padding:10px; border-radius:8px; height:130px; overflow-y:auto;">
                    <p>[SYSTEM] AMP V3.1 Sync Engine Ready.</p>
                </div>
            </div>
        </div>

        <!-- Bottom Navigation -->
        <div class="bottom-nav">
            <div class="nav-link active" onclick="showModule(1)"><i class="fas fa-home"></i>Dashboard</div>
            <div class="nav-link" onclick="showModule(3)"><i class="fas fa-camera"></i>Absensi</div>
            <div class="nav-link" onclick="showModule(4)"><i class="fas fa-file-invoice-dollar"></i>MR (Req)</div>
            <div class="nav-link" onclick="showModule(2)"><i class="fas fa-user-shield"></i>Profil</div>
        </div>

    </div>

</div>

<script>
    // Digital Clock Engine
    setInterval(() => {
        const now = new Date();
        const clockStr = now.toLocaleTimeString('id-ID', { hour: '2-digit', minute: '2-digit', second: '2-digit' }) + " WIB";
        const clockEl = document.getElementById('live-clock');
        if(clockEl) clockEl.innerText = clockStr;
    }, 1000);

    let USER_DATABASE = JSON.parse(localStorage.getItem('AMP_USER_DATABASE')) || {
        "AMP001": { id: "AMP001", name: "M. Soheh", role: "HeadOfOp", pin: "123456", site: "Pusat / All Sites" },
        "KOR001": { id: "KOR001", name: "Ahmad Korlap", role: "Korlap", pin: "123456", site: "PLN Area Jakarta Central" },
        "TAD001": { id: "TAD001", name: "Budi Santoso", role: "TAD", pin: "123456", site: "PLN Unit Gambir" }
    };

    let CENTRAL_ATTENDANCE_DB = JSON.parse(localStorage.getItem('AMP_CENTRAL_ATTENDANCE')) || [];
    let MCP_LOGS_DB = JSON.parse(localStorage.getItem('AMP_MCP_LOGS')) || [];
    let LEAVE_REQUESTS_DB = JSON.parse(localStorage.getItem('AMP_LEAVE_REQUESTS')) || [];
    let MARKET_REQUESTS_DB = JSON.parse(localStorage.getItem('AMP_MARKET_REQUESTS')) || [];

    let currentUser = null;
    let currentPhotoBase64 = '';
    let currentMRFileBase64 = '';
    let supabaseClient = null;

    // AUTO INIT SUPABASE UPON LOAD
    window.addEventListener('DOMContentLoaded', () => {
        const savedUrl = localStorage.getItem('AMP_SUPABASE_URL');
        const savedKey = localStorage.getItem('AMP_SUPABASE_KEY');
        if (savedUrl) document.getElementById('cfg-url').value = savedUrl;
        if (savedKey) document.getElementById('cfg-key').value = savedKey;

        if (savedUrl && savedKey) {
            initSupabase(savedUrl, savedKey);
        }
    });

    function initSupabase(url, key) {
        try {
            if (window.supabase && typeof window.supabase.createClient === 'function') {
                supabaseClient = window.supabase.createClient(url, key);
                writeLog('✓ Supabase Client Terkoneksi.');
            }
        } catch (e) { writeLog('❌ Init Gagal: ' + e.message); }
    }

    function saveSupabaseConfig() {
        const url = document.getElementById('cfg-url').value.trim();
        const key = document.getElementById('cfg-key').value.trim();
        if (!url || !key) { alert('URL dan Anon Key wajib diisi!'); return; }

        localStorage.setItem('AMP_SUPABASE_URL', url);
        localStorage.setItem('AMP_SUPABASE_KEY', key);
        initSupabase(url, key);
        alert('Kredensial Supabase Berhasil Disimpan!');
    }

    async function testSupabaseConnection() {
        const url = localStorage.getItem('AMP_SUPABASE_URL');
        const key = localStorage.getItem('AMP_SUPABASE_KEY');
        if (!url || !key) { alert('Konfigurasi URL & Anon Key terlebih dahulu!'); return; }

        if (!supabaseClient) initSupabase(url, key);

        writeLog('[CONNECTING] Menguji ke Supabase...');
        try {
            const { data, error } = await supabaseClient.auth.getSession();
            if (error) throw error;
            writeLog('✓ [SUCCESS] Supabase Aktif & Terhubung!');
            alert('Koneksi ke Supabase Berhasil!');
        } catch (err) {
            writeLog('❌ [FAILED] Gagal: ' + err.message);
            alert('Gagal Terhubung: ' + err.message);
        }
    }

    function writeLog(msg) {
        const logBox = document.getElementById('sync-log');
        if (!logBox) return;
        const time = new Date().toLocaleTimeString();
        logBox.innerHTML += `<p>[${time}] ${msg}</p>`;
        logBox.scrollTop = logBox.scrollHeight;
    }

    function switchAuthSubView(view) {
        document.getElementById('login-box-asli').style.display = 'none';
        document.getElementById('register-box-asli').style.display = 'none';
        document.getElementById('reset-box-asli').style.display = 'none';

        if(view === 'login') document.getElementById('login-box-asli').style.display = 'block';
        if(view === 'register') document.getElementById('register-box-asli').style.display = 'block';
        if(view === 'reset-pin') document.getElementById('reset-box-asli').style.display = 'block';
    }

    function processRegister() {
        const name = document.getElementById('reg-name').value.trim();
        const id = document.getElementById('reg-id').value.trim().toUpperCase();
        const role = document.getElementById('reg-role').value;
        const site = document.getElementById('reg-site').value.trim() || 'PLN Unit Central';
        const pin = document.getElementById('reg-pin').value.trim();

        if(!name || !id || !pin) { alert('Lengkapi seluruh form pendaftaran!'); return; }
        if(USER_DATABASE[id]) { alert('ID Karyawan sudah terdaftar!'); return; }

        USER_DATABASE[id] = { id, name, role, pin, site };
        localStorage.setItem('AMP_USER_DATABASE', JSON.stringify(USER_DATABASE));
        alert(`Akun Baru Berhasil Dibuat!\nID: ${id}\nNama: ${name}`);
        switchAuthSubView('login');
    }

    function processResetPIN() {
        const id = document.getElementById('reset-id').value.trim().toUpperCase();
        const oldPin = document.getElementById('reset-old-pin').value.trim();
        const newPin = document.getElementById('reset-new-pin').value.trim();

        if(!id || !oldPin || !newPin) { alert('Lengkapi form reset PIN!'); return; }
        if(!USER_DATABASE[id]) { alert('ID Karyawan tidak terdaftar!'); return; }

        if(USER_DATABASE[id].pin === oldPin || oldPin === '123456') {
            USER_DATABASE[id].pin = newPin;
            localStorage.setItem('AMP_USER_DATABASE', JSON.stringify(USER_DATABASE));
            alert(`PIN Akun ${id} Berhasil Diperbarui!`);
            switchAuthSubView('login');
        } else { alert('PIN Lama Salah!'); }
    }

    function changeOwnPIN() {
        const oldPin = document.getElementById('prof-old-pin').value.trim();
        const newPin = document.getElementById('prof-new-pin').value.trim();
        if(!oldPin || !newPin) { alert('Isi PIN Lama dan PIN Baru!'); return; }

        if(currentUser.pin === oldPin) {
            USER_DATABASE[currentUser.id].pin = newPin;
            currentUser.pin = newPin;
            localStorage.setItem('AMP_USER_DATABASE', JSON.stringify(USER_DATABASE));
            alert('PIN Anda berhasil diperbarui!');
        } else { alert('PIN Lama Salah!'); }
    }

    function generateMRNumber() {
        const now = new Date();
        const year = now.getFullYear();
        const month = String(now.getMonth() + 1).padStart(2, '0');
        const day = String(now.getDate()).padStart(2, '0');
        const random = Math.floor(100 + Math.random() * 900);
        return `MR-${year}${month}${day}-${random}`;
    }

    function processLogin() {
        const idInput = document.getElementById('login-id').value.trim().toUpperCase();
        const pinInput = document.getElementById('login-pin').value.trim();

        if (USER_DATABASE[idInput] && USER_DATABASE[idInput].pin === pinInput) {
            currentUser = USER_DATABASE[idInput];
            document.getElementById('auth-modal-overlay').style.display = 'none';
            
            document.getElementById('header-user-id').innerText = currentUser.id;
            document.getElementById('dash-user-name').innerText = currentUser.name;
            document.getElementById('dash-user-role').innerText = currentUser.role;
            document.getElementById('dash-user-site').innerHTML = `<i class="fas fa-building"></i> Site: ${currentUser.site}`;
            document.getElementById('prof-name').innerText = currentUser.name;
            document.getElementById('prof-id').innerText = `ID: ${currentUser.id}`;

            // Generate MR ID Otomatis
            document.getElementById('mr-number').value = generateMRNumber();

            renderAttendanceLogs();
            renderUserDirectory();
            renderLeaveLogs();
            renderMCPLogs();
            renderMarketRequests();
            alert(`Selamat Datang, ${currentUser.name}!`);
        } else {
            alert('ID Karyawan / PIN Salah!');
        }
    }

    function logout() {
        currentUser = null;
        document.getElementById('auth-modal-overlay').style.display = 'flex';
        switchAuthSubView('login');
    }

    function showModule(modId) {
        document.querySelectorAll('.screen-panel').forEach(p => p.classList.remove('active'));
        document.querySelectorAll('.nav-link').forEach(l => l.classList.remove('active'));
        const target = document.getElementById('mod-' + modId);
        if(target) target.classList.add('active');

        // Nav active highlight
        const navIndex = { 1: 0, 3: 1, 4: 2, 2: 3 };
        if(navIndex[modId] !== undefined) {
            document.querySelectorAll('.bottom-nav .nav-link')[navIndex[modId]].classList.add('active');
        }
    }

    async function startWebcam() {
        const video = document.getElementById('webcam');
        try {
            const stream = await navigator.mediaDevices.getUserMedia({ video: { facingMode: "user" } });
            video.srcObject = stream;
            video.style.display = 'block';
            document.getElementById('camera-placeholder').style.display = 'none';
            document.getElementById('photo-preview').style.display = 'none';
        } catch (err) { alert('Gunakan tombol Upload Foto HP.'); }
    }

    function takeSnapshot() {
        const video = document.getElementById('webcam');
        const img = document.getElementById('photo-preview');
        
        if (video.style.display === 'block' && video.srcObject) {
            const canvas = document.createElement('canvas');
            canvas.width = 320; canvas.height = 240;
            canvas.getContext('2d').drawImage(video, 0, 0, canvas.width, canvas.height);
            currentPhotoBase64 = canvas.toDataURL('image/png');
            img.src = currentPhotoBase64;
            img.style.display = 'block';
            video.style.display = 'none';
            alert('Snapshot selfie berhasil!');
        } else { alert('Aktifkan kamera live terlebih dahulu.'); }
    }

    function loadPhotoFromFile(e) {
        const file = e.target.files[0];
        if (file) {
            const reader = new FileReader();
            reader.onload = function(evt) {
                currentPhotoBase64 = evt.target.result;
                document.getElementById('photo-preview').src = currentPhotoBase64;
                document.getElementById('photo-preview').style.display = 'block';
                document.getElementById('camera-placeholder').style.display = 'none';
            };
            reader.readAsDataURL(file);
        }
    }

    function getRealtimeGPS() {
        const coordsInput = document.getElementById('gps-coords');
        const gmapsLinkBox = document.getElementById('gmaps-link-box');
        coordsInput.value = "Mendeteksi GPS...";

        if ("geolocation" in navigator) {
            navigator.geolocation.getCurrentPosition(
                (pos) => {
                    const lat = pos.coords.latitude.toFixed(6);
                    const lng = pos.coords.longitude.toFixed(6);
                    const gmapsUrl = `https://maps.google.com/?q=${lat},${lng}`;
                    coordsInput.value = `Site ${currentUser.site} | GPS: ${lat}, ${lng}`;
                    gmapsLinkBox.innerHTML = `<a href="${gmapsUrl}" target="_blank" style="color:var(--blue-accent); font-size:10px; font-weight:bold;"><i class="fas fa-external-link-alt"></i> Buka di Google Maps</a>`;
                },
                () => { coordsInput.value = `${currentUser.site} (-6.175392, 106.827153)`; }
            );
        } else { coordsInput.value = `${currentUser.site} (-6.175392, 106.827153)`; }
    }

    async function saveAttendance(type) {
        const gps = document.getElementById('gps-coords').value;
        if(!currentPhotoBase64) { alert('Ambil foto selfie terlebih dahulu!'); return; }
        if(!gps || gps.includes("Mendeteksi")) { alert('Tarik lokasi GPS terlebih dahulu!'); return; }

        const now = new Date();
        const timeStr = now.toLocaleTimeString('id-ID', { hour: '2-digit', minute: '2-digit', second: '2-digit' }) + " WIB";
        const dateStr = now.toLocaleDateString('id-ID', { day: 'numeric', month: 'short', year: 'numeric' });

        const record = {
            user_id: currentUser.id, name: currentUser.name, role: currentUser.role, site: currentUser.site,
            type: type, time: timeStr, date: dateStr, gps: gps, photo: currentPhotoBase64
        };

        CENTRAL_ATTENDANCE_DB.unshift(record);
        localStorage.setItem('AMP_CENTRAL_ATTENDANCE', JSON.stringify(CENTRAL_ATTENDANCE_DB));
        renderAttendanceLogs();

        if (supabaseClient) {
            writeLog(`Mengirim data absensi (${type}) ke Supabase...`);
            try {
                const { error } = await supabaseClient.from('attendance_logs').insert([record]);
                if (error) throw error;
                writeLog(`✓ Absensi ${type} berhasil dikirim ke Supabase server!`);
            } catch (err) {
                writeLog(`⚠ Tersimpan di HP (Offline Queue): ${err.message}`);
            }
        }

        alert(`Absensi ${type === 'IN' ? 'CHECK-IN' : 'CHECK-OUT'} Berhasil Disimpan!`);
    }

    function renderAttendanceLogs() {
        const logList = document.getElementById('attendance-log');
        logList.innerHTML = '';
        const filtered = CENTRAL_ATTENDANCE_DB.filter(l => (currentUser.role === 'HeadOfOp' || currentUser.role === 'Admin') ? true : l.user_id === currentUser.id);

        if(filtered.length === 0) { logList.innerHTML = `<li class="log-item" style="color:var(--text-muted); text-align:center;">Belum ada data absensi.</li>`; return; }

        filtered.forEach(log => {
            const li = document.createElement('li');
            li.className = 'log-item';
            li.innerHTML = `
                <div style="display:flex; align-items:center; gap:8px;">
                    <img src="${log.photo}" class="log-thumb">
                    <div>
                        <strong>${log.name} (${log.user_id})</strong>
                        <p style="color:var(--text-muted); font-size:9.5px;"><i class="fas fa-clock"></i> ${log.date} - ${log.time}</p>
                        <p style="color:var(--navy-primary); font-size:9px;"><i class="fas fa-map-marker-alt"></i> ${(log.gps||'').substring(0, 28)}...</p>
                    </div>
                </div>
                <span class="badge ${log.type === 'IN' ? 'badge-in' : 'badge-out'}">${log.type === 'IN' ? 'CHECK-IN' : 'CHECK-OUT'}</span>
            `;
            logList.appendChild(li);
        });
    }

    // MODUL 4: REVISI - FITUR MR (MARKET REQUEST)
    function loadMRFile(e) {
        const file = e.target.files[0];
        if (file) {
            const reader = new FileReader();
            reader.onload = function(evt) {
                currentMRFileBase64 = evt.target.result;
            };
            reader.readAsDataURL(file);
        }
    }

    async function submitMarketRequest() {
        const mrNo = document.getElementById('mr-number').value;
        const category = document.getElementById('mr-category').value;
        const details = document.getElementById('mr-details').value.trim();
        const cost = document.getElementById('mr-cost').value.trim();
        const priority = document.getElementById('mr-priority').value;

        if(!details || !cost) { alert('Rincian Kebutuhan & Estimasi Biaya/Jumlah wajib diisi!'); return; }

        const now = new Date();
        const timeStr = now.toLocaleTimeString('id-ID');
        const dateStr = now.toLocaleDateString('id-ID', { day: 'numeric', month: 'short', year: 'numeric' });

        const record = {
            mr_id: mrNo, user_id: currentUser.id, name: currentUser.name, site: currentUser.site,
            category: category, details: details, cost: cost, priority: priority, date: dateStr, time: timeStr,
            approval_korlap: "Diajukan", approval_pusat: "Pending Review", file: currentMRFileBase64 || null
        };

        MARKET_REQUESTS_DB.unshift(record);
        localStorage.setItem('AMP_MARKET_REQUESTS', JSON.stringify(MARKET_REQUESTS_DB));
        renderMarketRequests();

        // push offline queue to supabase
        if(supabaseClient) {
            writeLog(`Mengirim MR (${mrNo}) ke Supabase...`);
            try {
                const { error } = await supabaseClient.from('market_requests').insert([record]);
                if (error) throw error;
                writeLog(`✓ MR ${mrNo} berhasil masuk ke server terpusat.`);
            } catch (err) { writeLog(`⚠ Tersimpan di HP (Offline Queue): ${err.message}`); }
        }

        alert(`Market Request ${mrNo} Berhasil Dikirim!`);
        document.getElementById('mr-details').value = '';
        document.getElementById('mr-cost').value = '';
        document.getElementById('mr-file').value = '';
        document.getElementById('mr-number').value = generateMRNumber(); // reset number
    }

    function approveMR(id, roleApprove) {
        MARKET_REQUESTS_DB.forEach(mr => {
            if(mr.mr_id === id) {
                if(roleApprove === 'Korlap') mr.approval_korlap = 'Disetujui Korlap';
                if(roleApprove === 'Pusat') {
                    mr.approval_korlap = 'Selesai';
                    mr.approval_pusat = 'Verified & Approved';
                }
            }
        });
        localStorage.setItem('AMP_MARKET_REQUESTS', JSON.stringify(MARKET_REQUESTS_DB));
        renderMarketRequests();
        alert('Status MR berhasil diperbarui!');
    }

    function renderMarketRequests() {
        const list = document.getElementById('mr-log-list');
        if(!list) return;
        list.innerHTML = '';

        const filtered = MARKET_REQUESTS_DB.filter(r => {
            if(currentUser.role === 'HeadOfOp' || currentUser.role === 'Admin') return true;
            if(currentUser.role === 'Korlap') return true;
            return r.user_id === currentUser.id;
        });

        if(filtered.length === 0) { list.innerHTML = `<li class="log-item" style="color:var(--text-muted); text-align:center;">Belum ada pengajuan MR.</li>`; return; }

        filtered.forEach(r => {
            const li = document.createElement('li');
            li.className = 'log-item';
            li.style.flexDirection = 'column';
            li.style.alignItems = 'flex-start';
            li.style.gap = '6px';
            li.style.borderBottom = '2px solid #cbd5e1';
            li.style.padding = '10px';

            let actionBtn = '';
            if(currentUser.role === 'Korlap' && r.approval_korlap === 'Diajukan') {
                actionBtn = `<button class="btn btn-warning" style="padding: 2px 6px; font-size: 8px; margin-top:4px;" onclick="approveMR('${r.mr_id}', 'Korlap')">✔ Setujui (Korlap)</button>`;
            } else if(currentUser.role === 'HeadOfOp' && r.approval_pusat === 'Pending Review') {
                actionBtn = `<button class="btn btn-success" style="padding: 2px 6px; font-size: 8px; margin-top:4px;" onclick="approveMR('${r.mr_id}', 'Pusat')">👑 Approve & Cairkan (Admin)</button>`;
            }

            li.innerHTML = `
                <div style="display:flex; justify-content:space-between; width:100%; border-bottom:1px dashed #cbd5e1; padding-bottom:4px;">
                    <span style="font-weight:bold; color:var(--navy-primary);">${r.mr_id}</span>
                    <span class="badge ${r.priority === 'DARURAT' ? 'badge-out' : 'badge-warning'}">${r.priority}</span>
                </div>
                <div style="font-size:9.5px; color:var(--text-main);">
                    <strong>Pengaju:</strong> ${r.name} (${r.user_id}) | Site ${r.site}<br>
                    <strong>Kategori:</strong> ${r.category}<br>
                    <strong>Kebutuhan:</strong> ${r.details}<br>
                    <strong>Estimasi:</strong> <span style="color:var(--gold-accent); font-weight:bold;">${r.cost}</span>
                </div>
                <div style="display:flex; justify-content:space-between; width:100%; align-items:center; font-size:8.5px; margin-top:4px;">
                    <div>K: <span class="badge badge-in" style="font-size:8px;">${r.approval_korlap}</span> P: <span class="badge badge-warning" style="font-size:8px;">${r.approval_pusat}</span></div>
                    <span>${r.date} - ${r.time}</span>
                </div>
                ${actionBtn}
            `;
            list.appendChild(li);
        });
    }

    /* INPUT & OUTPUT MODUL MCP */
    async function saveMCPProgress() {
        const c1 = document.getElementById('mcp-1').checked;
        const c2 = document.getElementById('mcp-2').checked;
        const c3 = document.getElementById('mcp-3').checked;
        const c4 = document.getElementById('mcp-4').checked;
        const c5 = document.getElementById('mcp-5').checked;

        let total = (c1?1:0) + (c2?1:0) + (c3?1:0) + (c4?1:0) + (c5?1:0);
        let percent = (total / 5) * 100;
        const timeStr = new Date().toLocaleTimeString('id-ID');

        const record = { user_id: currentUser.id, name: currentUser.name, percent: percent, time: timeStr };
        MCP_LOGS_DB.unshift(record);
        localStorage.setItem('AMP_MCP_LOGS', JSON.stringify(MCP_LOGS_DB));
        renderMCPLogs();

        if (supabaseClient) {
            writeLog(`Mengirim data MCP (${percent}%) ke Supabase...`);
            try {
                const { error } = await supabaseClient.from('mcp_logs').insert([record]);
                if (error) throw error;
                writeLog(`✓ MCP Progress terkirim ke Supabase!`);
            } catch (err) {
                writeLog(`⚠ Progress MCP tersimpan offline.`);
            }
        }

        alert(`Progress MCP Kebersihan ${percent}% Berhasil Disubmit!`);
    }

    function renderMCPLogs() {
        const list = document.getElementById('mcp-log-list');
        if(!list) return;
        list.innerHTML = '';
        MCP_LOGS_DB.forEach(log => {
            const li = document.createElement('li');
            li.className = 'log-item';
            li.innerHTML = `<div><strong>${log.name} (${log.user_id||'TAD'})</strong><p style="font-size:9px;">Waktu: ${log.time}</p></div><span class="badge badge-in">${log.percent}% SELESAI</span>`;
            list.appendChild(li);
        });
    }

    /* SINKRONISASI BATCH KE SUPABASE */
    async function syncAllToSupabase() {
        if (!supabaseClient) {
            alert('Supabase belum dikonfigurasi! Buka form di atas.');
            return;
        }

        const icon = document.getElementById('sync-icon');
        if (icon) icon.className = 'fas fa-spinner fa-spin';
        writeLog('[SYNC BATCH] Mendorong antrean data lokal ke Supabase...');

        try {
            if (CENTRAL_ATTENDANCE_DB.length > 0) {
                const { error: err1 } = await supabaseClient.from('attendance_logs').upsert(CENTRAL_ATTENDANCE_DB);
                if (err1) throw err1;
                writeLog(`✓ ${CENTRAL_ATTENDANCE_DB.length} data Absensi berhasil disinkronkan.`);
            }

            if (MCP_LOGS_DB.length > 0) {
                const { error: err2 } = await supabaseClient.from('mcp_logs').upsert(MCP_LOGS_DB);
                if (err2) throw err2;
                writeLog(`✓ ${MCP_LOGS_DB.length} data MCP berhasil disinkronkan.`);
            }

            if (MARKET_REQUESTS_DB.length > 0) {
                const { error: err3 } = await supabaseClient.from('market_requests').upsert(MARKET_REQUESTS_DB);
                if (err3) throw err3;
                writeLog(`✓ ${MARKET_REQUESTS_DB.length} data MR berhasil disinkronkan.`);
            }

            alert('Sinkronisasi Data ke Supabase Berhasil!');
        } catch (err) {
            writeLog(`❌ Sync Gagal: ${err.message}`);
            alert('Gagal Sinkronisasi: ' + err.message);
        } finally {
            if (icon) icon.className = 'fas fa-database';
        }
    }

    /* INPUT & OUTPUT IZIN/CUTI */
    function submitLeaveRequest() {
        const type = document.getElementById('leave-type').value;
        const reason = document.getElementById('leave-reason').value;
        if(!reason) { alert('Isi alasan pengajuan!'); return; }

        LEAVE_REQUESTS_DB.unshift({ id: currentUser.id, name: currentUser.name, type: type, reason: reason, korlapStatus: "PENDING", headStatus: "PENDING" });
        localStorage.setItem('AMP_LEAVE_REQUESTS', JSON.stringify(LEAVE_REQUESTS_DB));
        renderLeaveLogs();
        alert('Pengajuan izin berhasil terkirim!');
    }

    function renderLeaveLogs() {
        const list = document.getElementById('leave-log-list');
        if(!list) return;
        list.innerHTML = '';
        LEAVE_REQUESTS_DB.forEach(item => {
            const li = document.createElement('li');
            li.className = 'log-item';
            li.innerHTML = `<div><strong>${item.name} (${item.type})</strong><p style="font-size:9px; color:var(--text-muted);">${item.reason}</p></div><span class="badge badge-in">SUBMITTED</span>`;
            list.appendChild(li);
        });
    }

    function renderUserDirectory() {
        const dirList = document.getElementById('user-directory-list');
        if(!dirList) return;
        dirList.innerHTML = '';
        Object.keys(USER_DATABASE).forEach(id => {
            const u = USER_DATABASE[id];
            const li = document.createElement('li');
            li.className = 'log-item';
            li.innerHTML = `<div><strong>${u.name} (${u.id})</strong><p style="font-size:9px; color:var(--text-muted);">${u.role} | Site: ${u.site}</p></div><span class="badge badge-in">AKTIF</span>`;
            dirList.appendChild(li);
        });
    }

    /* FITUR DOWNLOAD EXCEL (.CSV) */
    function exportToExcel() {
        let csv = "data:text/csv;charset=utf-8,ID,Nama,Role,Site,Tipe,Tanggal,Waktu,GPS\n";
        CENTRAL_ATTENDANCE_DB.forEach(r => { csv += `${r.user_id||r.id},${r.name},${r.role},${r.site||'PLN'},${r.type},${r.date},${r.time},"${r.gps}"\n`; });
        downloadCSV(csv, `Rekap_Absensi_AMP_${new Date().toISOString().slice(0,10)}.csv`);
    }

    function exportMCPToCSV() {
        let csv = "data:text/csv;charset=utf-8,ID,Nama,Persentase MCP,Waktu\n";
        MCP_LOGS_DB.forEach(r => { csv += `${r.user_id||r.id},${r.name},${r.percent}%,${r.time}\n`; });
        downloadCSV(csv, `Rekap_MCP_Kebersihan_AMP_${new Date().toISOString().slice(0,10)}.csv`);
    }

    function exportCutiToCSV() {
        let csv = "data:text/csv;charset=utf-8,ID,Nama,Jenis Izin,Alasan\n";
        LEAVE_REQUESTS_DB.forEach(r => { csv += `${r.id},${r.name},${r.type},"${r.reason}"\n`; });
        downloadCSV(csv, `Rekap_Izin_Cuti_AMP_${new Date().toISOString().slice(0,10)}.csv`);
    }

    function exportMRToCSV() {
        let csv = "data:text/csv;charset=utf-8,ID MR,Pengaju,Site,Kategori,Prioritas,Rincian,Estimasi,Status Korlap,Status Pusat,Tanggal\n";
        MARKET_REQUESTS_DB.forEach(r => { csv += `${r.mr_id},${r.name},${r.site},${r.category},${r.priority},"${r.details}",${r.cost},${r.approval_korlap},${r.approval_pusat},${r.date}\n`; });
        downloadCSV(csv, `Rekap_Market_Request_AMP_${new Date().toISOString().slice(0,10)}.csv`);
    }

    function downloadCSV(csvData, filename) {
        const link = document.createElement("a");
        link.setAttribute("href", encodeURI(csvData));
        link.setAttribute("download", filename);
        document.body.appendChild(link);
        link.click();
    }
</script>
</body>
</html>
