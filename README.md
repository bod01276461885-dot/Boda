<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ناو كاش - Now Cash</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet">
    <style>
        :root {
            --primary: #e60000;
            --primary-dark: #b30000;
            --bg: #0f172a;
            --card-bg: rgba(30, 41, 59, 0.7);
            --text: #ffffff;
            --text-sub: #94a3b8;
            --accent: #22c55e;
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
