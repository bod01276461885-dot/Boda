<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ناو كاش - بوده المكسيكي</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet">
    <style>
        :root {
            --primary: #e60000;
            --primary-dark: #b30000;
            --bg: #0f172a;
            --card-bg: rgba(15, 23, 42, 0.75);
            --text: #ffffff;
            --text-sub: #cbd5e1;
            --accent: #22c55e;
            --gold: #f59e0b;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            -webkit-tap-highlight-color: transparent;
        }

        body {
            background-color: var(--bg);
            color: var(--text);
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 10px;
        }

        /* حاوية التطبيق مع الخلفية المدمجة */
        .app-container {
            width: 100%;
            max-width: 430px;
            height: 92vh;
            border-radius: 35px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.8), 0 0 25px rgba(230, 0, 0, 0.3);
            border: 1px solid rgba(255,255,255,0.15);
            display: flex;
            flex-direction: column;
            overflow: hidden;
            position: relative;
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
        }

        /* طبقة تظليل لتوضيح النصوص والكروت فوق الصورة */
        .app-container::before {
            content: '';
            position: absolute;
            top: 0; left: 0; right: 0; bottom: 0;
            background: linear-gradient(180deg, rgba(15, 23, 42, 0.8) 0%, rgba(15, 23, 42, 0.92) 100%);
            z-index: 1;
        }

        .header, .content, .bottom-nav {
            position: relative;
            z-index: 2;
        }

        /* Header */
        .header {
            padding: 15px 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: rgba(15, 23, 42, 0.85);
            backdrop-filter: blur(12px);
            border-bottom: 1px solid rgba(255, 255, 255, 0.05);
        }

        .brand {
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .brand-logo {
            width: 45px;
            height: 45px;
            border-radius: 50%;
            object-fit: cover;
            border: 2px solid var(--primary);
            box-shadow: 0 0 10px rgba(230, 0, 0, 0.5);
        }

        .brand-info {
            display: flex;
            flex-direction: column;
        }

        .brand-name {
            font-size: 18px;
            font-weight: bold;
            line-height: 1.2;
        }

        .brand-name span {
            color: var(--primary);
        }

        .owner-name {
            font-size: 11px;
            color: var(--accent);
            font-weight: 600;
        }

        .bell-btn {
            position: relative;
            cursor: pointer;
            padding: 8px;
        }

        .bell-badge {
            position: absolute;
            top: 5px;
            right: 5px;
            width: 8px;
            height: 8px;
            background-color: var(--primary);
            border-radius: 50%;
        }

        /* Balance Card */
        .balance-card {
            margin: 15px 20px;
            padding: 20px;
            background: linear-gradient(135deg, rgba(230, 0, 0, 0.9), rgba(179, 0, 0, 0.95));
            border-radius: 20px;
            box-shadow: 0 10px 20px rgba(230, 0, 0, 0.3);
            position: relative;
            overflow: hidden;
            cursor: pointer;
            backdrop-filter: blur(5px);
        }

        .balance-title {
            font-size: 14px;
            opacity: 0.9;
        }

        .balance-amount {
            font-size: 32px;
            font-weight: bold;
            margin: 10px 0;
        }

        /* Content Area */
        .content {
            flex: 1;
            overflow-y: auto;
            padding: 0 20px 20px 20px;
            scroll-behavior: smooth;
        }

        .content::-webkit-scrollbar {
            display: none;
        }

        .tab-page {
            display: none;
            animation: fadeIn 0.3s ease-in-out;
        }

        .tab-page.active {
            display: block;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(8px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .section-title {
            font-size: 16px;
            font-weight: 600;
            margin: 20px 0 12px 0;
            display: flex;
            align-items: center;
            justify-content: space-between;
            text-shadow: 0 2px 4px rgba(0,0,0,0.8);
        }

        .view-all-btn {
            color: #ff4d4d;
            cursor: pointer;
            font-size: 13px;
            font-weight: bold;
        }

        /* Services Grid */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 12px;
        }

        .service-item {
            background: var(--card-bg);
            border: 1px solid rgba(255,255,255,0.1);
            border-radius: 16px;
            padding: 12px 5px;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 8px;
            cursor: pointer;
            backdrop-filter: blur(8px);
        }

        .service-icon {
            width: 45px;
            height: 45px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.1);
            display: flex;
            align-items: center;
            justify-content: center;
            color: #ff3333;
            font-size: 18px;
        }

        .service-title {
            font-size: 11px;
            text-align: center;
            color: #ffffff;
            font-weight: bold;
        }

        /* Offers */
        .offers-container {
            display: flex;
            gap: 15px;
            overflow-x: auto;
            padding-bottom: 10px;
        }

        .offer-card {
            min-width: 240px;
            background: var(--card-bg);
            border-radius: 20px;
            border: 1px solid rgba(255,255,255,0.1);
            overflow: hidden;
            backdrop-filter: blur(8px);
            display: flex;
            flex-direction: column;
        }

        .offer-img {
            width: 100%;
            height: 120px;
            object-fit: cover;
        }

        .offer-body {
            padding: 15px;
            display: flex;
            flex-direction: column;
            gap: 8px;
        }

        .offer-badge {
            align-self: flex-start;
            background: rgba(34, 197, 94, 0.2);
            color: var(--accent);
            padding: 4px 8px;
            border-radius: 8px;
            font-size: 10px;
            font-weight: bold;
        }

        .btn-order {
            width: 100%;
            background: linear-gradient(135deg, var(--primary), var(--primary-dark));
            color: white;
            border: none;
            padding: 10px;
            border-radius: 12px;
            font-weight: bold;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
        }

        /* Bottom Nav */
        .bottom-nav {
            height: 65px;
            background: rgba(15, 23, 42, 0.9);
            backdrop-filter: blur(12px);
            border-top: 1px solid rgba(255,255,255,0.1);
            display: flex;
            justify-content: space-around;
            align-items: center;
        }

        .nav-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 4px;
            color: var(--text-sub);
            font-size: 11px;
            cursor: pointer;
            width: 25%;
            padding: 8px 0;
        }

        .nav-item.active {
            color: #ff3333;
        }

        .nav-item i {
            font-size: 18px;
        }
    </style>
</head>
<body>

    <div class="app-container" id="bgContainer">
        <!-- Header -->
        <div class="header">
            <div class="brand">
                <img id="logoImg" src="" alt="بوده المكسيكي" class="brand-logo">
                <div class="brand-info">
                    <div class="brand-name">ناو <span>كاش</span></div>
                    <div class="owner-name"><i class="fa-solid fa-crown"></i> بوده المكسيكي</div>
                </div>
            </div>
            <div class="bell-btn">
                <i class="fa-regular fa-bell" style="font-size: 20px; color: var(--text-sub);"></i>
                <div class="bell-badge"></div>
            </div>
        </div>

        <!-- Content Area -->
        <div class="content">
            <div id="page-home" class="tab-page active">
                <div class="balance-card">
                    <div class="balance-title">محفظة ناو كاش الرقمية <i class="fa-solid fa-circle-info" style="font-size: 12px; float: left;"></i></div>
                    <div class="balance-amount">5,250.00 <small style="font-size: 16px;">ج.م</small></div>
                    <div style="font-size: 12px; opacity: 0.8;">رقم المحفظة: 01276461885</div>
                </div>

                <div class="section-title">
                    <span>خدمات كاش الشاملة</span>
                </div>
                
                <div class="services-grid">
                    <div class="service-item">
                        <div class="service-icon"><i class="fa-solid fa-paper-plane"></i></div>
                        <div class="service-title">تحويل أموال</div>
                    </div>
                    <div class="service-item">
                        <div class="service-icon"><i class="fa-solid fa-money-bill-transfer"></i></div>
                        <div class="service-title">سحب وإيداع</div>
                    </div>
                    <div class="service-item">
                        <div class="service-icon"><i class="fa-solid fa-mobile-screen-button"></i></div>
                        <div class="service-title">شحن رصيد</div>
                    </div>
                    <div class="service-item">
                        <div class="service-icon"><i class="fa-solid fa-file-invoice-dollar"></i></div>
                        <div class="service-title">دفع فواتير</div>
                    </div>
                </div>

                <div class="section-title">
                    <span>عروض وخصومات حصريّة</span>
                </div>
                
                <div class="offers-container">
                    <div class="offer-card">
                        <img src="https://images.unsplash.com/photo-1607604276583-eef5d076aa5f?w=500&auto=format&fit=crop" class="offer-img">
                        <div class="offer-body">
                            <div class="offer-badge">خصم 50%</div>
                            <div style="font-size: 14px; font-weight: bold;">عرض ضعف الرصيد</div>
                            <div style="font-size: 12px; color: var(--text-sub);">احصل على ضعف الشحنة فوراً عند التحويل من ناو كاش.</div>
                            <button class="btn-order">
                                <i class="fa-brands fa-whatsapp"></i> اطلب العرض
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Bottom Navigation -->
        <div class="bottom-nav">
            <div class="nav-item active">
                <i class="fa-solid fa-house"></i>
                <span>الرئيسية</span>
            </div>
            <div class="nav-item">
                <i class="fa-solid fa-tags"></i>
                <span>العروض</span>
            </div>
            <div class="nav-item">
                <i class="fa-solid fa-clock-rotate-left"></i>
                <span>المعاملات</span>
            </div>
            <div class="nav-item">
                <i class="fa-solid fa-user"></i>
                <span>حسابي</span>
            </div>
        </div>
    </div>

    <script>
        // الصورة مرفقة مباشرة داخل الكود لتجنب مشكلة عدم التحميل أو المسارات الخاطئة
        const userImgData = "1000128457_2.png"; 

        // تطبيق الصورة كخلفية وللشعار تلقائياً
        document.getElementById('bgContainer').style.backgroundImage = `url('${userImgData}')`;
        document.getElementById('logoImg').src = userImgData;
    </script>
</body>
</html>
            -webkit-tap-highlight-color: transparent;
        }

        body {
            background-color: var(--bg);
            color: var(--text);
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 10px;
        }

        .app-container {
            width: 100%;
            max-width: 430px;
            height: 92vh;
            background: linear-gradient(180deg, #1e1e2e 0%, #0f172a 100%);
            border-radius: 35px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.6), 0 0 20px rgba(230, 0, 0, 0.2);
            border: 1px solid rgba(255,255,255,0.1);
            display: flex;
            flex-direction: column;
            overflow: hidden;
            position: relative;
        }

        /* Top Header */
        .header {
            padding: 15px 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: rgba(15, 23, 42, 0.8);
            backdrop-filter: blur(10px);
            z-index: 10;
        }

        .brand {
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .brand-logo {
            width: 45px;
            height: 45px;
            border-radius: 50%;
            object-fit: cover;
            border: 2px solid var(--primary);
            box-shadow: 0 0 10px rgba(230, 0, 0, 0.5);
        }

        .brand-info {
            display: flex;
            flex-direction: column;
        }

        .brand-name {
            font-size: 18px;
            font-weight: bold;
            line-height: 1.2;
        }

        .brand-name span {
            color: var(--primary);
        }

        .owner-name {
            font-size: 11px;
            color: var(--accent);
            font-weight: 600;
        }

        .bell-btn {
            position: relative;
            cursor: pointer;
            padding: 8px;
        }

        .bell-badge {
            position: absolute;
            top: 5px;
            right: 5px;
            width: 8px;
            height: 8px;
            background-color: var(--primary);
            border-radius: 50%;
        }

        /* Balance Card */
        .balance-card {
            margin: 15px 20px;
            padding: 20px;
            background: linear-gradient(135deg, rgba(230, 0, 0, 0.9), rgba(179, 0, 0, 0.95));
            border-radius: 20px;
            box-shadow: 0 10px 20px rgba(230, 0, 0, 0.3);
            position: relative;
            overflow: hidden;
            cursor: pointer;
            transition: transform 0.2s;
        }

        .balance-card:active {
            transform: scale(0.98);
        }

        .balance-card::after {
            content: '';
            position: absolute;
            top: -50%;
            right: -50%;
            width: 200px;
            height: 200px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
        }

        .balance-title {
            font-size: 14px;
            opacity: 0.9;
        }

        .balance-amount {
            font-size: 32px;
            font-weight: bold;
            margin: 10px 0;
        }

        /* Content Area */
        .content {
            flex: 1;
            overflow-y: auto;
            padding: 0 20px 20px 20px;
            scroll-behavior: smooth;
        }

        .content::-webkit-scrollbar {
            display: none;
        }

        .tab-page {
            display: none;
            animation: fadeIn 0.3s ease-in-out;
        }

        .tab-page.active {
            display: block;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(8px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .section-title {
            font-size: 16px;
            font-weight: 600;
            margin: 20px 0 12px 0;
            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        .view-all-btn {
            color: var(--primary);
            cursor: pointer;
            font-size: 13px;
            font-weight: bold;
            transition: 0.2s;
        }

        /* Services Grid */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 12px;
        }

        .service-item {
            background: var(--card-bg);
            border: 1px solid rgba(255,255,255,0.05);
            border-radius: 16px;
            padding: 12px 5px;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 8px;
            cursor: pointer;
            transition: all 0.2s;
        }

        .service-item:active {
            transform: scale(0.95);
            background: rgba(230, 0, 0, 0.2);
        }

        .service-icon {
            width: 45px;
            height: 45px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.05);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--primary);
            font-size: 18px;
        }

        .service-title {
            font-size: 11px;
            text-align: center;
            color: var(--text-sub);
        }

        /* Games & Offers Cards */
        .games-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 15px;
        }

        .game-card {
            background: var(--card-bg);
            border-radius: 18px;
            border: 1px solid rgba(255,255,255,0.08);
            overflow: hidden;
            display: flex;
            flex-direction: column;
            box-shadow: 0 5px 15px rgba(0,0,0,0.4);
        }

        .game-img {
            width: 100%;
            height: 110px;
            object-fit: cover;
        }

        .game-body {
            padding: 12px;
            display: flex;
            flex-direction: column;
            gap: 6px;
            flex: 1;
        }

        .game-title { font-size: 14px; font-weight: bold; }
        .game-desc { font-size: 11px; color: var(--text-sub); }

        .btn-game-charge {
            margin-top: auto;
            width: 100%;
            background: linear-gradient(135deg, var(--gold), #d97706);
            color: #000;
            border: none;
            padding: 8px;
            border-radius: 10px;
            font-weight: bold;
            font-size: 12px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 6px;
        }

        .offers-container {
            display: flex;
            gap: 15px;
            overflow-x: auto;
            padding-bottom: 10px;
        }

        .offers-container::-webkit-scrollbar { display: none; }

        .offers-grid {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .offer-card {
            min-width: 240px;
            background: var(--card-bg);
            border-radius: 20px;
            border: 1px solid rgba(255,255,255,0.08);
            overflow: hidden;
            box-shadow: 0 8px 16px rgba(0,0,0,0.3);
            display: flex;
            flex-direction: column;
        }

        .offer-img {
            width: 100%;
            height: 120px;
            object-fit: cover;
        }

        .offer-body {
            padding: 15px;
            display: flex;
            flex-direction: column;
            gap: 8px;
            flex: 1;
        }

        .offer-badge {
            align-self: flex-start;
            background: rgba(34, 197, 94, 0.2);
            color: var(--accent);
            padding: 4px 8px;
            border-radius: 8px;
            font-size: 10px;
            font-weight: bold;
        }

        .offer-title { font-size: 14px; font-weight: bold; }
        .offer-desc { font-size: 12px; color: var(--text-sub); }

        .btn-order {
            margin-top: auto;
            width: 100%;
            background: linear-gradient(135deg, var(--primary), var(--primary-dark));
            color: white;
            border: none;
            padding: 10px;
            border-radius: 12px;
            font-weight: bold;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
        }

        /* Modal Overlay */
        .modal-overlay {
            position: absolute;
            top: 0; left: 0; right: 0; bottom: 0;
            background: rgba(0, 0, 0, 0.8);
            backdrop-filter: blur(5px);
            display: none;
            justify-content: center;
            align-items: center;
            z-index: 100;
            padding: 20px;
        }

        .modal-card {
            background: #1e293b;
            border-radius: 24px;
            width: 100%;
            padding: 20px;
            border: 1px solid rgba(255,255,255,0.1);
            display: flex;
            flex-direction: column;
            gap: 15px;
            animation: fadeIn 0.2s ease-out;
        }

        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 1px solid rgba(255,255,255,0.1);
            padding-bottom: 10px;
        }

        .modal-close {
            cursor: pointer;
            color: var(--text-sub);
            font-size: 18px;
        }

        /* Network Select Grid for Phone Recharge */
        .network-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 10px;
            margin: 10px 0;
        }

        .network-btn {
            background: var(--card-bg);
            border: 1px solid rgba(255,255,255,0.1);
            padding: 10px;
            border-radius: 12px;
            color: white;
            text-align: center;
            cursor: pointer;
            font-size: 12px;
            font-weight: bold;
        }

        .network-btn:hover, .network-btn.active {
            border-color: var(--primary);
            background: rgba(230, 0, 0, 0.2);
        }

        .input-box {
            width: 100%;
            padding: 12px;
            border-radius: 12px;
            border: 1px solid rgba(255,255,255,0.1);
            background: rgba(15, 23, 42, 0.6);
            color: white;
            font-size: 14px;
            outline: none;
        }

        /* Bottom Nav */
        .bottom-nav {
            height: 65px;
            background: rgba(15, 23, 42, 0.95);
            backdrop-filter: blur(10px);
            border-top: 1px solid rgba(255,255,255,0.05);
            display: flex;
            justify-content: space-around;
            align-items: center;
        }

        .nav-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 4px;
            color: var(--text-sub);
            font-size: 11px;
            cursor: pointer;
            transition: 0.2s;
            width: 25%;
            padding: 8px 0;
        }

        .nav-item.active {
            color: var(--primary);
        }

        .nav-item i {
            font-size: 18px;
        }
    </style>
</head>
<body>

    <div class="app-container">
        <!-- Header -->
        <div class="header">
            <div class="brand">
                <img src="1000128457.png" alt="بوده المكسيكي" class="brand-logo">
                <div class="brand-info">
                    <div class="brand-name">ناو <span>كاش</span></div>
                    <div class="owner-name"><i class="fa-solid fa-crown"></i> بوده المكسيكي</div>
                </div>
            </div>
            <!-- زر الإشعارات المشتعل -->
            <div class="bell-btn" onclick="openNotifications()">
                <i class="fa-regular fa-bell" style="font-size: 20px; color: var(--text-sub);"></i>
                <div class="bell-badge"></div>
            </div>
        </div>

        <!-- Content Area -->
        <div class="content">

            <!-- PAGE 1: الرئيسية -->
            <div id="page-home" class="tab-page active">
                <!-- كارت محفظة تفاعلي عند الضغط عليه يظهر تفاصيل الرصيد -->
                <div class="balance-card" onclick="openBalanceDetails()">
                    <div class="balance-title">محفظة ناو كاش الرقمية <i class="fa-solid fa-circle-info" style="font-size: 12px; float: left;"></i></div>
                    <div class="balance-amount">5,250.00 <small style="font-size: 16px;">ج.م</small></div>
                    <div style="font-size: 12px; opacity: 0.8;">رقم المحفظة: 01276461885</div>
                </div>

                <div class="section-title">
                    <span>خدمات كاش الشاملة</span>
                </div>
                
                <!-- شبكة الخدمات المفعلة بالكامل -->
                <div class="services-grid">
                    <div class="service-item" onclick="openServiceModal('تحويل أموال')">
                        <div class="service-icon"><i class="fa-solid fa-paper-plane"></i></div>
                        <div class="service-title">تحويل أموال</div>
                    </div>
                    <div class="service-item" onclick="openServiceModal('سحب وإيداع')">
                        <div class="service-icon"><i class="fa-solid fa-money-bill-transfer"></i></div>
                        <div class="service-title">سحب وإيداع</div>
                    </div>
                    <div class="service-item" onclick="openRechargeModal()">
                        <div class="service-icon"><i class="fa-solid fa-mobile-screen-button"></i></div>
                        <div class="service-title">شحن رصيد</div>
                    </div>
                    <div class="service-item" onclick="openServiceModal('دفع فواتير')">
                        <div class="service-icon"><i class="fa-solid fa-file-invoice-dollar"></i></div>
                        <div class="service-title">دفع فواتير</div>
                    </div>
                    <div class="service-item" onclick="switchTab('games')">
                        <div class="service-icon"><i class="fa-solid fa-gamepad"></i></div>
                        <div class="service-title">شحن ألعاب</div>
                    </div>
                    <div class="service-item" onclick="openServiceModal('كارت دافع أونلاين')">
                        <div class="service-icon"><i class="fa-solid fa-credit-card"></i></div>
                        <div class="service-title">كارت دافع</div>
                    </div>
                    <div class="service-item" onclick="openServiceModal('تجديد باقة')">
                        <div class="service-icon"><i class="fa-solid fa-arrows-rotate"></i></div>
                        <div class="service-title">تجديد باقة</div>
                    </div>
                    <div class="service-item" onclick="openMoreServices()">
                        <div class="service-icon"><i class="fa-solid fa-ellipsis"></i></div>
                        <div class="service-title">المزيد</div>
                    </div>
                </div>

                <div class="section-title">
                    <span>عروض وخصومات حصريّة</span>
                    <!-- زر عرض الكل مفعل -->
                    <small class="view-all-btn" onclick="switchTab('offers')">عرض الكل</small>
                </div>
                
                <div class="offers-container">
                    <div class="offer-card">
                        <img src="https://images.unsplash.com/photo-1607604276583-eef5d076aa5f?w=500&auto=format&fit=crop" class="offer-img">
                        <div class="offer-body">
                            <div class="offer-badge">خصم 50%</div>
                            <div class="offer-title">عرض ضعف الرصيد</div>
                            <div class="offer-desc">احصل على ضعف الشحنة فوراً عند التحويل من ناو كاش.</div>
                            <button class="btn-order" onclick="requestOffer('عرض ضعف الرصيد')">
                                <i class="fa-brands fa-whatsapp"></i> اطلب العرض
                            </button>
                        </div>
                    </div>
                    <div class="offer-card">
                        <img src="https://images.unsplash.com/photo-1556742049-0a67464841c1?w=500&auto=format&fit=crop" class="offer-img">
                        <div class="offer-body">
                            <div class="offer-badge">كاش باك 100%</div>
                            <div class="offer-title">عرض كاش باك الفواتير</div>
                            <div class="offer-desc">سدد فاتورتك واسترجع قيمتها بالكامل في محفظتك.</div>
                            <button class="btn-order" onclick="requestOffer('عرض كاش باك الفواتير')">
                                <i class="fa-brands fa-whatsapp"></i> اطلب العرض
                            </button>
                        </div>
                    </div>
                </div>
            </div>

            <!-- PAGE: شحن ألعاب -->
            <div id="page-games" class="tab-page">
                <div class="section-title">
                    <span>مركز شحن الألعاب الإلكترونية 🎮</span>
                    <small class="view-all-btn" onclick="switchTab('home')">رجوع</small>
                </div>
                <div class="games-grid">
                    <div class="game-card">
                        <img src="https://images.unsplash.com/photo-1542751371-adc38448a05e?w=500&auto=format&fit=crop" class="game-img">
                        <div class="game-body">
                            <div class="game-title">ببجي موبايل</div>
                            <div class="game-desc">شدات UC فورية عن طريق الايدي ID</div>
                            <button class="btn-game-charge" onclick="chargeGame('ببجي موبايل (UC)')">
                                <i class="fa-solid fa-bolt"></i> اشحن الآن
                            </button>
                        </div>
                    </div>
                    <div class="game-card">
                        <img src="https://images.unsplash.com/photo-1511512578047-dfb367046420?w=500&auto=format&fit=crop" class="game-img">
                        <div class="game-body">
                            <div class="game-title">فري فاير</div>
                            <div class="game-desc">مجوهرات Free Fire عبر ID مباشر</div>
                            <button class="btn-game-charge" onclick="chargeGame('فري فاير (جواهر)')">
                                <i class="fa-solid fa-bolt"></i> اشحن الآن
                            </button>
                        </div>
                    </div>
                    <div class="game-card">
                        <img src="https://images.unsplash.com/photo-1579373903781-fd5c0c30c4cd?w=500&auto=format&fit=crop" class="game-img">
                        <div class="game-body">
                            <div class="game-title">كونكر أونلاين</div>
                            <div class="game-desc">سيلك و كروت Conquer أونلاين</div>
                            <button class="btn-game-charge" onclick="chargeGame('كونكر أونلاين (CPS)')">
                                <i class="fa-solid fa-bolt"></i> اشحن الآن
                            </button>
                        </div>
                    </div>
                    <div class="game-card">
                        <img src="https://images.unsplash.com/photo-1538481199705-c710c4e965fc?w=500&auto=format&fit=crop" class="game-img">
                        <div class="game-body">
                            <div class="game-title">ألعاب أخرى</div>
                            <div class="game-desc">كول اوف ديوتي، كلاش، وروبلوكس</div>
                            <button class="btn-game-charge" onclick="chargeGame('العاب أخرى مختلفة')">
                                <i class="fa-solid fa-bolt"></i> طلب شحن
                            </button>
                        </div>
                    </div>
                </div>
            </div>

            <!-- PAGE 2: العروض (عرض الكل) -->
            <div id="page-offers" class="tab-page">
                <div class="section-title">
                    <span>جميع العروض والخصومات 🔥</span>
                    <small class="view-all-btn" onclick="switchTab('home')">الرئيسية</small>
                </div>
                <div class="offers-grid">
                    <div class="offer-card">
                        <img src="https://images.unsplash.com/photo-1607604276583-eef5d076aa5f?w=500&auto=format&fit=crop" class="offer-img">
                        <div class="offer-body">
                            <div class="offer-badge">خصم 50%</div>
                            <div class="offer-title">عرض ضعف الرصيد</div>
                            <div class="offer-desc">احصل على ضعف الشحنة فوراً عند التحويل من ناو كاش.</div>
                            <button class="btn-order" onclick="requestOffer('عرض ضعف الرصيد')">
                                <i class="fa-brands fa-whatsapp"></i> اطلب العرض
                            </button>
                        </div>
                    </div>
                    <div class="offer-card">
                        <img src="https://images.unsplash.com/photo-1556742049-0a67464841c1?w=500&auto=format&fit=crop" class="offer-img">
                        <div class="offer-body">
                            <div class="offer-badge">كاش باك 100%</div>
                            <div class="offer-title">عرض كاش باك الفواتير</div>
                            <div class="offer-desc">سدد فاتورتك واسترجع قيمتها بالكامل في محفظتك.</div>
                            <button class="btn-order" onclick="requestOffer('عرض كاش باك الفواتير')">
                                <i class="fa-brands fa-whatsapp"></i> اطلب العرض
                            </button>
                        </div>
                    </div>
                    <div class="offer-card">
                        <img src="https://images.unsplash.com/photo-1538481199705-c710c4e965fc?w=500&auto=format&fit=crop" class="offer-img">
                        <div class="offer-body">
                            <div class="offer-badge">هدية مجانية</div>
                            <div class="offer-title">عرض شحن الألعاب</div>
                            <div class="offer-desc">اشحن مجوهرات وألعابك المفضلة واحصل على 20% بونص.</div>
                            <button class="btn-order" onclick="requestOffer('عرض شحن الألعاب والشدات')">
                                <i class="fa-brands fa-whatsapp"></i> اطلب العرض
                            </button>
                        </div>
                    </div>
                </div>
            </div>

            <!-- PAGE 3: المعاملات -->
            <div id="page-txns" class="tab-page">
                <div class="section-title">
                    <span>سجل المعاملات الأخير</span>
                </div>
                <div style="display:flex; flex-direction:column; gap:12px;">
                    <div style="background:var(--card-bg); padding:14px; border-radius:16px; display:flex; justify-shadow:space-between; align-items:center;">
                        <div>
                            <div style="font-size:13px; font-weight:bold;">استلام إيداع</div>
                            <div style="font-size:11px; color:var(--text-sub);">اليوم، 03:20 م</div>
                        </div>
                        <div style="color:var(--accent); font-weight:bold;">+500 ج.م</div>
                    </div>
                    <div style="background:var(--card-bg); padding:14px; border-radius:16px; display:flex; justify-content:space-between; align-items:center;">
                        <div>
                            <div style="font-size:13px; font-weight:bold;">شحن شدات ببجي</div>
                            <div style="font-size:11px; color:var(--text-sub);">أمس، 08:45 م</div>
                        </div>
                        <div style="color:var(--primary); font-weight:bold;">-180 ج.م</div>
                    </div>
                </div>
            </div>

            <!-- PAGE 4: حسابي -->
            <div id="page-profile" class="tab-page">
                <div class="section-title"><span>الملف الشخصي</span></div>
                <div style="background:var(--card-bg); border-radius:20px; padding:20px; text-align:center;">
                    <img src="1000128457.png" style="width:80px; height:80px; border-radius:50%; border:3px solid var(--primary);">
                    <h3 style="font-size:16px; margin-top:8px;">بوده المكسيكي</h3>
                    <p style="font-size:12px; color:var(--text-sub);">01276461885</p>
                </div>
            </div>

        </div>

        <!-- Bottom Navigation -->
        <div class="bottom-nav">
            <div class="nav-item active" id="nav-home" onclick="switchTab('home')">
                <i class="fa-solid fa-house"></i>
                <span>الرئيسية</span>
            </div>
            <div class="nav-item" id="nav-offers" onclick="switchTab('offers')">
                <i class="fa-solid fa-tags"></i>
                <span>العروض</span>
            </div>
            <div class="nav-item" id="nav-txns" onclick="switchTab('txns')">
                <i class="fa-solid fa-clock-rotate-left"></i>
                <span>المعاملات</span>
            </div>
            <div class="nav-item" id="nav-profile" onclick="switchTab('profile')">
                <i class="fa-solid fa-user"></i>
                <span>حسابي</span>
            </div>
        </div>
    </div>

    <!-- Modal Box (شاشة تفاعلية انبثاقية) -->
    <div class="modal-overlay" id="customModal">
        <div class="modal-card">
            <div class="modal-header">
                <h4 id="modalTitle" style="font-size: 15px;">تفاصيل الخدمة</h4>
                <i class="fa-solid fa-xmark modal-close" onclick="closeModal()"></i>
            </div>
            <div id="modalBody">
                <!-- يُملأ ديناميكياً بواسطة JavaScript -->
            </div>
        </div>
    </div>

    <script>
        const myPhoneNumber = "201276461885";

        // التنقل بين الأقسام والصفحات
        function switchTab(tabName) {
            const pages = document.querySelectorAll('.tab-page');
            pages.forEach(page => page.classList.remove('active'));

            const navItems = document.querySelectorAll('.nav-item');
            navItems.forEach(item => item.classList.remove('active'));

            document.getElementById(`page-${tabName}`).classList.add('active');

            if(document.getElementById(`nav-${tabName}`)) {
                document.getElementById(`nav-${tabName}`).classList.add('active');
            }
        }

        // إغلاق النافذة المجهزة
        function closeModal() {
            document.getElementById('customModal').style.display = 'none';
        }

        // فتح نافذة تفاصيل الرصيد عند الضغط على كارت المحفظة
        function openBalanceDetails() {
            document.getElementById('modalTitle').innerText = "تفاصيل رصيد المحفظة 💳";
            document.getElementById('modalBody').innerHTML = `
                <div style="display:flex; flex-direction:column; gap:10px; font-size:13px;">
                    <div style="display:flex; justify-between; background:rgba(255,255,255,0.05); padding:10px; border-radius:10px;">
                        <span>الرصيد المتاح:</span>
                        <strong style="color:var(--accent);">5,250.00 ج.م</strong>
                    </div>
                    <div style="display:flex; justify-between; background:rgba(255,255,255,0.05); padding:10px; border-radius:10px;">
                        <span>الكاش باك المكتسب:</span>
                        <strong style="color:var(--gold);">150.00 ج.م</strong>
                    </div>
                    <div style="display:flex; justify-between; background:rgba(255,255,255,0.05); padding:10px; border-radius:10px;">
                        <span>رقم المحفظة:</span>
                        <strong>01276461885</strong>
                    </div>
                    <button class="btn-order" onclick="closeModal()"><i class="fa-solid fa-check"></i> حسناً</button>
                </div>
            `;
            document.getElementById('customModal').style.display = 'flex';
        }

        // فتح نافذة الإشعارات
        function openNotifications() {
            document.getElementById('modalTitle').innerText = "مركز الإشعارات 🔔";
            document.getElementById('modalBody').innerHTML = `
                <div style="display:flex; flex-direction:column; gap:10px; font-size:12px;">
                    <div style="background:rgba(255,255,255,0.05); padding:10px; border-radius:10px;">
                        <strong style="color:var(--accent);">تم خصم الشحنة بنجاح</strong>
                        <p style="color:var(--text-sub); margin-top:4px;">تم شحن شدات ببجي بقيمة 180 ج.م</p>
                    </div>
                    <div style="background:rgba(255,255,255,0.05); padding:10px; border-radius:10px;">
                        <strong style="color:var(--gold);">عرض جديد المكسيكي🔥</strong>
                        <p style="color:var(--text-sub); margin-top:4px;">احصل على ضعف الرصيد الآن لفترة محدودة</p>
                    </div>
                    <button class="btn-order" onclick="closeModal()">إغلاق</button>
                </div>
            `;
            document.getElementById('customModal').style.display = 'flex';
        }

        // فتح نافذة خدمة شحن الرصيد
        function openRechargeModal() {
            document.getElementById('modalTitle').innerText = "شحن رصيد الموبايل 📱";
            document.getElementById('modalBody').innerHTML = `
                <div style="display:flex; flex-direction:column; gap:10px;">
                    <label style="font-size:12px; color:var(--text-sub);">اختر شبكة الهاتف:</label>
                    <div class="network-grid">
                        <div class="network-btn active">فودافون</div>
                        <div class="network-btn">أورنج</div>
                        <div class="network-btn">اتصالات</div>
                        <div class="network-btn">وی (WE)</div>
                    </div>
                    <input type="tel" id="rechargePhone" placeholder="أدخل رقم الموبايل" class="input-box">
                    <input type="number" id="rechargeAmount" placeholder="قيمة الشحن (ج.م)" class="input-box">
                    <button class="btn-order" onclick="confirmRecharge()"><i class="fa-brands fa-whatsapp"></i> تأكيد الشحن عبر الواتساب</button>
                </div>
            `;
            document.getElementById('customModal').style.display = 'flex';
        }

        function confirmRecharge() {
            const phone = document.getElementById('rechargePhone').value;
            const amount = document.getElementById('rechargeAmount').value;
            if(!phone || !amount) {
                alert("يرجى إدخال الرقم والمبلغ أولاً!");
                return;
            }
            const message = `مرحباً بوده المكسيكي 👋🏼، أريد شحن رصيد للرقم: (${phone}) بقيمة: (${amount} ج.م) عبر ناو كاش.`;
            window.open(`https://wa.me/${myPhoneNumber}?text=${encodeURIComponent(message)}`, '_blank');
            closeModal();
        }

        // فتح الخدمات العامة
        function openServiceModal(serviceName) {
            document.getElementById('modalTitle').innerText = `طلب خدمة: ${serviceName}`;
            document.getElementById('modalBody').innerHTML = `
                <div style="display:flex; flex-direction:column; gap:12px;">
                    <p style="font-size:13px; color:var(--text-sub);">أدخل التفاصيل والمبلغ المطلوبة لتأكيد الخدمة عبر الواتساب:</p>
                    <input type="text" id="servDetails" placeholder="أدخل بيانات الخدمة / التفاصيل" class="input-box">
                    <button class="btn-order" onclick="sendServiceReq('${serviceName}')"><i class="fa-brands fa-whatsapp"></i> إرسال الطلب الآن</button>
                </div>
            `;
            document.getElementById('customModal').style.display = 'flex';
        }

        function sendServiceReq(serviceName) {
            const details = document.getElementById('servDetails').value || 'بدون تفاصيل إضافية';
            const message = `مرحباً بوده المكسيكي 👋🏼، أريد تنفيذ خدمة: (${serviceName}) - التفاصيل: (${details}) عبر تطبيق ناو كاش.`;
            window.open(`https://wa.me/${myPhoneNumber}?text=${encodeURIComponent(message)}`, '_blank');
            closeModal();
        }

        // فتح المزيد من الخدمات
        function openMoreServices() {
            document.getElementById('modalTitle').innerText = "المزيد من الخدمات ⚡";
            document.getElementById('modalBody').innerHTML = `
                <div style="display:grid; grid-template-columns:repeat(2, 1fr); gap:10px;">
                    <button class="network-btn" onclick="openServiceModal('تبرعات وجمعيات')">تبرعات كاش</button>
                    <button class="network-btn" onclick="openServiceModal('اشتراك نيتفلكس و شاهد')">اشتراكات ترفيه</button>
                    <button class="network-btn" onclick="openServiceModal('دفع الإنترنت الأرضي')">إنترنت أرضي</button>
                    <button class="network-btn" onclick="openServiceModal('شحن كارت الكهرباء')">كارت الكهرباء</button>
                </div>
            `;
            document.getElementById('customModal').style.display = 'flex';
        }

        // شحن الألعاب
        function chargeGame(gameName) {
            const confirmAction = confirm(`هل تؤكد الانتقال لشحن لعبة (${gameName}) عبر التواصل مع إدارةوده المكسيكي؟`);
            if (confirmAction) {
                const message = `مرحباً بوده المكسيكي 👋🏼، أريد شحن لعبة: (${gameName}) عبر تطبيق ناو كاش. الرجاء إرسال الأسعار والـ ID.`;
                window.open(`https://wa.me/${myPhoneNumber}?text=${encodeURIComponent(message)}`, '_blank');
            }
        }

        // طلب العروض
        function requestOffer(offerName) {
            const confirmAction = confirm(`هل تؤكد طلب (${offerName}) عبر الواتساب مع إدارةوده المكسيكي؟`);
            if (confirmAction) {
                const message = `مرحباً بوده المكسيكي 👋🏼، أريد الاستفسار وطلب ${offerName} من تطبيق ناو كاش.`;
                window.open(`https://wa.me/${myPhoneNumber}?text=${encodeURIComponent(message)}`, '_blank');
            }
        }
    </script>
</body>
</html>
            -webkit-tap-highlight-color: transparent;
        }

        body {
            background-color: var(--bg);
            color: var(--text);
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 10px;
        }

        .app-container {
            width: 100%;
            max-width: 430px;
            height: 92vh;
            background: linear-gradient(180deg, #1e1e2e 0%, #0f172a 100%);
            border-radius: 35px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.6), 0 0 20px rgba(230, 0, 0, 0.2);
            border: 1px solid rgba(255,255,255,0.1);
            display: flex;
            flex-direction: column;
            overflow: hidden;
            position: relative;
        }

        /* Top Header */
        .header {
            padding: 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: rgba(15, 23, 42, 0.8);
            backdrop-filter: blur(10px);
        }

        .brand {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .brand-icon {
            width: 40px;
            height: 40px;
            background: linear-gradient(135deg, var(--primary), #ff4d4d);
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 20px;
            box-shadow: 0 4px 10px rgba(230, 0, 0, 0.4);
        }

        .brand-name {
            font-size: 20px;
            font-weight: bold;
            letter-spacing: 0.5px;
        }

        .brand-name span {
            color: var(--primary);
        }

        /* Balance Card */
        .balance-card {
            margin: 15px 20px;
            padding: 20px;
            background: linear-gradient(135deg, rgba(230, 0, 0, 0.8), rgba(179, 0, 0, 0.9));
            border-radius: 20px;
            box-shadow: 0 10px 20px rgba(230, 0, 0, 0.3);
            position: relative;
            overflow: hidden;
        }

        .balance-card::after {
            content: '';
            position: absolute;
            top: -50%;
            right: -50%;
            width: 200px;
            height: 200px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
        }

        .balance-title {
            font-size: 14px;
            opacity: 0.9;
        }

        .balance-amount {
            font-size: 32px;
            font-weight: bold;
            margin: 10px 0;
        }

        /* Content Area */
        .content {
            flex: 1;
            overflow-y: auto;
            padding: 0 20px 20px 20px;
        }

        .content::-webkit-scrollbar {
            display: none;
        }

        .section-title {
            font-size: 16px;
            font-weight: 600;
            margin: 20px 0 12px 0;
            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        /* Services Grid */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 12px;
        }

        .service-item {
            background: var(--card-bg);
            border: 1px solid rgba(255,255,255,0.05);
            border-radius: 16px;
            padding: 12px 5px;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 8px;
            cursor: pointer;
            transition: all 0.2s;
        }

        .service-item:active {
            transform: scale(0.95);
            background: rgba(230, 0, 0, 0.2);
        }

        .service-icon {
            width: 45px;
            height: 45px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.05);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--primary);
            font-size: 18px;
        }

        .service-title {
            font-size: 11px;
            text-align: center;
            color: var(--text-sub);
        }

        /* Offers Carousel */
        .offers-container {
            display: flex;
            gap: 15px;
            overflow-x: auto;
            padding-bottom: 10px;
        }

        .offers-container::-webkit-scrollbar {
            display: none;
        }

        .offer-card {
            min-width: 240px;
            background: var(--card-bg);
            border-radius: 20px;
            border: 1px solid rgba(255,255,255,0.08);
            overflow: hidden;
            position: relative;
            box-shadow: 0 8px 16px rgba(0,0,0,0.3);
            display: flex;
            flex-direction: column;
        }

        .offer-img {
            width: 100%;
            height: 120px;
            object-fit: cover;
        }

        .offer-body {
            padding: 15px;
            display: flex;
            flex-direction: column;
            gap: 8px;
            flex: 1;
        }

        .offer-badge {
            align-self: flex-start;
            background: rgba(34, 197, 94, 0.2);
            color: var(--accent);
            padding: 4px 8px;
            border-radius: 8px;
            font-size: 10px;
            font-weight: bold;
        }

        .offer-title {
            font-size: 14px;
            font-weight: bold;
        }

        .offer-desc {
            font-size: 12px;
            color: var(--text-sub);
        }

        .btn-order {
            margin-top: auto;
            width: 100%;
            background: linear-gradient(135deg, var(--primary), var(--primary-dark));
            color: white;
            border: none;
            padding: 10px;
            border-radius: 12px;
            font-weight: bold;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
            transition: opacity 0.2s;
        }

        .btn-order:active {
            opacity: 0.8;
        }

        /* Bottom Nav */
        .bottom-nav {
            height: 65px;
            background: rgba(15, 23, 42, 0.95);
            backdrop-filter: blur(10px);
            border-top: 1px solid rgba(255,255,255,0.05);
            display: flex;
            justify-content: space-around;
            align-items: center;
        }

        .nav-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 4px;
            color: var(--text-sub);
            font-size: 11px;
            cursor: pointer;
        }

        .nav-item.active {
            color: var(--primary);
        }

        .nav-item i {
            font-size: 18px;
        }
    </style>
</head>
<body>

    <div class="app-container">
        <!-- Header -->
        <div class="header">
            <div class="brand">
                <div class="brand-icon">
                    <i class="fa-solid fa-bolt"></i>
                </div>
                <div class="brand-name">ناو <span>كاش</span></div>
            </div>
            <i class="fa-regular fa-bell" style="font-size: 20px; color: var(--text-sub);"></i>
        </div>

        <!-- Content Area -->
        <div class="content">
            <!-- Balance Card -->
            <div class="balance-card">
                <div class="balance-title">محفظة ناو كاش الرقمية</div>
                <div class="balance-amount">5,250.00 <small style="font-size: 16px;">ج.م</small></div>
                <div style="font-size: 12px; opacity: 0.8;">رقم المحفظة: 01276461885</div>
            </div>

            <!-- Quick Services -->
            <div class="section-title">
                <span>خدمات كاش الشاملة</span>
            </div>
            <div class="services-grid">
                <div class="service-item" onclick="sendCustomRequest('تحويل أموال')">
                    <div class="service-icon"><i class="fa-solid fa-paper-plane"></i></div>
                    <div class="service-title">تحويل أموال</div>
                </div>
                <div class="service-item" onclick="sendCustomRequest('سحب وإيداع')">
                    <div class="service-icon"><i class="fa-solid fa-money-bill-transfer"></i></div>
                    <div class="service-title">سحب وإيداع</div>
                </div>
                <div class="service-item" onclick="sendCustomRequest('شحن رصيد')">
                    <div class="service-icon"><i class="fa-solid fa-mobile-screen-button"></i></div>
                    <div class="service-title">شحن رصيد</div>
                </div>
                <div class="service-item" onclick="sendCustomRequest('دفع فواتير')">
                    <div class="service-icon"><i class="fa-solid fa-file-invoice-dollar"></i></div>
                    <div class="service-title">دفع فواتير</div>
                </div>
                <div class="service-item" onclick="sendCustomRequest('شحن ألعاب')">
                    <div class="service-icon"><i class="fa-solid fa-gamepad"></i></div>
                    <div class="service-title">شحن ألعاب</div>
                </div>
                <div class="service-item" onclick="sendCustomRequest('كارت أونلاين')">
                    <div class="service-icon"><i class="fa-solid fa-credit-card"></i></div>
                    <div class="service-title">كارت دافع</div>
                </div>
                <div class="service-item" onclick="sendCustomRequest('تجديد الباقة')">
                    <div class="service-icon"><i class="fa-solid fa-arrows-rotate"></i></div>
                    <div class="service-title">تجديد باقة</div>
                </div>
                <div class="service-item" onclick="sendCustomRequest('خدمات أخرى')">
                    <div class="service-icon"><i class="fa-solid fa-ellipsis"></i></div>
                    <div class="service-title">المزيد</div>
                </div>
            </div>

            <!-- Offers Section -->
            <div class="section-title">
                <span>عروض وخصومات حصريّة</span>
                <small style="color: var(--primary);">عرض الكل</small>
            </div>
            
            <div class="offers-container">
                <!-- Offer 1 -->
                <div class="offer-card">
                    <img src="https://images.unsplash.com/photo-1607604276583-eef5d076aa5f?w=500&auto=format&fit=crop" class="offer-img" alt="عرض الشحن">
                    <div class="offer-body">
                        <div class="offer-badge">خصم 50%</div>
                        <div class="offer-title">عرض ضعف الرصيد</div>
                        <div class="offer-desc">احصل على ضعف الشحنة فوراً عند التحويل من ناو كاش.</div>
                        <button class="btn-order" onclick="requestOffer('عرض ضعف الرصيد')">
                            <i class="fa-brands fa-whatsapp"></i> اطلب العروض
                        </button>
                    </div>
                </div>

                <!-- Offer 2 -->
                <div class="offer-card">
                    <img src="https://images.unsplash.com/photo-1556742049-0a67464841c1?w=500&auto=format&fit=crop" class="offer-img" alt="كاش باك">
                    <div class="offer-body">
                        <div class="offer-badge">كاش باك 100%</div>
                        <div class="offer-title">عرض كاش باك الفواتير</div>
                        <div class="offer-desc">سدد فاتورتك واسترجع قيمتها بالكامل في محفظتك.</div>
                        <button class="btn-order" onclick="requestOffer('عرض كاش باك الفواتير')">
                            <i class="fa-brands fa-whatsapp"></i> اطلب العرض
                        </button>
                    </div>
                </div>

                <!-- Offer 3 -->
                <div class="offer-card">
                    <img src="https://images.unsplash.com/photo-1538481199705-c710c4e965fc?w=500&auto=format&fit=crop" class="offer-img" alt="شحن ألعاب">
                    <div class="offer-body">
                        <div class="offer-badge">هدية مجانية</div>
                        <div class="offer-title">عرض شحن الألعاب</div>
                        <div class="offer-desc">اشحن مجوهرات وألعابك المفضلة واحصل على 20% بونص.</div>
                        <button class="btn-order" onclick="requestOffer('عرض شحن الألعاب والشدات')">
                            <i class="fa-brands fa-whatsapp"></i> اطلب العرض
                        </button>
                    </div>
                </div>
            </div>

        </div>

        <!-- Bottom Navigation -->
        <div class="bottom-nav">
            <div class="nav-item active">
                <i class="fa-solid fa-house"></i>
                <span>الرئيسية</span>
            </div>
            <div class="nav-item">
                <i class="fa-solid fa-tags"></i>
                <span>العروض</span>
            </div>
            <div class="nav-item">
                <i class="fa-solid fa-clock-rotate-left"></i>
                <span>المعاملات</span>
            </div>
            <div class="nav-item">
                <i class="fa-solid fa-user"></i>
                <span>حسابي</span>
            </div>
        </div>
    </div>

    <script>
        const myPhoneNumber = "201276461885";

        // وظيفة طلب العروض عبر الواتساب
        function requestOffer(offerName) {
            const message = `مرحباً، أريد الاستفسار وطلب ${offerName} من تطبيق ناو كاش.`;
            const whatsappUrl = `https://wa.me/${myPhoneNumber}?text=${encodeURIComponent(message)}`;
            window.open(whatsappUrl, '_blank');
        }

        // وظيفة طلب الخدمات الأخرى عبر الواتساب
        function sendCustomRequest(serviceName) {
            const message = `مرحباً، أريد الاستفادة من خدمة: (${serviceName}) عبر تطبيق ناو كاش.`;
            const whatsappUrl = `https://wa.me/${myPhoneNumber}?text=${encodeURIComponent(message)}`;
            window.open(whatsappUrl, '_blank');
        }
    </script>
</body>
</html>
