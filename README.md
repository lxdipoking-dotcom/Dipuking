<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dipu VIP Cash</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Roboto, sans-serif;
        }

        body {
            background: linear-gradient(135deg, #0a0314, #1a0524, #040108);
            color: #f8fafc;
            min-height: 100vh;
            padding: 15px;
        }

        .container {
            max-width: 650px;
            margin: 0 auto;
            padding-top: 15px;
        }

        .card {
            background: rgba(25, 8, 38, 0.7);
            backdrop-filter: blur(20px);
            border: 1px solid rgba(255, 20, 147, 0.25);
            border-radius: 24px;
            padding: 25px;
            margin-bottom: 25px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.6);
            position: relative;
        }

        /* প্রোফাইল হেডার ব্যানার */
        .user-profile-banner {
            background: linear-gradient(135deg, #ff1493, #420a2b);
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 20px;
            padding: 15px 20px;
            margin-bottom: 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 10px 25px rgba(255, 20, 147, 0.3);
            position: relative;
        }
        .user-info-left h3 { font-size: 18px; color: #fff; font-weight: 700; }
        .user-info-left p { font-size: 13px; color: #ffb6c1; margin-top: 2px; }
        
        .header-controls {
            display: flex;
            align-items: center;
            gap: 10px;
            position: relative;
        }

        /* সেটিংস বাটন */
        .settings-icon-btn {
            background: rgba(255, 255, 255, 0.1);
            color: white;
            border: 1px solid rgba(255, 255, 255, 0.2);
            width: 38px;
            height: 38px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 20px;
            cursor: pointer;
            transition: 0.3s;
            z-index: 101;
        }
        .settings-icon-btn:hover {
            background: #ff1493;
            transform: rotate(45deg);
        }

        /* সেটিংস ড্রপডাউন মেনু */
        .settings-dropdown {
            display: none;
            position: absolute;
            top: 45px;
            right: 0;
            background: #1a0524;
            border: 1px solid #ff1493;
            border-radius: 16px;
            width: 200px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.8);
            z-index: 9999;
            overflow: hidden;
            animation: slideDown 0.2s ease;
        }
        .settings-dropdown button {
            display: block;
            width: 100%;
            padding: 12px 16px;
            color: #ffb6c1;
            font-size: 13px;
            text-align: left;
            background: none;
            border: none;
            cursor: pointer;
            border-bottom: 1px solid rgba(255, 20, 147, 0.1);
            transition: 0.2s;
        }
        .settings-dropdown button:hover {
            background: rgba(255, 20, 147, 0.2);
            color: #fff;
        }
        .settings-dropdown .admin-item {
            color: #00ffff;
            font-weight: bold;
            background: rgba(0, 255, 255, 0.05);
        }
        .settings-dropdown .admin-item:hover {
            background: #00ffff;
            color: #000;
        }
        .settings-dropdown .logout-item {
            color: #ff4d4d;
            font-weight: bold;
        }
        .settings-dropdown .logout-item:hover {
            background: #ff4d4d;
            color: #fff;
        }

        .tg-top-btn {
            background: #0088cc; color: #fff; padding: 8px 14px; border-radius: 12px; font-size: 12px; font-weight: bold; text-decoration: none; box-shadow: 0 4px 10px rgba(0, 136, 204, 0.4); transition: 0.2s;
        }
        .tg-top-btn:hover { background: #00a2f2; }

        /* রানিং নোটিশ বোর্ড */
        .marquee-container {
            background: linear-gradient(90deg, #ff1493, #800080); color: #fff; padding: 8px; border-radius: 12px; margin-bottom: 15px; font-size: 13px; font-weight: 600; display: flex; align-items: center;
        }
        .marquee-label {
            background: #00ffff; color: #000; padding: 2px 8px; border-radius: 6px; margin-right: 10px; font-size: 11px; text-transform: uppercase;
        }

        h2 {
            font-size: 24px; background: linear-gradient(90deg, #ff69b4, #ff1493, #ff76ce); -webkit-background-clip: text; -webkit-text-fill-color: transparent; margin-bottom: 22px; text-align: center; font-weight: 800;
        }

        h4 {
            color: #ffb6c1; margin-bottom: 12px; font-size: 15px; font-weight: 600; border-bottom: 1px dashed rgba(255, 105, 180, 0.3); padding-bottom: 6px;
        }

        .form-group { margin-bottom: 18px; }
        label { display: block; font-size: 12px; color: #ff76ce; margin-bottom: 8px; font-weight: 500; text-transform: uppercase; }
        
        input, select {
            width: 100%; padding: 14px; background: rgba(15, 5, 25, 0.9); border: 1px solid rgba(255, 20, 147, 0.4); border-radius: 14px; color: #fff; font-size: 14px; outline: none;
        }

        .btn {
            width: 100%; padding: 14px; border: none; border-radius: 14px; font-size: 15px; font-weight: 700; cursor: pointer; transition: all 0.3s ease; text-align: center; display: block; text-decoration: none;
        }
        .btn-pink { 
            background: linear-gradient(90deg, #ff1493, #ff69b4); color: white; box-shadow: 0 4px 15px rgba(255, 20, 147, 0.4);
        }
        .btn-pink:hover { transform: translateY(-2px); box-shadow: 0 0 30px rgba(255, 20, 147, 0.7); }

        .btn-skip {
            background: rgba(255, 255, 255, 0.03); border: 1px solid rgba(255, 105, 180, 0.3); color: #ffb6c1; margin-top: 12px;
        }

        .btn-wtd-trigger {
            background: linear-gradient(90deg, #8b0000, #ff1493); color: white; margin-top: 15px;
        }

        .payment-box {
            background: linear-gradient(135deg, #420a2b, #210214); border: 1px solid rgba(255, 20, 147, 0.4); padding: 20px; border-radius: 18px; text-align: center; margin-bottom: 22px;
        }
        .num-box { font-size: 28px; color: #fff; font-weight: 800; text-shadow: 0 0 15px #ff1493; }

        .pending-hold-box {
            background: rgba(234, 179, 8, 0.1); border: 1px dashed #eab308; padding: 18px; border-radius: 16px; text-align: center; margin-top: 15px; color: #fef08a;
        }

        .pending-admin-btn {
            display: inline-block; margin-top: 15px; padding: 10px 20px; background: rgba(6, 182, 212, 0.05); border: 2px solid; border-image: linear-gradient(90deg, #ff1493, #00ffff) 1; color: #ffffff; font-weight: bold; cursor: pointer;
        }

        .status-badge { padding: 4px 8px; border-radius: 6px; font-size: 11px; font-weight: bold; text-align: center; display: inline-block; }
        .status-active { background: rgba(0, 255, 0, 0.15); color: #00ff00; border: 1px solid #00ff00; }
        .status-inactive { background: rgba(255, 0, 0, 0.15); color: #ff4d4d; border: 1px solid #ff4d4d; }

        .sell-offer-box {
            background: linear-gradient(135deg, #2b0c3a, #0b1836); border: 1px solid #ff69b4; padding: 18px; border-radius: 16px; margin-bottom: 20px; color: #e2e8f0; font-size: 13px;
        }
        .sell-offer-box h3 { color: #ff69b4; text-align: center; margin-bottom: 8px; }
        .required-pass-badge {
            background: rgba(255, 20, 147, 0.2); border: 1px solid #ff1493; color: #ffb6c1; padding: 6px 10px; border-radius: 8px; display: block; margin-top: 8px; font-weight: bold; text-align: center;
        }

        .admin-secret-trigger {
            display: block; text-align: center; color: #5a2046; font-size: 12px; margin-top: 35px; cursor: pointer; font-style: italic;
        }
        .admin-secret-trigger:hover { color: #ff1493; }

        /* 👑 অ্যাডমিন কন্ট্রোল মাস্টার ডিজাইন 👑 */
        .admin-header {
            text-align: center; background: linear-gradient(135deg, #a100ff, #ff1493); border-radius: 20px 20px 0 0; padding: 20px; font-weight: bold;
        }
        .admin-header h1 { font-size: 22px; color: #fff; text-shadow: 0 2px 4px rgba(0,0,0,0.4); }
        .admin-header p { font-size: 12px; color: #ffb6c1; margin-top: 4px; font-weight: normal; }

        .admin-box {
            background: #0b0712; border: 2px solid #00ffff; border-radius: 0 0 24px 24px; padding: 15px; box-shadow: 0 0 30px rgba(0, 255, 255, 0.15);
        }

        .admin-menu-list {
            display: flex; flex-direction: column; gap: 12px; margin-top: 5px; margin-bottom: 20px;
        }

        .admin-row {
            display: flex; align-items: center; justify-content: space-between; background: rgba(255,255,255,0.04); padding: 14px 18px; border-radius: 16px; cursor: pointer; border-left: 4px solid #00ffff; transition: all 0.2s ease;
        }
        .admin-row:nth-child(2) { border-left-color: #00ff00; }
        .admin-row:nth-child(3) { border-left-color: #0088cc; }
        .admin-row:nth-child(4) { border-left-color: #ffaa00; }
        .admin-row:nth-child(5) { border-left-color: #a100ff; }
        .admin-row:nth-child(6) { border-left-color: #ff1493; }
        .admin-row:nth-child(7) { border-left-color: #eab308; }
        .admin-row:nth-child(8) { border-left-color: #ff4d4d; }
        .admin-row:nth-child(9) { border-left-color: #3b82f6; }
        .admin-row:nth-child(10) { border-left-color: #10b981; }

        .admin-row:hover { background: rgba(255,255,255,0.08); transform: scale(1.01); }
        .admin-row-left { display: flex; align-items: center; gap: 12px; font-size: 14px; font-weight: 600; color: #f8fafc; }
        .admin-row-left span.icon { font-size: 16px; }

        .badge-count {
            background: #00ffff; color: #000; font-weight: bold; padding: 4px 14px; border-radius: 20px; font-size: 12px; min-width: 35px; text-align: center;
        }
        .badge-pink { background: #ff1493; color: #fff; }
        .badge-green { background: #00ff00; color: #000; }
        .badge-blue { background: #3b82f6; color: #fff; }
        .badge-purple { background: #a100ff; color: #fff; }

        .opt-content { 
            display: none; background: #130a1c; padding: 15px; border-radius: 14px; border: 1px solid rgba(0, 255, 255, 0.2); margin-bottom: 5px; animation: slideDown 0.3s ease;
            overflow-x: auto;
        }

        @keyframes slideDown {
            from { opacity: 0; transform: translateY(-5px); }
            to { opacity: 1; transform: translateY(0); }
        }

        table { width: 100%; border-collapse: collapse; font-size: 12px; margin-top: 5px; min-width: 400px; }
        th, td { padding: 10px 8px; border-bottom: 1px solid rgba(255, 105, 180, 0.1); text-align: left; color: #fff; }
        th { color: #00ffff; background: rgba(0, 255, 255, 0.05); font-weight: 700; }
        
        .btn-action { padding: 5px 10px; font-size: 11px; border: none; border-radius: 6px; cursor: pointer; font-weight: bold; margin-right: 4px; }
        .btn-app { background: linear-gradient(90deg, #00ced1, #00ffff); color: #000; }
        .btn-del { background: #ff4d4d; color: #fff; }
        
        /* নতুন ইয়েস/নো স্পেশাল বাটন স্টাইল */
        .btn-yes { background: #00ff00; color: #000; border-radius: 4px; }
        .btn-no { background: #ff4d4d; color: #fff; border-radius: 4px; }

        .grid-3 { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 8px; margin-bottom: 15px; }
        .wallet-stat { background: rgba(255,255,255,0.03); padding: 14px; border-radius: 14px; text-align: center; border: 1px solid rgba(255,105,180,0.15); }
        
        .btn-logout-blue {
            background: linear-gradient(90deg, #ff4d4d, #ff1493); color: #fff; font-weight: bold; font-size: 15px; padding: 14px; border: none; border-radius: 14px; width: 100%; cursor: pointer; text-align: center; box-shadow: 0 4px 15px rgba(255,20,147,0.3);
        }
        
        .extra-earn-card {
            background: rgba(255, 20, 147, 0.05); border: 1px dashed #ff1493; border-radius: 16px; padding: 15px; margin-top: 15px; text-align: center;
        }

        .income-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; margin-top: 12px; }
        .income-btn {
            background: rgba(255,255,255,0.04); border: 1px solid rgba(0, 255, 255, 0.3); padding: 12px; border-radius: 14px; text-align: center; cursor: pointer;
        }
        .income-btn h5 { color: #00ffff; font-size: 13px; margin-bottom: 4px; }
        .income-btn p { color: #ffb6c1; font-size: 11px; }

        .refer-link-box {
            background: rgba(15, 5, 25, 0.9); border: 1px solid #00ffff; padding: 10px; border-radius: 10px; font-size: 12px; color: #fff; text-align: center; margin-top: 10px; word-break: break-all;
        }

        .admin-form-group { margin-bottom: 12px; text-align: left; }
        .admin-form-group label { color: #00ffff; font-size: 11px; margin-bottom: 5px; display: block; }
        .admin-form-group input { background: #15151e; border: 1px solid rgba(0, 255, 255, 0.3); padding: 10px; font-size: 13px; }
    </style>
</head>
<body>

<div class="container" id="userAppContainer">

    <div class="marquee-container" id="userMarqueeBox" style="display:none;">
        <span class="marquee-label">Notice</span>
        <marquee id="liveNoticeText">Dipu VIP Cash এ আপনাকে স্বাগতম!</marquee>
    </div>

    <div class="user-profile-banner" id="userTopBanner" style="display: none;">
        <div class="user-info-left">
            <h3 id="topBannerName">Dipu King</h3>
            <p id="topBannerPhone">017XXXXXXXX</p>
        </div>
        <div class="header-controls">
            <a href="https://t.me/Dipuking1" id="tgLinkTop" target="_blank" class="tg-top-btn">✈️ Join</a>
            
            <button class="settings-icon-btn" onclick="toggleSettingsMenu(event)">⚙️</button>
            
            <div class="settings-dropdown" id="mySettingsDropdown">
                <button type="button" class="admin-item" onclick="promptAdminPassword()">🔮 Admin Panel</button>
                <button type="button" onclick="alert('👤 প্রোফাইল স্ট্যাটাস: ভেরিফাইড!')">👤 My Profile</button>
                <button type="button" onclick="alert('🔒 সিকিউরিটি লেভেল: হাই-প্রোটেকশন')">🔒 Account Security</button>
                <button type="button" class="logout-item" onclick="triggerUserLogout()">🚪 Log Out</button>
            </div>
        </div>
    </div>

    <div id="step-auth" class="card">
        <h2>💖 অ্যাকাউন্ট তৈরি / লগইন 💖</h2>
        <form onsubmit="event.preventDefault(); handleAuthSubmit();">
            <div class="form-group"><label>আপনার মিষ্টি নাম</label><input type="text" id="userNameInput" placeholder="পুরো নাম লিখুন" required></div>
            <div class="form-group"><label>মোবাইল নাম্বার</label><input type="text" id="userPhone" placeholder="01XXXXXXXXX" required></div>
            <div class="form-group"><label>গোপন পাসওয়ার্ড</label><input type="password" id="userPassInput" placeholder="পাসওয়ার্ড দিন" required></div>
            <div class="form-group"><label>রেফার কোড (ঐচ্ছিক)</label><input type="text" id="userReferInput" placeholder="রেফার করা মোবাইল নাম্বার"></div>
            <button type="submit" class="btn btn-pink">প্রবেশ করুন ✨</button>
        </form>
        <span class="admin-secret-trigger" onclick="promptAdminPassword()">এখানে শুধু এডমিনরা ঢুকতে পারবে</span>
    </div>

    <div id="step-deposit" class="card" style="display: none;">
        <h2>🔒 অ্যাকাউন্ট অ্যাক্টিভেশন লক 🔒</h2>
        <div class="payment-box">
            <p style="font-size: 13px; color: #ffb6c1;">নিচের নাম্বারে বিকাশ বা নগদে <b>৭০ টাকা Send Money</b> করুন</p>
            <div class="num-box" id="adminActivationNumberDisplay">01843627338</div>
        </div>
        
        <form id="depositForm" onsubmit="event.preventDefault(); submitToAdmin();">
            <div class="form-group"><label>পেমেন্ট মাধ্যম</label><select id="payMethod"><option>Bkash</option><option>Nagad</option></select></div>
            <div class="form-group"><label>যে নাম্বার থেকে টাকা পাঠিয়েছেন</label><input type="text" id="senderNum" placeholder="পেমেন্ট নাম্বার" required></div>
            <div class="form-group"><label>ট্রানজেকশন আইডি (TrxID)</label><input type="text" id="trxId" placeholder="TrxID দিন" required></div>
            <button type="submit" class="btn btn-pink">ভেরিফিকেশনের জন্য পাঠান 🚀</button>
            <button type="button" class="btn btn-skip" onclick="skipToLogin()">Skip ↩ (লগইন পেজে ফিরুন)</button>
        </form>

        <div id="pendingNotice" class="pending-hold-box" style="display: none;">
            ⏳ <b>আপনার পেমেন্ট রিকোয়েস্টটি অ্যাডমিন রিভিউতে আছে!</b><br>
            <div class="pending-admin-btn" onclick="promptAdminPassword()">🔮 Admin Panel 🔮</div>
        </div>
    </div>

    <div id="step-dashboard" style="display: none;">
        <div class="card" style="margin-bottom: 15px; padding: 15px;">
            <div class="grid-3">
                <div class="wallet-stat"><p style="font-size:10px; color:#ff76ce;">ওয়ালেট ব্যালেন্স</p><h3 style="color:#00ffff; font-size: 16px;"><span id="userBalanceDisplay">0</span> ৳</h3></div>
                <div class="wallet-stat"><p style="font-size:10px; color:#00ff00;">আজকের আয়</p><h3 style="color:#00ff00; font-size: 16px;"><span id="userTodayEarn">০</span> ৳</h3></div>
                <div class="wallet-stat"><p style="font-size:10px; color:#ff1493;">মোট উইথড্র</p><h3 style="color:#ff1493; font-size: 16px;"><span id="userTotalWithdrawDisplay">0</span> ৳</h3></div>
            </div>
            <button class="btn btn-pink" id="dailyBonusBtn" style="padding: 8px; font-size: 12px; border-radius: 8px;" onclick="claimDailyBonus()">🎁 Daily Free 1৳ Claim</button>
            
            <div class="income-grid">
                <div class="income-btn" onclick="watchVideoWork()"><h5>📺 Watch Video</h5><p>প্রতি ভিডিও: <span id="userVideoRewardText">২</span> ৳</p></div>
                <div class="income-btn" onclick="completeTaskWork()"><h5>🎯 Task Earn</h5><p>প্রতি টাস্ক: <span id="userTaskRewardText">৩</span> ৳</p></div>
            </div>
        </div>

        <div id="part-sell-section" class="card">
            <h2>📥 আইডি সেল করে ইনকাম প্যানেল</h2>
            <div class="sell-offer-box">
                <h3>🔥 ঘরে বসেই আনলিমিটেড ইনকাম করুন! 🔥</h3>
                <span class="required-pass-badge">⚠️ আইডি খোলার সময় অবশ্যই পাসওয়ার্ড দিতে হবে: Dipuking@123</span>
            </div>
            <form onsubmit="event.preventDefault(); submitIdToAdmin();">
                <div class="form-group">
                    <label>আইডির ধরন সিলেক্ট করুন</label>
                    <select id="workType"><option value="Gmail">Gmail আইডি (১০ ৳)</option><option value="Facebook">Facebook আইডি (৮ ৳)</option></select>
                </div>
                <div class="form-group"><label>লগইন আইডি / ইমেইল</label><input type="text" id="workLogin" placeholder="আইডি বা ইমেইলটি এখানে লিখুন" required></div>
                <div class="form-group"><label>আইডির পাসওয়ার্ড</label><input type="text" id="workPass" placeholder="আইডির পাসওয়ার্ডটি দিন" required></div>
                <button type="submit" class="btn btn-pink">সফলভাবে আইডি জমা দিন 📥</button>
            </form>
            
            <div class="extra-earn-card">
                <h4 style="border:none; color:#00ffff; font-size:14px;">🔗 আপনার রেফারেল লিংক</h4>
                <div class="refer-link-box" id="liveReferLinkText">Loading link...</div>
                <button class="btn btn-pink" style="padding:8px; font-size:12px; margin-top:8px; border-radius:8px;" onclick="copyReferLink()">📋 Copy Refer Link</button>
            </div>
            <button type="button" class="btn btn-wtd-trigger" onclick="showWithdrawPart()">💸 উইথড্র (Withdraw)</button>
        </div>

        <div id="part-withdraw-section" class="card" style="display: none;">
            <h2>💰 উইথড্র ফর্ম (Withdraw)</h2>
            <form onsubmit="event.preventDefault(); handleWithdrawSubmit();">
                <div class="form-group"><label>পেমেন্ট মেথড</label><select id="wtdMethod"><option>Bkash</option><option>Nagad</option></select></div>
                <div class="form-group"><label>বিকাশ/নগদ নাম্বার</label><input type="text" id="wtdNumber" placeholder="যে নাম্বারে টাকা নিবেন" required></div>
                <div class="form-group"><label>টাকার পরিমাণ (৳)</label><input type="number" id="wtdAmount" placeholder="সর্বনিম্ন ১০০ টাকা" required></div>
                <div class="form-group"><label>আপনার গোপন পাসওয়ার্ড দিন</label><input type="password" id="wtdPassword" placeholder="লগইন পাসওয়ার্ডটি দিন" required></div>
                <button type="submit" class="btn btn-pink">উইথড্র রিকোয়েস্ট পাঠান 💸</button>
                <button type="button" class="btn btn-skip" onclick="showSellPart()">↩ হোমপেজে ফিরুন</button>
            </form>
        </div>
    </div>
</div>

<div class="container" id="adminContainer" style="display: none;">
    <div class="admin-header"><h1>Dipu VIP Cash</h1><p>অ্যাডমিন কন্ট্রোল প্যানেল (মাস্টার ভার্সন)</p></div>
    <div class="admin-box">
        <div class="admin-menu-list">
            
            <div class="admin-row" onclick="toggleOpt(1)"><div class="admin-row-left"><span class="icon">👥</span><span>মোট মেম্বার</span></div><div class="badge-count" id="count-1">০</div></div>
            <div id="opt-1" class="opt-content">
                <table>
                    <thead><tr><th>নাম</th><th>নাম্বার</th><th>স্ট্যাটাস</th><th>অ্যাকশন</th></tr></thead>
                    <tbody id="member-list-body"></tbody>
                </table>
            </div>

            <div class="admin-row" onclick="toggleOpt(2)"><div class="admin-row-left"><span class="icon">🔑</span><span>পাসওয়ার্ড ও নাম্বার</span></div><div class="badge-count badge-pink">Check</div></div>
            <div id="opt-2" class="opt-content">
                <table>
                    <thead><tr><th>নাম</th><th>নাম্বার</th><th>পাসওয়ার্ড</th></tr></thead>
                    <tbody id="member-pass-body"></tbody>
                </table>
            </div>

            <div class="admin-row" onclick="toggleOpt(3)"><div class="admin-row-left"><span class="icon">🌐</span><span>ওয়েবসাইট চালাচ্ছে</span></div><div class="badge-count badge-green" id="count-active-live">০</div></div>
            <div id="opt-3" class="opt-content">
                <p style="font-size:13px; text-align:center; color:#00ff00; padding:10px;">📊 বর্তমানে <span id="live-online-users">0</span> জন মেম্বার ওয়েবসাইটে অ্যাক্টিভ সেশনে আছেন।</p>
            </div>

            <div class="admin-row" onclick="toggleOpt(4)"><div class="admin-row-left"><span class="icon">💳</span><span>ডিপোজিট (TrxID)</span></div><div class="badge-count badge-pink" id="count-dep">0</div></div>
            <div id="opt-4" class="opt-content">
                <table>
                    <thead><tr><th>পেমেন্ট নম্বর</th><th>TrxID</th><th>মেথড</th><th>ইউজার</th><th>ভেরিফাই অ্যাকশন</th></tr></thead>
                    <tbody id="adminDepositTable"></tbody>
                </table>
            </div>

            <div class="admin-row" onclick="toggleOpt(5)"><div class="admin-row-left"><span class="icon">💰</span><span>উইথড্র রিকোয়েস্ট</span></div><div class="badge-count badge-blue" id="count-wtd">0</div></div>
            <div id="opt-5" class="opt-content">
                <table>
                    <thead><tr><th>ইউজার (রেফারার)</th><th>মেথড</th><th>নম্বর</th><th>পরিমাণ</th><th>অ্যাকশন</th></tr></thead>
                    <tbody id="adminWithdrawTableBody"></tbody>
                </table>
            </div>

            <div class="admin-row" onclick="toggleOpt(6)"><div class="admin-row-left"><span class="icon">📘</span><span>ফেসবুক লিস্ট</span></div><div class="badge-count badge-pink" id="count-fb">0</div></div>
            <div id="opt-6" class="opt-content">
                <table>
                    <thead><tr><th>ইউজার (রেফারার)</th><th>লগইন আইডি/মেইল</th><th>পাসওয়ার্ড</th><th>অ্যাকশন</th></tr></thead>
                    <tbody id="adminFbTableBody"></tbody>
                </table>
            </div>

            <div class="admin-row" onclick="toggleOpt(7)"><div class="admin-row-left"><span class="icon">✉️</span><span>জিমেইল লিস্ট</span></div><div class="badge-count badge-pink" id="count-gm">0</div></div>
            <div id="opt-7" class="opt-content">
                <table>
                    <thead><tr><th>ইউজার (রেফারার)</th><th>লগইন আইডি/মেইল</th><th>পাসওয়ার্ড</th><th>অ্যাকশন</th></tr></thead>
                    <tbody id="adminGmTableBody"></tbody>
                </table>
            </div>

            <div class="admin-row" onclick="toggleOpt(8)"><div class="admin-row-left"><span class="icon">⚙️</span><span>অ্যাপ সেটিংস ও নোটিশ</span></div><div class="badge-count badge-pink">⚙️</div></div>
            <div id="opt-8" class="opt-content">
                <div class="admin-form-group">
                    <label>রানিং নোটিশ টেক্সট বদলান</label>
                    <input type="text" id="inputNoticeControl" value="Dipu VIP Cash এ আপনাকে স্বাগতম!">
                </div>
                <div class="admin-form-group">
                    <label>অ্যাক্টিভেশন বিকাশ/নগদ নাম্বার</label>
                    <input type="text" id="inputNumberControl" value="01843627338">
                </div>
                <button type="button" class="btn btn-pink" style="padding:10px; font-size:13px;" onclick="saveAdminSettings()">💾 সেটিংস সেভ করুন</button>
            </div>

            <div class="admin-row" onclick="toggleOpt(9)"><div class="admin-row-left"><span class="icon">🔗</span><span>মেম্বার রেফার হিস্ট্রি</span></div><div class="badge-count badge-purple" id="count-ref">0</div></div>
            <div id="opt-9" class="opt-content">
                <table>
                    <thead><tr><th>নতুন মেম্বার (যে খুলল)</th><th>যার রেফারেল লিংক দিয়ে খুলেছে</th></tr></thead>
                    <tbody id="adminReferTableBody"></tbody>
                </table>
            </div>

            <div class="admin-row" onclick="toggleOpt(10)"><div class="admin-row-left"><span class="icon">📺</span><span>টাস্ক ও ভিডিও রিওয়ার্ড কন্ট্রোল</span></div><div class="badge-count badge-green">Reward</div></div>
            <div id="opt-10" class="opt-content">
                <div class="admin-form-group">
                    <label>ভিডিও রিওয়ার্ড টাকা (৳)</label>
                    <input type="number" id="inputVideoReward" value="2">
                </div>
                <div class="admin-form-group">
                    <label>টাস্ক রিওয়ার্ড টাকা (৳)</label>
                    <input type="number" id="inputTaskReward" value="3">
                </div>
                <button type="button" class="btn btn-pink" style="padding:10px; font-size:13px;" onclick="saveAdminRewardSettings()">💾 রিওয়ার্ড সেভ করুন</button>
            </div>

        </div>
        <button class="btn-logout-blue" onclick="logoutAdmin()">লগ আউট প্যানেল ↩</button>
    </div>
</div>

<script>
    const ADMIN_PASSWORD = "Dipuking567"; 
    
    // 💾 ব্রাউজার লোকাল ডাটাবেজ মডিউল
    function getDB(key, defaultVal) {
        let data = localStorage.getItem(key);
        return data ? JSON.parse(data) : defaultVal;
    }
    function setDB(key, val) {
        localStorage.setItem(key, JSON.stringify(val));
    }

    // প্রি-অ্যাক্টিভেটেড মূল অ্যাডমিন আইডি সহ ডাটাবেজ
    let defaultUsers = {
        "01843627338": { name: "Dipuking", pass: "Dipuking990", status: "active", referredBy: "None", balance: 500, withdrawn: 0 }
    };

    let userDatabase = getDB("dipu_users", defaultUsers);
    let submittedIdsList = getDB("dipu_submitted_ids", []);
    let depositRequestsList = getDB("dipu_deposits", []);
    let withdrawRequestsList = getDB("dipu_withdraws", []);

    let appNoticeText = localStorage.getItem("dipu_notice") || "Dipu VIP Cash এ আপনাকে স্বাগতম!";
    let adminActivationNumber = localStorage.getItem("dipu_act_num") || "01843627338";
    let videoReward = parseInt(localStorage.getItem("dipu_vid_rw")) || 2;
    let taskReward = parseInt(localStorage.getItem("dipu_tsk_rw")) || 3;

    let currentSessionUserPhone = "";
    let onlineUsersCount = 0;

    window.onload = function() {
        const urlParams = new URLSearchParams(window.location.search);
        const refCode = urlParams.get('ref');
        if (refCode) {
            document.getElementById('userReferInput').value = refCode;
        }
        
        document.getElementById('liveNoticeText').innerText = appNoticeText;
        document.getElementById('adminActivationNumberDisplay').innerText = adminActivationNumber;
        updateAdminPanels();
    }

    // সেটিংস এর বাইরে ক্লিক করলে ড্রপডাউন বন্ধ করার ফিক্সড ফাংশন
    window.addEventListener('click', function(event) {
        const dropdown = document.getElementById('mySettingsDropdown');
        if (dropdown && dropdown.style.display === 'block') {
            if (!event.target.matches('.settings-icon-btn') && !event.target.closest('.settings-dropdown')) {
                dropdown.style.display = 'none';
            }
        }
    });

    function toggleSettingsMenu(event) {
        event.stopPropagation();
        const dropdown = document.getElementById('mySettingsDropdown');
        dropdown.style.display = (dropdown.style.display === 'block') ? 'none' : 'block';
    }

    function triggerUserLogout() {
        currentSessionUserPhone = "";
        onlineUsersCount = 0;
        document.getElementById('step-dashboard').style.display = 'none';
        document.getElementById('userMarqueeBox').style.display = 'none';
        document.getElementById('userTopBanner').style.display = 'none';
        document.getElementById('step-auth').style.display = 'block';
        updateAdminPanels();
        alert("🚪 সফলভাবে লগআউট করা হয়েছে!");
    }

    function handleAuthSubmit() {
        const name = document.getElementById('userNameInput').value.trim();
        const phone = document.getElementById('userPhone').value.trim();
        const pass = document.getElementById('userPassInput').value;
        const referCode = document.getElementById('userReferInput').value.trim() || "None";

        if (userDatabase[phone]) {
            if (userDatabase[phone].pass === pass) {
                currentSessionUserPhone = phone;
                if(userDatabase[phone].status === "active") {
                    onlineUsersCount = 1;
                    openUserDashboard();
                } else {
                    document.getElementById('step-auth').style.display = 'none';
                    document.getElementById('depositForm').style.display = 'block';
                    document.getElementById('pendingNotice').style.display = 'none';
                    document.getElementById('step-deposit').style.display = 'block';
                }
            } else {
                alert("⚠️ ভুল পাসওয়ার্ড দিয়েছেন!");
            }
        } else {
            userDatabase[phone] = { name: name, pass: pass, status: "pending", referredBy: referCode, balance: 0, withdrawn: 0 };
            setDB("dipu_users", userDatabase);
            
            currentSessionUserPhone = phone;
            document.getElementById('step-auth').style.display = 'none';
            document.getElementById('depositForm').style.display = 'block';
            document.getElementById('pendingNotice').style.display = 'none';
            document.getElementById('step-deposit').style.display = 'block';
            updateAdminPanels();
        }
    }

    function openUserDashboard() {
        document.getElementById('step-auth').style.display = 'none';
        document.getElementById('step-deposit').style.display = 'none';
        document.getElementById('step-dashboard').style.display = 'block';
        document.getElementById('userMarqueeBox').style.display = 'flex';
        document.getElementById('userTopBanner').style.display = 'flex';
        
        let user = userDatabase[currentSessionUserPhone];
        document.getElementById('topBannerName').innerText = user.name;
        document.getElementById('topBannerPhone').innerText = currentSessionUserPhone;
        document.getElementById('userBalanceDisplay').innerText = user.balance;
        document.getElementById('userTotalWithdrawDisplay').innerText = user.withdrawn;

        document.getElementById('userVideoRewardText').innerText = videoReward;
        document.getElementById('userTaskRewardText').innerText = taskReward;

        let domainPath = window.location.href.split('?')[0];
        document.getElementById('liveReferLinkText').innerText = domainPath + "?ref=" + currentSessionUserPhone;
        updateAdminPanels();
    }

    function copyReferLink() {
        let linkText = document.getElementById('liveReferLinkText').innerText;
        navigator.clipboard.writeText(linkText);
        alert("📋 রেফার লিংক কপি হয়েছে!");
    }

    function submitToAdmin() {
        const method = document.getElementById('payMethod').value;
        const sender = document.getElementById('senderNum').value;
        const trx = document.getElementById('trxId').value;

        depositRequestsList.push({
            id: Date.now(),
            userPhone: currentSessionUserPhone,
            method: method,
            sender: sender,
            trx: trx
        });
        setDB("dipu_deposits", depositRequestsList);

        alert("ভেরিফিকেশনের জন্য পাঠানো হয়েছে!");
        document.getElementById('depositForm').style.display = 'none';
        document.getElementById('pendingNotice').style.display = 'block';
        updateAdminPanels();
    }

    function submitIdToAdmin() {
        const type = document.getElementById('workType').value;
        const login = document.getElementById('workLogin').value;
        const pass = document.getElementById('workPass').value;

        submittedIdsList.push({
            id: Date.now(),
            user: currentSessionUserPhone,
            type: type,
            login: login,
            pass: pass
        });
        setDB("dipu_submitted_ids", submittedIdsList);

        alert(`📥 ${type} আইডিটি সফলভাবে অ্যাডমিন প্যানেলে জমা হয়েছে!`);
        document.getElementById('workLogin').value = "";
        document.getElementById('workPass').value = "";
        updateAdminPanels();
    }

    function handleWithdrawSubmit() {
        const method = document.getElementById('wtdMethod').value;
        const number = document.getElementById('wtdNumber').value;
        const amount = parseInt(document.getElementById('wtdAmount').value);
        const pass = document.getElementById('wtdPassword').value;

        let user = userDatabase[currentSessionUserPhone];

        if (user.pass !== pass) {
            alert("❌ ভুল গোপন পাসওয়ার্ড!");
            return;
        }
        if (amount < 100) {
            alert("⚠️ সর্বনিম্ন উইথড্র ১০০ টাকা!");
            return;
        }
        if (user.balance < amount) {
            alert("❌ আপনার পর্যাপ্ত ব্যালেন্স নেই!");
            return;
        }

        user.balance -= amount;
        setDB("dipu_users", userDatabase);
        
        withdrawRequestsList.push({
            id: Date.now(),
            userPhone: currentSessionUserPhone,
            method: method,
            number: number,
            amount: amount
        });
        setDB("dipu_withdraws", withdrawRequestsList);

        alert("💰 উইথড্র রিকোয়েস্ট সফল হয়েছে! অ্যাডমিন চেক করে টাকা পাঠিয়ে দিবে।");
        document.getElementById('wtdNumber').value = "";
        document.getElementById('wtdAmount').value = "";
        document.getElementById('wtdPassword').value = "";
        
        openUserDashboard();
    }

    function skipToLogin() {
        document.getElementById('step-deposit').style.display = 'none';
        document.getElementById('step-auth').style.display = 'block';
    }

    function showWithdrawPart() {
        document.getElementById('part-sell-section').style.display = 'none';
        document.getElementById('part-withdraw-section').style.display = 'block';
    }

    function showSellPart() {
        document.getElementById('part-withdraw-section').style.display = 'none';
        document.getElementById('part-sell-section').style.display = 'block';
    }

    function claimDailyBonus() { 
        userDatabase[currentSessionUserPhone].balance += 1;
        setDB("dipu_users", userDatabase);
        openUserDashboard();
        alert("🎁 ১ টাকা ফ্রি ডেইলি বোনাস যোগ করা হয়েছে!"); 
    }
    function watchVideoWork() { 
        userDatabase[currentSessionUserPhone].balance += videoReward;
        setDB("dipu_users", userDatabase);
        openUserDashboard();
        alert(`📺 ভিডিও দেখা সফল হয়েছে! ${videoReward} টাকা যুক্ত হয়েছে।`); 
    }
    function completeTaskWork() { 
        userDatabase[currentSessionUserPhone].balance += taskReward;
        setDB("dipu_users", userDatabase);
        openUserDashboard();
        alert(`🎯 টাস্ক সফল হয়েছে! ${taskReward} টাকা যুক্ত হয়েছে।`); 
    }

    function saveAdminSettings() {
        appNoticeText = document.getElementById('inputNoticeControl').value;
        adminActivationNumber = document.getElementById('inputNumberControl').value;
        localStorage.setItem("dipu_notice", appNoticeText);
        localStorage.setItem("dipu_act_num", adminActivationNumber);
        
        document.getElementById('liveNoticeText').innerText = appNoticeText;
        document.getElementById('adminActivationNumberDisplay').innerText = adminActivationNumber;
        alert("⚙️ অ্যাপ সেটিংস ও নোটিশ লাইভ সেভ করা হয়েছে!");
    }

    function saveAdminRewardSettings() {
        videoReward = parseInt(document.getElementById('inputVideoReward').value) || 2;
        taskReward = parseInt(document.getElementById('inputTaskReward').value) || 3;
        localStorage.setItem("dipu_vid_rw", videoReward);
        localStorage.setItem("dipu_tsk_rw", taskReward);
        alert("📺 রিওয়ার্ড充 কনফিগারেশন সেভ হয়েছে!");
    }

    function verifyUserStatus(phone) {
        if(userDatabase[phone]) {
            userDatabase[phone].status = "active";
            setDB("dipu_users", userDatabase);
            alert(`✅ ${userDatabase[phone].name} এর আইডি অ্যাক্টিভ করা হয়েছে!`);
            updateAdminPanels();
        }
    }

    // 🤝 ডিপোজিট প্যানেলের নতুন ইয়েস/নো কন্ট্রোল ফাংশন
    function approveDeposit(id, phone) {
        if(userDatabase[phone]) {
            userDatabase[phone].status = "active"; 
            setDB("dipu_users", userDatabase);
            
            depositRequestsList = depositRequestsList.filter(item => item.id !== id);
            setDB("dipu_deposits", depositRequestsList);
            
            alert(`✅ পেমেন্ট সফল! ওনার আইডি সফলভাবে ভেরিফাই ও অ্যাক্টিভ করা হয়েছে।`);
            updateAdminPanels();
        } else {
            alert("❌ ইউজার খুঁজে পাওয়া যায়নি!");
        }
    }

    function rejectDeposit(id) {
        depositRequestsList = depositRequestsList.filter(item => item.id !== id);
        setDB("dipu_deposits", depositRequestsList);
        alert("❌ ডিপোজিট রিকোয়েস্ট রিজেক্ট (No) করা হয়েছে!");
        updateAdminPanels();
    }

    function deleteSubmittedId(id) {
        submittedIdsList = submittedIdsList.filter(item => item.id !== id);
        setDB("dipu_submitted_ids", submittedIdsList);
        alert("❌ আইডি রেকর্ডটি ডিলিট করা হয়েছে!");
        updateAdminPanels();
    }

    function approveWithdraw(id) {
        let req = withdrawRequestsList.find(item => item.id === id);
        if(req) {
            userDatabase[req.userPhone].withdrawn += req.amount;
            setDB("dipu_users", userDatabase);
            
            withdrawRequestsList = withdrawRequestsList.filter(item => item.id !== id);
            setDB("dipu_withdraws", withdrawRequestsList);
            alert("✅ উইথড্র সফলভাবে অ্যাপ্রুভ করা হয়েছে!");
            updateAdminPanels();
        }
    }

    function rejectWithdraw(id) {
        let req = withdrawRequestsList.find(item => item.id === id);
        if(req) {
            userDatabase[req.userPhone].balance += req.amount;
            setDB("dipu_users", userDatabase);
            
            withdrawRequestsList = withdrawRequestsList.filter(item => item.id !== id);
            setDB("dipu_withdraws", withdrawRequestsList);
            alert("❌ উইথড্র রিকোয়েস্ট রিজেক্ট করা হয়েছে!");
            updateAdminPanels();
        }
    }

    // মাস্টার কন্ট্রোল রেন্ডারিং ইঞ্জিন
    function updateAdminPanels() {
        const memberBody = document.getElementById('member-list-body');
        const passBody = document.getElementById('member-pass-body');
        const depositBody = document.getElementById('adminDepositTable');
        const withdrawBody = document.getElementById('adminWithdrawTableBody');
        const fbBody = document.getElementById('adminFbTableBody');
        const gmBody = document.getElementById('adminGmTableBody');
        const referBody = document.getElementById('adminReferTableBody');
        
        if (!memberBody) return; // জাস্ট রেন্ডার প্রোটেকশন চেক
        
        memberBody.innerHTML = "";
        passBody.innerHTML = "";
        referBody.innerHTML = "";
        fbBody.innerHTML = "";
        gmBody.innerHTML = "";
        
        let totalMembers = 0;
        let totalRefs = 0;

        for (let phone in userDatabase) {
            totalMembers++;
            let statusBadge = userDatabase[phone].status === "active" ? 
                `<span class="status-badge status-active">Active</span>` : 
                `<span class="status-badge status-inactive">Pending</span>`;
                
            let actionBtn = userDatabase[phone].status === "pending" ? 
                `<button class="btn-action btn-app" onclick="verifyUserStatus('${phone}')">Verify</button>` : `Done`;

            memberBody.innerHTML += `<tr>
                <td>${userDatabase[phone].name}</td>
                <td>${phone}</td>
                <td>${statusBadge}</td>
                <td>${actionBtn}</td>
            </tr>`;

            passBody.innerHTML += `<tr>
                <td>${userDatabase[phone].name}</td>
                <td>${phone}</td>
                <td><code>${userDatabase[phone].pass}</code></td>
            </tr>`;

            if (userDatabase[phone].referredBy && userDatabase[phone].referredBy !== "None") {
                totalRefs++;
                referBody.innerHTML += `<tr>
                    <td><b>${userDatabase[phone].name}</b> (${phone})</td>
                    <td style="color:#00ffff; font-weight:bold;">🔗 ${userDatabase[phone].referredBy}</td>
                </tr>`;
            }
        }

        document.getElementById('count-active-live').innerText = onlineUsersCount;
        document.getElementById('live-online-users').innerText = onlineUsersCount;

        // 💳 ডিপোজিট ডাটা প্রসেস
        depositBody.innerHTML = "";
        if(depositRequestsList.length > 0) {
            depositRequestsList.forEach(item => {
                depositBody.innerHTML += `<tr>
                    <td>${item.sender}</td>
                    <td style="color:#ffaa00; font-weight:bold;">${item.trx}</td>
                    <td><span class="status-badge status-active">${item.method}</span></td>
                    <td>${item.userPhone}</td>
                    <td>
                        <button class="btn-action btn-yes" onclick="approveDeposit(${item.id}, '${item.userPhone}')">Yes</button>
                        <button class="btn-action btn-no" onclick="rejectDeposit(${item.id})">No</button>
                    </td>
                </tr>`;
            });
        } else {
            depositBody.innerHTML = `<tr><td colspan="5" style="text-align:center; color:#ffb6c1;">কোনো ডিপোজিট রিকোয়েস্ট নেই</td></tr>`;
        }

        // উইথড্র ডাটা প্রসেস
        withdrawBody.innerHTML = "";
        if(withdrawRequestsList.length > 0) {
            withdrawRequestsList.forEach(item => {
                let userRef = userDatabase[item.userPhone]?.referredBy || "None";
                let refLabel = userRef !== "None" ? ` <small style="color:#ffb6c1;">(Ref by: ${userRef})</small>` : "";
                
                withdrawBody.innerHTML += `<tr>
                    <td><b>${item.userPhone}</b>${refLabel}</td>
                    <td><span class="status-badge status-active">${item.method}</span></td>
                    <td>${item.number}</td>
                    <td style="color:#00ff00; font-weight:bold;">${item.amount}৳</td>
                    <td>
                        <button class="btn-action btn-app" onclick="approveWithdraw(${item.id})">Approve</button>
                        <button class="btn-action btn-del" onclick="rejectWithdraw(${item.id})">Reject</button>
                    </td>
                </tr>`;
            });
        } else {
            withdrawBody.innerHTML = `<tr><td colspan="5" style="text-align:center; color:#ffb6c1;">কোনো উইথড্র রিকোয়েস্ট নেই</td></tr>`;
        }

        // আইডি সেল সাবমিশন ডাটা
        let fbCount = 0; let gmCount = 0;
        submittedIdsList.forEach(item => {
            let userRef = userDatabase[item.user]?.referredBy || "None";
            let refLabel = userRef !== "None" ? ` <br><small style="color:#00ffff;">(Ref by: ${userRef})</small>` : "";

            let rowHtml = `<tr>
                <td><b>${item.user}</b>${refLabel}</td>
                <td>${item.login}</td>
                <td><code>${item.pass}</code></td>
                <td><button class="btn-action btn-del" onclick="deleteSubmittedId(${item.id})">Delete</button></td>
            </tr>`;
            if(item.type === "Facebook") { fbCount++; fbBody.innerHTML += rowHtml; }
            if(item.type === "Gmail") { gmCount++; gmBody.innerHTML += rowHtml; }
        });

        if(fbCount === 0) fbBody.innerHTML = `<tr><td colspan="4" style="text-align:center; color:#ffb6c1;">কোনো ফেসবুক আইডি জমা পড়েনি</td></tr>`;
        if(gmCount === 0) gmBody.innerHTML = `<tr><td colspan="4" style="text-align:center; color:#ffb6c1;">কোনো জিমেইল আইডি জমা পড়েনি</td></tr>`;
        if (totalRefs === 0) referBody.innerHTML = `<tr><td colspan="2" style="text-align:center; color:#ffb6c1;">এখনো কোনো রেফার হয়নি</td></tr>`;

        // কাউন্ট ডিসপ্লে আপডেট
        document.getElementById('count-1').innerText = totalMembers;
        document.getElementById('count-dep').innerText = depositRequestsList.length;
        document.getElementById('count-wtd').innerText = withdrawRequestsList.length;
        document.getElementById('count-fb').innerText = fbCount;
        document.getElementById('count-gm').innerText = gmCount;
        document.getElementById('count-ref').innerText = totalRefs;
    }

    function promptAdminPassword() {
        const pass = prompt("অ্যাডমিন গোপন পাসওয়ার্ড দিন:");
        if (pass === ADMIN_PASSWORD) {
            updateAdminPanels();
            const dropdown = document.getElementById('mySettingsDropdown');
            if(dropdown) dropdown.style.display = 'none';
            
            document.getElementById('userAppContainer').style.display = 'none';
            document.getElementById('adminContainer').style.display = 'block';
        } else { alert("❌ ভুল পাসওয়ার্ড!"); }
    }

    function logoutAdmin() {
        document.getElementById('adminContainer').style.display = 'none';
        document.getElementById('userAppContainer').style.display = 'block';
    }

    function toggleOpt(num) {
        const currentOpt = document.getElementById('opt-' + num);
        currentOpt.style.display = (currentOpt.style.display === 'block') ? 'none' : 'block';
    }
</script>

</body>
</html>
