[index.html.html](https://github.com/user-attachments/files/32337072/index.html.html)
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>客舱行李放置英语 · 实训系统</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" />
    <style>
        * { margin:0; padding:0; box-sizing:border-box; }
        body { font-family:'Segoe UI','PingFang SC',Roboto,sans-serif; background:#f0f4f9; color:#1a2a3a; padding-top:68px; line-height:1.6; }
        .navbar { position:fixed; top:0; left:0; right:0; z-index:1000; background:linear-gradient(145deg,#1a3a2e,#2c6e5a); padding:0 14px; height:64px; display:flex; align-items:center; justify-content:space-between; box-shadow:0 4px 20px rgba(26,58,46,0.35); gap:4px; flex-wrap:nowrap; }
        .navbar .brand { display:flex; align-items:center; gap:8px; color:#fff; font-weight:700; font-size:0.85rem; white-space:nowrap; }
        .navbar .brand i { color:#f5d98f; font-size:1.1rem; }
        .navbar .brand span { font-size:0.6rem; font-weight:400; opacity:0.6; }
        .navbar .nav-links { display:flex; gap:2px; flex-wrap:nowrap; overflow-x:auto; }
        .navbar .nav-links a { color:rgba(255,255,255,0.6); text-decoration:none; padding:4px 10px; border-radius:30px; font-size:0.65rem; font-weight:600; transition:all 0.25s; white-space:nowrap; cursor:pointer; }
        .navbar .nav-links a:hover { color:#fff; background:rgba(255,255,255,0.08); }
        .navbar .nav-links a.active { color:#1a3a2e; background:#f5d98f; }
        .navbar .right-actions { display:flex; align-items:center; gap:6px; flex-shrink:0; }
        .navbar .print-btn { background:rgba(255,255,255,0.1); border:1px solid rgba(255,255,255,0.15); color:#fff; padding:3px 12px; border-radius:30px; font-size:0.6rem; font-weight:600; cursor:pointer; display:flex; align-items:center; gap:4px; }
        .navbar .print-btn:hover { background:rgba(255,255,255,0.2); }
        .container { max-width:1100px; margin:0 auto; padding:12px 14px 30px; }
        .page { display:none; animation:fadeUp 0.3s ease; }
        .page.active { display:block; }
        @keyframes fadeUp { from { opacity:0; transform:translateY(10px); } to { opacity:1; transform:translateY(0); } }
        .card { background:#fff; border-radius:16px; padding:18px 20px; box-shadow:0 2px 12px rgba(0,0,0,0.04); margin-bottom:18px; border:1px solid rgba(0,0,0,0.02); }
        .card-title { font-size:1.05rem; font-weight:700; color:#1a3a2e; margin-bottom:12px; display:flex; align-items:center; gap:10px; }
        .card-title i { color:#c99f4a; font-size:1rem; }
        .card-title .sub { font-weight:400; font-size:0.7rem; color:#8a9eb0; margin-left:auto; }
        .section-desc { color:#4a5a6e; font-size:0.9rem; margin-bottom:12px; }
        .form-row { display:grid; grid-template-columns:repeat(auto-fit,minmax(180px,1fr)); gap:12px; }
        .form-group { display:flex; flex-direction:column; gap:3px; }
        .form-group label { font-weight:600; font-size:0.78rem; color:#1a3a2e; }
        .form-group input, .form-group textarea, .form-group select { padding:6px 12px; border-radius:8px; border:1px solid #dce4ec; font-size:0.85rem; background:#fafcff; transition:0.2s; font-family:inherit; }
        .form-group input:focus, .form-group textarea:focus, .form-group select:focus { border-color:#c99f4a; outline:none; box-shadow:0 0 0 3px rgba(201,159,74,0.08); }
        .btn { padding:5px 16px; border-radius:30px; border:none; font-weight:600; font-size:0.75rem; cursor:pointer; transition:all 0.2s; display:inline-flex; align-items:center; gap:5px; }
        .btn-primary { background:#f5d98f; color:#1a3a2e; }
        .btn-primary:hover { background:#ffe8b5; }
        .btn-success { background:#2d7d5a; color:#fff; }
        .btn-success:hover { background:#3a9d72; }
        .btn-outline { background:transparent; border:1.5px solid #dce4ec; color:#5a6e82; }
        .btn-outline:hover { border-color:#b6cce0; background:#f7faff; }
        .btn-sm { padding:3px 12px; font-size:0.65rem; }
        .text-muted { color:#8a9eb0; font-size:0.78rem; }
        .text-gold { color:#c99f4a; }

        .vocab-grid { display:grid; grid-template-columns:repeat(auto-fill,minmax(220px,1fr)); gap:12px; }
        .vocab-card { background:#f7faff; border-radius:12px; padding:14px 16px; border:1px solid #e6edf6; transition:0.2s; }
        .vocab-card:hover { border-color:#b6cce0; background:#f0f6fe; }
        .vocab-card .word { font-weight:700; font-size:1.05rem; color:#1a3a2e; }
        .vocab-card .phonetic { font-size:0.8rem; color:#8a9eb0; margin-left:6px; font-weight:400; }
        .vocab-card .meaning { font-size:0.85rem; color:#4a5a6e; margin:2px 0 6px; }
        .vocab-card .actions { display:flex; align-items:center; gap:6px; flex-wrap:wrap; margin-top:6px; }
        .vocab-card .actions .speak-btn { background:rgba(201,159,74,0.12); border:none; color:#c99f4a; width:30px; height:30px; border-radius:50%; cursor:pointer; font-size:0.8rem; }
        .vocab-card .actions .speak-btn:hover { background:#c99f4a; color:#fff; }
        .vocab-card .actions .record-btn { background:rgba(52,152,219,0.12); border:none; color:#2980b9; width:30px; height:30px; border-radius:50%; cursor:pointer; font-size:0.8rem; }
        .vocab-card .actions .record-btn:hover { background:#2980b9; color:#fff; }
        .vocab-card .actions .record-btn.recording { background:#c0392b; color:#fff; animation:pulse-icon 0.6s infinite; }
        .vocab-card .score-display { margin-top:6px; font-size:0.8rem; font-weight:600; display:flex; align-items:center; gap:6px; }
        .vocab-card .score-display .score-value { padding:2px 10px; border-radius:20px; font-size:0.85rem; }
        .score-excellent { background:#d4edda; color:#1a6e4a; }
        .score-good { background:#d6eaf8; color:#1a5276; }
        .score-fair { background:#fdebd0; color:#935e38; }
        .score-poor { background:#fadbd8; color:#922b21; }
        .score-none { background:#e6edf6; color:#8a9eb0; }
        @keyframes pulse-icon { 0%,100% { transform:scale(1); opacity:1; } 50% { transform:scale(0.85); opacity:0.6; } }

        /* 句型分组 */
        .phrase-section { margin-bottom:20px; }
        .phrase-section-title { font-weight:700; font-size:0.95rem; color:#1a3a2e; padding:8px 14px; background:#f0f4f9; border-radius:10px; margin-bottom:8px; display:flex; align-items:center; gap:10px; }
        .phrase-section-title .badge { font-size:0.65rem; font-weight:600; background:#c99f4a; color:#fff; padding:0 12px; border-radius:20px; line-height:1.8; }

        /* ★ 句型卡片（支持单词级发音） */
        .phrase-item { padding:10px 14px; background:#f7faff; border-radius:10px; border-left:4px solid #c99f4a; margin-bottom:8px; transition:0.2s; }
        .phrase-item:hover { background:#f0f6fe; }
        .phrase-item .en-line { display:flex; flex-wrap:wrap; align-items:center; gap:3px; margin-bottom:6px; }
        .phrase-item .en-line .word-chip { display:inline-block; padding:2px 7px; border-radius:6px; font-weight:600; font-size:0.92rem; color:#1a3a2e; cursor:pointer; user-select:none; transition:0.15s; }
        .phrase-item .en-line .word-chip:hover { background:rgba(201,159,74,0.15); color:#c99f4a; }
        .phrase-item .en-line .word-chip.speaking { background:#c99f4a; color:#fff; animation:pulse-icon 0.8s infinite; }
        .phrase-item .zh-line { color:#4a5a6e; font-size:0.85rem; padding-left:2px; margin-bottom:6px; }
        .phrase-item .sentence-actions { display:flex; align-items:center; gap:8px; flex-wrap:wrap; padding-top:6px; border-top:1px dashed #e6edf6; }
        .btn-sentence { background:linear-gradient(135deg,#c99f4a,#e0b96a); border:none; color:#fff; padding:5px 14px; border-radius:20px; font-size:0.72rem; font-weight:600; cursor:pointer; display:inline-flex; align-items:center; gap:5px; transition:0.2s; box-shadow:0 2px 6px rgba(201,159,74,0.25); }
        .btn-sentence:hover { background:linear-gradient(135deg,#b88f3a,#c99f4a); transform:translateY(-1px); }
        .btn-sentence.playing { background:linear-gradient(135deg,#2d7d5a,#3a9d72); animation:pulse-icon 0.8s infinite; }
        .word-hint { font-size:0.68rem; color:#8a9eb0; margin-left:4px; font-weight:400; }

        /* ★ 对话卡片（支持单词级发音） */
        .dialogue-grid { display:grid; grid-template-columns:repeat(auto-fill,minmax(460px,1fr)); gap:20px; }
        .dialogue-card { background:#ffffff; border-radius:16px; padding:20px 22px; border:1px solid #e6edf6; transition:0.25s; display:flex; flex-direction:column; box-shadow:0 2px 6px rgba(0,0,0,0.02); }
        .dialogue-card:hover { border-color:#b6cce0; box-shadow:0 4px 16px rgba(0,0,0,0.06); }
        .dialogue-card .d-header { display:flex; align-items:center; gap:12px; margin-bottom:14px; flex-wrap:wrap; border-bottom:1px solid #f0f4f9; padding-bottom:10px; }
        .dialogue-card .d-num { font-size:0.65rem; font-weight:700; color:#c99f4a; background:rgba(201,159,74,0.12); padding:3px 14px; border-radius:30px; }
        .dialogue-card .d-title { font-weight:700; font-size:1.05rem; color:#1a3a2e; }
        .dialogue-card .d-scene-label { font-size:0.7rem; color:#8a9eb0; margin-left:auto; background:#e6edf6; padding:2px 14px; border-radius:30px; }
        .dialogue-card .d-body { display:flex; flex-direction:column; gap:8px; margin:6px 0 12px; max-height:600px; overflow-y:auto; padding-right:4px; }
        .dialogue-card .d-body::-webkit-scrollbar { width:4px; }
        .dialogue-card .d-body::-webkit-scrollbar-thumb { background:#c99f4a; border-radius:10px; }
        .dialogue-card .d-line { padding:10px 14px; border-radius:12px; background:#fafcff; border-left:4px solid #c99f4a; }
        .dialogue-card .d-line.crew { background:#f2f8f0; border-left-color:#2c6e5a; }
        .dialogue-card .d-line.passenger { background:#f7faff; border-left-color:#2980b9; }
        .dialogue-card .d-line .d-speaker { font-weight:700; font-size:0.8rem; color:#4a5a6e; display:flex; align-items:center; gap:6px; margin-bottom:4px; }
        .dialogue-card .d-line .d-en-line { display:flex; flex-wrap:wrap; align-items:center; gap:3px; margin-bottom:4px; }
        .dialogue-card .d-line .d-en-line .word-chip { display:inline-block; padding:2px 7px; border-radius:6px; font-weight:600; font-size:0.98rem; color:#1a2a3a; cursor:pointer; user-select:none; transition:0.15s; }
        .dialogue-card .d-line .d-en-line .word-chip:hover { background:rgba(201,159,74,0.15); color:#c99f4a; }
        .dialogue-card .d-line .d-en-line .word-chip.speaking { background:#c99f4a; color:#fff; animation:pulse-icon 0.8s infinite; }
        .dialogue-card .d-line .d-trans { font-size:0.88rem; color:#5a6e82; line-height:1.5; padding-top:4px; border-top:1px dashed rgba(0,0,0,0.05); margin-bottom:6px; }
        .dialogue-card .d-line .d-actions { display:flex; align-items:center; gap:8px; flex-wrap:wrap; }
        .dialogue-card .d-audio-bar { display:flex; align-items:center; gap:8px; margin-top:12px; padding-top:12px; border-top:1px solid #e6edf6; flex-wrap:wrap; }
        .dialogue-card .d-audio-bar .btn-audio-sm { background:rgba(201,159,74,0.1); border:none; color:#c99f4a; padding:5px 14px; border-radius:30px; font-size:0.7rem; font-weight:600; cursor:pointer; display:inline-flex; align-items:center; gap:6px; }
        .dialogue-card .d-audio-bar .btn-audio-sm:hover { background:#c99f4a; color:#fff; }
        .dialogue-card .d-audio-bar .btn-audio-sm.playing { background:#2d7d5a; color:#fff; animation:pulse-icon 0.8s infinite; }
        .dialogue-card .d-audio-bar .btn-recording-sm { background:rgba(41,128,185,0.1); border:none; color:#2980b9; padding:5px 14px; border-radius:30px; font-size:0.7rem; font-weight:600; cursor:pointer; display:inline-flex; align-items:center; gap:6px; }
        .dialogue-card .d-audio-bar .btn-recording-sm:hover { background:#2980b9; color:#fff; }
        .dialogue-card .d-audio-bar .btn-recording-sm.recording { background:#c0392b; color:#fff; animation:pulse-icon 0.6s infinite; }
        .dialogue-card .d-audio-bar .d-status { font-size:0.7rem; color:#8a9eb0; }
        .dialogue-card .d-audio-bar .d-status.done { color:#2d7d5a; font-weight:600; }

        .case-card { display:grid; grid-template-columns:1fr 1fr; gap:16px; }
        .case-card .info-item { background:#f7faff; border-radius:10px; padding:12px 16px; border:1px solid #e6edf6; }
        .case-card .info-item .label { font-weight:600; font-size:0.75rem; color:#8a9eb0; text-transform:uppercase; letter-spacing:0.5px; }
        .case-card .info-item .value { font-weight:700; font-size:1rem; color:#1a3a2e; margin-top:2px; }
        .case-card .info-item .value.en { color:#2980b9; font-weight:600; font-size:0.9rem; }
        .case-card .info-item .value.zh { color:#4a5a6e; font-size:0.85rem; }
        @media (max-width:600px) { .case-card { grid-template-columns:1fr; } }

        .role-grid { display:grid; grid-template-columns:repeat(auto-fit,minmax(180px,1fr)); gap:12px; }
        .role-card { background:#f7faff; border-radius:12px; padding:12px 14px; border:1px solid #e6edf6; }
        .role-card .r-title { font-weight:700; font-size:0.85rem; color:#1a3a2e; display:flex; align-items:center; gap:6px; }
        .role-card .r-title .icon { color:#c99f4a; }
        .role-card .r-name input { width:100%; padding:4px 10px; border-radius:6px; border:1px solid #dce4ec; font-size:0.8rem; background:#fff; margin-top:4px; }

        .script-step { display:flex; align-items:center; gap:10px; padding:8px 12px; background:#fafcff; border-radius:8px; border:1px solid #e6edf6; margin-bottom:6px; flex-wrap:wrap; }
        .script-step .step-num { font-weight:700; font-size:0.75rem; color:#8a9eb0; min-width:30px; }
        .script-step select, .script-step input { padding:4px 8px; border-radius:6px; border:1px solid #dce4ec; font-size:0.8rem; background:#fff; flex:1 1 140px; min-width:100px; }
        .script-step .custom-input { flex:2 1 180px; }
        .script-step .btn-remove-step { background:transparent; border:none; color:#c0392b; cursor:pointer; font-size:0.8rem; padding:2px 6px; }
        .script-preview { background:#f7faff; border-radius:10px; padding:12px 16px; border:1px solid #e6edf6; margin-top:10px; white-space:pre-wrap; font-family:'Consolas',monospace; font-size:0.85rem; line-height:1.8; max-height:300px; overflow-y:auto; }

        .eval-item { display:flex; align-items:center; gap:12px; padding:8px 14px; background:#f7faff; border-radius:10px; border:1px solid #e6edf6; flex-wrap:wrap; }
        .eval-item .e-label { font-weight:600; font-size:0.82rem; color:#1a3a2e; min-width:100px; }
        .eval-item .e-desc { font-size:0.75rem; color:#5a6e82; flex:1; min-width:80px; }
        .eval-item .e-score-input select { padding:3px 8px; border-radius:6px; border:1px solid #dce4ec; font-size:0.8rem; background:#fff; font-weight:600; width:70px; }
        .score-summary { display:grid; grid-template-columns:repeat(auto-fit,minmax(160px,1fr)); gap:14px; margin-bottom:16px; }
        .score-box { background:#f7faff; border-radius:12px; padding:14px 16px; text-align:center; border:1px solid #e6edf6; }
        .score-box .label { font-size:0.72rem; color:#5a6e82; }
        .score-box .value { font-size:1.8rem; font-weight:700; color:#1a3a2e; }
        .score-box .value.gold { color:#c99f4a; }
        .score-box .value.green { color:#2d7d5a; }
        .score-box .weight { font-size:0.65rem; color:#8a9eb0; }
        .score-detail table { width:100%; border-collapse:collapse; font-size:0.82rem; }
        .score-detail th { background:#f0f4f9; padding:6px 10px; text-align:left; font-weight:700; color:#1a3a2e; border-bottom:2px solid #dce4ec; }
        .score-detail td { padding:5px 10px; border-bottom:1px solid #e6edf6; }

        .toast { position:fixed; bottom:24px; right:24px; background:#1a3a2e; color:#fff; padding:8px 20px; border-radius:12px; box-shadow:0 8px 24px rgba(0,0,0,0.2); font-weight:600; transform:translateY(100px); opacity:0; transition:all 0.4s ease; z-index:999; max-width:400px; font-size:0.8rem; }
        .toast.show { transform:translateY(0); opacity:1; }
        .toast.success { background:#2d7d5a; }
        .toast.error { background:#c0392b; }
        .toast.info { background:#2980b9; }
        .footer { text-align:center; padding:14px 0 4px; color:#8a9eb0; font-size:0.65rem; border-top:1px solid #e6edf6; margin-top:4px; }
        .footer i { color:#c99f4a; }
        .recognition-status { font-size:0.75rem; color:#5a6e82; padding:4px 10px; border-radius:20px; background:#f0f4f9; display:inline-block; margin-top:4px; }
        .recognition-status.active { background:#d6eaf8; color:#1a5276; }
        .recognition-status.error { background:#fadbd8; color:#922b21; }
        .recognition-status.success { background:#d4edda; color:#1a6e4a; }

        @media print {
            body { padding-top:0; background:#fff; }
            .navbar { display:none !important; }
            .page { display:block !important; animation:none !important; }
            .card { box-shadow:none !important; border:1px solid #ddd; }
            .btn { display:none !important; }
            .btn-sentence { display:none !important; }
            .dialogue-grid { grid-template-columns:repeat(2,1fr); }
            .vocab-grid { grid-template-columns:repeat(2,1fr); }
            .word-chip { background:none !important; color:#000 !important; }
        }
        @media (max-width:820px) {
            .navbar { padding:0 10px; height:56px; }
            .navbar .brand { font-size:0.7rem; }
            .navbar .brand span { display:none; }
            .navbar .nav-links a { font-size:0.55rem; padding:3px 8px; }
            body { padding-top:60px; }
            .container { padding:10px; }
            .vocab-grid { grid-template-columns:repeat(auto-fill,minmax(180px,1fr)); }
            .dialogue-grid { grid-template-columns:1fr; }
            .role-grid { grid-template-columns:1fr 1fr; }
            .form-row { grid-template-columns:1fr; }
            .score-summary { grid-template-columns:1fr 1fr; }
        }
        @media (max-width:480px) {
            .navbar .nav-links a { font-size:0.5rem; padding:2px 6px; }
            .navbar .brand { font-size:0.6rem; }
            .navbar .right-actions .print-btn span { display:none; }
            .vocab-grid { grid-template-columns:1fr; }
            .role-grid { grid-template-columns:1fr; }
            .score-summary { grid-template-columns:1fr; }
            .dialogue-grid { grid-template-columns:1fr; }
            .case-card { grid-template-columns:1fr; }
        }
    </style>
</head>
<body>

    <nav class="navbar" id="navbar">
        <div class="brand">
            <i class="fas fa-suitcase"></i>
            行李放置 <span>· 英语实训</span>
        </div>
        <div class="nav-links">
            <a class="active" data-page="page-info"><i class="fas fa-info-circle"></i> 小组</a>
            <a data-page="page-case"><i class="fas fa-clipboard-list"></i> 案例信息</a>
            <a data-page="page-vocab"><i class="fas fa-book-open"></i> 词汇</a>
            <a data-page="page-phrases"><i class="fas fa-comment-dots"></i> 句型</a>
            <a data-page="page-dialogue"><i class="fas fa-comments"></i> 对话卡片</a>
            <a data-page="page-performance"><i class="fas fa-user-tag"></i> 模拟展演</a>
            <a data-page="page-eval"><i class="fas fa-chalkboard-teacher"></i> 师评成绩</a>
        </div>
        <div class="right-actions">
            <button class="print-btn" onclick="window.print()"><i class="fas fa-print"></i> <span>打印</span></button>
        </div>
    </nav>

    <div class="container">

        <!-- 小组信息 -->
        <div class="page active" id="page-info">
            <div class="card">
                <div class="card-title"><i class="fas fa-info-circle"></i> 小组基本信息</div>
                <div class="form-row">
                    <div class="form-group"><label><i class="fas fa-school"></i> 班级</label><input type="text" id="className" placeholder="请输入班级" /></div>
                    <div class="form-group"><label><i class="fas fa-tag"></i> 小组名称</label><input type="text" id="groupName" placeholder="如：第1组 / Sky Team" /></div>
                    <div class="form-group"><label><i class="fas fa-hashtag"></i> 小组编号</label><input type="text" id="groupId" placeholder="如：G01" /></div>
                    <div class="form-group"><label><i class="fas fa-tasks"></i> 实训任务</label><input type="text" id="taskName" value="行李放置英语实训" /></div>
                    <div class="form-group"><label><i class="fas fa-user-tie"></i> 指导教师</label><input type="text" id="teacherName" placeholder="请输入姓名" /></div>
                </div>
                <div style="margin-top:10px;">
                    <button class="btn btn-success" id="saveInfoBtn"><i class="fas fa-save"></i> 保存信息</button>
                    <span class="text-muted" style="margin-left:10px;">数据自动保存在浏览器</span>
                </div>
            </div>
            <div class="card">
                <div class="card-title"><i class="fas fa-clipboard-list"></i> 任务说明</div>
                <p style="color:#4a5a6e;font-size:0.92rem;">
                    本实训系统基于 <strong>HU7480 三亚→北京 航班登机阶段行李放置</strong> 真实案例设计。
                    通过 <strong>词汇跟读评分</strong>、<strong>句型逐词发音</strong>、<strong>对话卡片学习</strong>、<strong>模拟展演对话编排</strong> 四个环节，
                    掌握 <strong>6大情境、28个核心句型</strong>，实现“会认、会说、会用”的学习目标。
                </p>
                <div style="background:#fcf9f0;border-radius:10px;padding:12px 16px;border-left:4px solid #c99f4a;margin-top:10px;">
                    <strong style="color:#1a3a2e;">💡 特色功能：</strong>
                    <span style="color:#4a5a6e;font-size:0.88rem;">① 点击任意单词听发音并显示中文释义；② 每句提供"整句朗读"按钮；③ 支持跟读评分与对话录音。</span>
                </div>
            </div>
        </div>

        <!-- 案例信息 -->
        <div class="page" id="page-case">
            <div class="card">
                <div class="card-title"><i class="fas fa-clipboard-list"></i> HU7480 行李放置案例 <span class="sub">案例详情</span></div>
                <p class="section-desc">以下为本次行李放置英语实训所使用的完整案例信息。</p>
                <div style="background:#f7faff;border-radius:10px;padding:14px 16px;border-left:4px solid #c99f4a;margin-bottom:14px;">
                    <p style="color:#1a3a2e;font-size:0.92rem;line-height:1.8;">
                        <strong>✈️ 航班：</strong> HU7480 三亚（SYX）→ 北京（PEK）<br>
                        <strong>📅 日期：</strong> 2025年1月20日 &nbsp;|&nbsp; <strong>机型：</strong> 空客 A330-300<br>
                        <strong>⏰ 阶段：</strong> 登机阶段（离港时间 22:10）
                    </p>
                </div>
                <div class="case-card">
                    <div class="info-item"><div class="label">旅客 / Passenger</div><div class="value en">Ms. Wang, Seat 23A</div><div class="value zh">王女士，座位23A</div></div>
                    <div class="info-item"><div class="label">行李问题 / Issue</div><div class="value en">Baggage cannot fit into overhead bin</div><div class="value zh">行李无法放入行李架</div></div>
                    <div class="info-item"><div class="label">乘务员解决 / Solution</div><div class="value en">Find space → Lead to front cabin</div><div class="value zh">寻找空位 → 引导至前舱</div></div>
                    <div class="info-item"><div class="label">关键句型 / Key Sentence</div><div class="value en">"Let me help you put it in the overhead compartment."</div><div class="value zh">“我来帮您放进行李架。”</div></div>
                </div>
                <div style="margin-top:14px;background:#fcf9f0;border-radius:10px;padding:10px 16px;border-left:4px solid #c99f4a;">
                    <strong style="color:#1a3a2e;">📌 案例要点：</strong>
                    <span style="color:#4a5a6e;font-size:0.9rem;">登机阶段，旅客行李无法放入行李架（行李架已满/尺寸过大/阻塞通道/阻塞紧急出口/易碎品/旅客不会放置），乘务员需用英语提供专业、礼貌、安全的解决方案。</span>
                </div>
            </div>
        </div>

        <!-- 词汇 -->
        <div class="page" id="page-vocab">
            <div class="card">
                <div class="card-title"><i class="fas fa-book-open"></i> 行李放置核心词汇 <span class="sub">点击 <i class="fas fa-volume-up"></i> 听发音 · 点击 <i class="fas fa-microphone"></i> 跟读评分</span></div>
                <p class="section-desc">共20个行李放置专属词汇，点击喇叭听标准发音，点击麦克风跟读评分。</p>
                <div class="vocab-grid" id="vocabGrid"></div>
                <div style="margin-top:12px;display:flex;gap:10px;flex-wrap:wrap;align-items:center;">
                    <button class="btn btn-outline btn-sm" id="resetVocabScoresBtn"><i class="fas fa-redo-alt"></i> 重置所有评分</button>
                    <span class="text-muted" id="vocabProgress">已学 0/20 个词汇</span>
                </div>
            </div>
        </div>

        <!-- 句型 -->
        <div class="page" id="page-phrases">
            <div class="card">
                <div class="card-title"><i class="fas fa-comment-dots"></i> 行李放置常用句型 <span class="sub">6大情境 · 点击单词发音 · 点击按钮听整句</span></div>
                <p class="section-desc">
                    <strong>①</strong> 点击句中任意单词 → 听该单词发音并显示中文释义；
                    <strong>②</strong> 点击 <i class="fas fa-volume-up text-gold"></i> <strong>整句朗读</strong>按钮 → 听整句标准发音。
                </p>
                <div id="phraseContainer"></div>
            </div>
        </div>

        <!-- 对话卡片 -->
        <div class="page" id="page-dialogue">
            <div class="card">
                <div class="card-title"><i class="fas fa-comments"></i> 行李放置对话卡片 <span class="sub">点击单词发音 · 点击按钮听整句 · 支持录音</span></div>
                <p class="section-desc">
                    <strong>点击台词中任意单词</strong>可听该单词发音并显示中文释义；<strong>点击台词下方的"整句朗读"按钮</strong>可听整句发音。
                </p>
                <div class="dialogue-grid" id="dialogueGrid"></div>
                <div style="margin-top:12px;display:flex;gap:10px;flex-wrap:wrap;align-items:center;">
                    <button class="btn btn-outline btn-sm" id="clearDialogueRecordingsBtn"><i class="fas fa-trash-alt"></i> 清除所有录音</button>
                    <span class="text-muted" id="dialogueProgress">已录音 0/6 个对话</span>
                </div>
            </div>
        </div>

        <!-- 模拟展演 -->
        <div class="page" id="page-performance">
            <div class="card">
                <div class="card-title"><i class="fas fa-user-tag"></i> 1. 角色分工（6人一组）</div>
                <div class="role-grid" id="roleGrid"></div>
                <div style="margin-top:12px;">
                    <button class="btn btn-success" id="saveRolesBtn"><i class="fas fa-save"></i> 保存角色分配</button>
                </div>
            </div>
            <div class="card">
                <div class="card-title"><i class="fas fa-pen-fancy"></i> 2. 对话文本编写</div>
                <div id="scriptEditor">
                    <div id="scriptStepsContainer"></div>
                    <div style="margin-top:8px;display:flex;gap:8px;flex-wrap:wrap;">
                        <button class="btn btn-primary btn-sm" id="addStepBtn"><i class="fas fa-plus"></i> 添加步骤</button>
                        <button class="btn btn-outline btn-sm" id="resetScriptBtn"><i class="fas fa-redo-alt"></i> 重置为默认流程</button>
                        <span class="text-muted" style="font-size:0.7rem;">共 <span id="stepCount">0</span> 个步骤</span>
                    </div>
                </div>
                <div style="margin-top:14px;">
                    <button class="btn btn-success" id="previewScriptBtn"><i class="fas fa-eye"></i> 预览对话</button>
                    <button class="btn btn-primary" id="downloadScriptBtn"><i class="fas fa-download"></i> 下载对话文本</button>
                </div>
                <div id="scriptPreviewContainer" style="margin-top:12px;display:none;">
                    <div class="card" style="background:#f7faff;border:1px solid #e6edf6;border-radius:10px;padding:12px 16px;">
                        <div class="card-title" style="font-size:0.95rem;margin-bottom:6px;"><i class="fas fa-file-alt text-gold"></i> 对话预览</div>
                        <div class="script-preview" id="scriptPreviewText"></div>
                    </div>
                </div>
            </div>
            <div class="card">
                <div class="card-title"><i class="fas fa-clipboard-check"></i> 3. 模拟展演评分（教师用）</div>
                <div id="roleplayEvalContainer"></div>
                <div style="margin-top:10px;">
                    <button class="btn btn-success" id="saveRoleplayEvalBtn"><i class="fas fa-save"></i> 保存评分</button>
                </div>
            </div>
        </div>

        <!-- 师评成绩 -->
        <div class="page" id="page-eval">
            <div class="card">
                <div class="card-title"><i class="fas fa-chalkboard-teacher"></i> 教师综合评价</div>
                <div id="teacherEvalContainer"></div>
                <div style="margin-top:10px;">
                    <button class="btn btn-success" id="saveTeacherEvalBtn"><i class="fas fa-save"></i> 保存师评</button>
                </div>
            </div>
            <div class="card">
                <div class="card-title"><i class="fas fa-chart-bar"></i> 成绩总览</div>
                <p class="text-muted" style="margin-bottom:10px;">最终成绩 = 词汇掌握 × 20% + 对话理解 × 30% + 模拟展演 × 50%</p>
                <div id="scoreSummary"></div>
                <div id="scoreDetail" class="score-detail"></div>
            </div>
        </div>

        <div class="footer">
            <i class="fas fa-suitcase"></i> 客舱行李放置英语 · 实训系统 &nbsp;|&nbsp; 数据本地存储
            <br><span style="font-size:0.6rem;">"安全放置，始于你我" —— 以专业态度，学好行李放置英语</span>
        </div>
    </div>

    <div class="toast" id="toast"></div>

    <script>
        const STORAGE_KEY = 'baggage_stowage_system_v4';

        // ===== 20个行李放置核心词汇 =====
        const VOCAB_DATA = [
            { word: 'overhead bin', phonetic: '/ˈəʊvəhed bɪn/', meaning: 'n. 行李架' },
            { word: 'stow', phonetic: '/stəʊ/', meaning: 'v. 放置、安放' },
            { word: 'baggage', phonetic: '/ˈbæɡɪdʒ/', meaning: 'n. 行李' },
            { word: 'carry-on', phonetic: '/ˈkæriɒn/', meaning: 'n. 随身行李' },
            { word: 'checked baggage', phonetic: '/tʃekt ˈbæɡɪdʒ/', meaning: 'n. 托运行李' },
            { word: 'suitcase', phonetic: '/ˈsuːtkeɪs/', meaning: 'n. 手提箱' },
            { word: 'personal item', phonetic: '/ˈpɜːsənl ˈaɪtəm/', meaning: 'n. 私人物品' },
            { word: 'aisle', phonetic: '/aɪl/', meaning: 'n. 过道' },
            { word: 'emergency exit', phonetic: '/iˈmɜːdʒənsi ˈeksɪt/', meaning: 'n. 紧急出口' },
            { word: 'turbulence', phonetic: '/ˈtɜːbjələns/', meaning: 'n. 颠簸（不可数）' },
            { word: 'cloakroom', phonetic: '/ˈkləʊkruːm/', meaning: 'n. 衣帽间' },
            { word: 'secure', phonetic: '/sɪˈkjʊə/', meaning: 'v. 固定好' },
            { word: 'fit', phonetic: '/fɪt/', meaning: 'v. 放得进、合适' },
            { word: 'fragile items', phonetic: '/ˈfrædʒaɪl ˈaɪtəmz/', meaning: 'n. 易碎物品' },
            { word: 'valuables', phonetic: '/ˈvæljuəblz/', meaning: 'n. 贵重物品' },
            { word: 'take-off', phonetic: '/ˈteɪkɒf/', meaning: 'n. 起飞' },
            { word: 'landing', phonetic: '/ˈlændɪŋ/', meaning: 'n. 着陆、降落' },
            { word: 'cargo hold', phonetic: '/ˈkɑːɡəʊ həʊld/', meaning: 'n. 货舱' },
            { word: 'oversized', phonetic: '/ˈəʊvəsaɪzd/', meaning: 'adj. 尺寸过大的' },
            { word: 'compartment', phonetic: '/kəmˈpɑːtmənt/', meaning: 'n. 隔间、行李架' }
        ];

        // ===== 单词中文释义词典（用于单词级释义显示） =====
        const WORD_DICT = {
            // 常见词汇
            'good': '好的', 'morning': '早上', 'afternoon': '下午', 'evening': '晚上',
            'welcome': '欢迎', 'aboard': '登机', 'sir': '先生', 'madam': '女士', 'miss': '女士',
            'excuse': '打扰', 'me': '我', 'please': '请', 'thank': '感谢', 'you': '您',
            'thanks': '谢谢', 'sorry': '抱歉', 'yes': '是的', 'no': '不',
            'may': '可以', 'i': '我', 'see': '看', 'your': '您的', 'boarding': '登机',
            'pass': '牌/通行证', 'here': '这里', 'are': '是', 'where': '哪里',
            'is': '是', 'my': '我的', 'seat': '座位', 'number': '号码',
            'could': '能', 'show': '展示', 'this': '这个', 'that': '那个',
            'the': '这个（定冠词）', 'a': '一个', 'an': '一个', 'and': '和',
            'in': '在……里', 'on': '在……上', 'at': '在', 'to': '到',
            'of': '……的', 'for': '为了', 'with': '和', 'from': '从',
            'we': '我们', 'us': '我们', 'our': '我们的', 'it': '它',
            'help': '帮助', 'put': '放', 'place': '放置', 'bag': '包',
            'baggage': '行李', 'luggage': '行李', 'suitcase': '手提箱',
            'overhead': '头顶的', 'bin': '行李架', 'compartment': '行李架',
            'under': '在……下面', 'front': '前面', 'behind': '后面',
            'aisle': '过道', 'window': '窗户', 'seat': '座位',
            'small': '小的', 'large': '大的', 'heavy': '重的', 'light': '轻的',
            'loose': '松散的', 'items': '物品', 'item': '物品',
            'personal': '私人的', 'fragile': '易碎的', 'valuable': '贵重的',
            'valuables': '贵重物品', 'secure': '固定好', 'safely': '安全地',
            'safe': '安全的', 'safety': '安全', 'emergency': '紧急的',
            'exit': '出口', 'block': '阻挡', 'blocking': '阻挡',
            'clear': '畅通的', 'keep': '保持', 'need': '需要',
            'other': '其他的', 'passengers': '旅客', 'passenger': '旅客',
            'flight': '航班', 'aircraft': '飞机', 'cabin': '客舱',
            'take': '拿/带', 'take-off': '起飞', 'landing': '降落',
            'land': '降落', 'turbulence': '颠簸', 'during': '在……期间',
            'may': '可能', 'fall': '掉落', 'cause': '造成', 'injury': '伤害',
            'afraid': '恐怕', 'check': '办理/检查', 'checked': '托运的',
            'ground': '地面', 'staff': '工作人员', 'gate': '登机口',
            'out': '出来', 'any': '任何', 'recommend': '建议',
            'keeping': '保持', 'double-check': '再次检查',
            'before': '在……之前', 'leave': '离开', 'aircraft': '飞机',
            'belongings': '物品', 'cooperation': '配合', 'appreciate': '感谢',
            'realize': '意识到', 'should': '应该', 'spot': '位置',
            'move': '移动', 'vacant': '空闲的', 'organize': '整理',
            'moment': '一会儿', 'worries': '担心', 'properly': '正确地',
            'slide': '滑动', 'around': '周围', 'enjoy': '享受',
            'pleasant': '愉快的', 'nice': '美好的', 'advice': '建议',
            'glass': '玻璃', 'store': '储存', 'pocket': '口袋',
            'remember': '记得', 'belongings': '物品', 'all': '所有',
            'would': '会', 'like': '喜欢', 'hand': '帮助',
            'let': '让', 'make': '使', 'sure': '确定',
            'sure': '确定', 'still': '仍然', 'some': '一些',
            'space': '空间', 'there': '那里', 'carry': '携带',
            'show': '带领', 'front': '前面', 'cabin': '客舱',
            'seems': '似乎', 'bit': '有点', 'fit': '放得进',
            'hoping': '希望', 'up': '上面', 'better': '更好的',
            'placed': '放置', 'doesn\'t': '不', 'staff': '工作人员',
            'will': '将', 'very': '非常', 'helpful': '有帮助的',
            'letting': '让', 'know': '知道', 'worries': '担心',
            'stow': '放置', 'larger': '更大的', 'organize': '整理',
            'allowed': '允许', 'near': '附近', 'could': '可能',
            'evacuation': '撤离', 'didn\'t': '没有', 'did': '做了',
            'where': '哪里', 'appreciate': '感谢', 'again': '再次',
            'recommend': '建议', 'inside': '里面', 'double-check': '仔细检查',
            'anything': '任何东西', 'else': '其他'
        };

        // ===== 28个句型 =====
        const PHRASE_DATA = [
            { en: 'Good morning! Would you like a hand with your baggage?', zh: '早上好！需要我帮您放行李吗？', tag: '行李放置' },
            { en: 'Let me help you put it in the overhead compartment and make sure it\'s secure.', zh: '我来帮您放进行李架并固定好。', tag: '行李放置' },
            { en: 'Please place small loose items inside your bag or in the seat pocket.', zh: '零散小件物品请收纳进包里或放入前排座椅口袋。', tag: '行李放置' },
            { en: 'Please remember to take all your belongings when you leave the aircraft.', zh: '下机时请记得带好您全部随身物品。', tag: '行李放置' },
            { en: 'The overhead bin above my seat is full.', zh: '我座位上方的行李架满了。', tag: '行李架已满' },
            { en: 'Don\'t worry. Let me check it for you.', zh: '别担心，我帮您看看。', tag: '行李架已满' },
            { en: 'Would you like me to help you place your bag under the seat in front of you?', zh: '需要我帮您把包放在前排座椅下方吗？', tag: '行李架已满' },
            { en: 'I can show you to the front cabin — there\'s still some space there.', zh: '我带您去前排客舱，那边还有空位。', tag: '行李架已满' },
            { en: 'Please keep fragile or valuable items with you personally.', zh: '请将易碎品和贵重物品随身携带保管好。', tag: '行李架已满' },
            { en: 'Your bag seems a bit heavy and oversized.', zh: '您的行李偏重、尺寸偏大。', tag: '尺寸过大' },
            { en: 'It doesn\'t fit in the overhead bin.', zh: '放不进行李架。', tag: '尺寸过大' },
            { en: 'For your safety, heavy items are better placed under the seat.', zh: '为了您的安全，重物最好放在座椅下方。', tag: '尺寸过大' },
            { en: 'During turbulence, heavy bags may fall and cause injury.', zh: '遇到颠簸时，重物可能掉落砸伤旅客。', tag: '尺寸过大' },
            { en: 'I\'m afraid you need to check it in.', zh: '恐怕您需要把行李进行托运。', tag: '尺寸过大' },
            { en: 'Your bag is blocking the aisle.', zh: '您的包挡住了过道。', tag: '阻塞通道' },
            { en: 'We need to keep it clear for other passengers.', zh: '我们需要保持畅通让其他旅客通行。', tag: '阻塞通道' },
            { en: 'Let me help you stow your larger bag properly.', zh: '我帮您把大包规整放好。', tag: '阻塞通道' },
            { en: 'Please put any small items into your bag or seat pocket so they don\'t slide around.', zh: '小件物品请全部装进包里或放入座椅袋，防止滑落。', tag: '阻塞通道' },
            { en: 'Please keep the aisle clear for flight safety.', zh: '为了飞行安全，请保持过道畅通。', tag: '阻塞通道' },
            { en: 'I\'m afraid baggage isn\'t allowed near the emergency exit.', zh: '紧急出口附近不允许放置行李。', tag: '阻塞紧急出口' },
            { en: 'It could block the way in case of emergency evacuation.', zh: '会挡住逃生通道。', tag: '阻塞紧急出口' },
            { en: 'I\'ll help you move it to a safe spot.', zh: '我帮您转移到安全位置。', tag: '阻塞紧急出口' },
            { en: 'I can place it in the overhead bin or under a vacant seat for you.', zh: '可以放进行李架或空闲座椅下方。', tag: '阻塞紧急出口' },
            { en: 'We appreciate your cooperation.', zh: '非常感谢您的配合。', tag: '阻塞紧急出口' },
            { en: 'Do you have any fragile or valuable items in your bag?', zh: '请问您包里有易碎品或贵重物品吗？', tag: '易碎品' },
            { en: 'I\'d recommend keeping fragile items under the seat.', zh: '我建议易碎品放在座椅下方。', tag: '易碎品' },
            { en: 'For any small loose items, feel free to store them in the seat pocket.', zh: '零散小件可以收纳在座椅口袋中。', tag: '易碎品' },
            { en: 'Please double-check your belongings before you leave the aircraft.', zh: '下机前请仔细检查随身物品，不要遗漏。', tag: '易碎品' }
        ];

        // ===== 6个完整对话 =====
        const DIALOGUE_DATA = [{
            id: 1,
            title: '旅客不会正确放置行李',
            scene: '行李放置',
            lines: [
                { speaker: 'Crew', text: 'Good morning! Would you like a hand with your baggage?', trans: '早上好！需要我帮您放行李吗？' },
                { speaker: 'Passenger', text: 'Yes, please. I\'m not sure how to stow it properly.', trans: '麻烦你了，我不知道怎么放才合适。' },
                { speaker: 'Crew', text: 'No problem. Let me help you put it in the overhead compartment and make sure it\'s secure.', trans: '没关系，我来帮您放进行李架并固定好。' },
                { speaker: 'Crew', text: 'For small loose items, please place them inside your bag or in the seat pocket in front of you. That way they won\'t fall during turbulence.', trans: '零散小件物品请收纳进包里或放入前排座椅口袋，这样颠簸时就不会掉落。' },
                { speaker: 'Passenger', text: 'Okay, thank you so much!', trans: '好的，非常感谢！' },
                { speaker: 'Crew', text: 'You\'re very welcome. Please remember to take all your belongings when you leave the aircraft. Enjoy your flight!', trans: '不客气。下机时请记得带好您全部随身物品。祝您旅途愉快！' }
            ]
        }, {
            id: 2,
            title: '行李架已满',
            scene: '行李架已满',
            lines: [
                { speaker: 'Passenger', text: 'Excuse me, the overhead bin above my seat is full. I don\'t have anywhere to put my bag.', trans: '你好，我座位上方的行李架满了，我的包没地方放了。' },
                { speaker: 'Crew', text: 'Don\'t worry. Let me check it for you. Would you like me to help you place your bag under the seat in front of you?', trans: '别担心，我帮您看看。需要我帮您把包放在前排座椅下方吗？' },
                { speaker: 'Passenger', text: 'That would be great. Thank you.', trans: '好的，谢谢。' },
                { speaker: 'Crew', text: 'Or I can show you to the front cabin — there\'s still some space there. Let me help you carry it.', trans: '或者我带您去前排客舱，那边还有空位，我帮您拿过去。' },
                { speaker: 'Crew', text: 'Please keep fragile or valuable items with you personally.', trans: '请将易碎品和贵重物品随身携带保管好。' },
                { speaker: 'Passenger', text: 'Thank you for your help!', trans: '谢谢你的帮助！' },
                { speaker: 'Crew', text: 'My pleasure. Have a nice flight!', trans: '不客气，祝您旅途愉快！' }
            ]
        }, {
            id: 3,
            title: '行李尺寸过大/超重',
            scene: '尺寸过大',
            lines: [
                { speaker: 'Crew', text: 'Excuse me, your bag seems a bit heavy and oversized. It doesn\'t fit in the overhead bin.', trans: '您好，您的行李偏重、尺寸偏大，放不进行李架。' },
                { speaker: 'Passenger', text: 'Really? I was hoping to put it up there.', trans: '是吗？我还想放上面呢。' },
                { speaker: 'Crew', text: 'For your safety, heavy items are better placed under the seat. During turbulence, heavy bags may fall and cause injury.', trans: '为了您的安全，重物最好放在座椅下方。遇到颠簸时，重物可能掉落砸伤旅客。' },
                { speaker: 'Passenger', text: 'I see.', trans: '我明白了。' },
                { speaker: 'Crew', text: 'I\'m afraid you need to check it in. The ground staff will help you at the boarding gate. Please take out any fragile or valuable items.', trans: '恐怕您需要把行李进行托运。地面工作人员会在登机口处帮助您。请把易碎品和贵重物品取出来。' },
                { speaker: 'Passenger', text: 'That\'s very helpful. Thank you for letting me know.', trans: '这很有帮助。谢谢你告诉我。' },
                { speaker: 'Crew', text: 'You\'re welcome. Enjoy your flight!', trans: '不客气。祝您旅途愉快！' }
            ]
        }, {
            id: 4,
            title: '行李阻塞过道',
            scene: '阻塞通道',
            lines: [
                { speaker: 'Crew', text: 'Excuse me, may I help you organize your belongings? Your bag is blocking the aisle, and we need to keep it clear for other passengers.', trans: '您好，我帮您整理一下物品好吗？您的包挡住了过道，我们需要保持畅通让其他旅客通行。' },
                { speaker: 'Passenger', text: 'Oh, I\'m sorry. I just put it here for a moment.', trans: '不好意思，我只是临时放了一下。' },
                { speaker: 'Crew', text: 'No worries. Let me help you stow your larger bag properly. Please put any small items into your bag or seat pocket so they don\'t slide around.', trans: '没关系。我帮您把大包规整放好。小件物品请全部装进包里或放入座椅袋，防止滑落。' },
                { speaker: 'Passenger', text: 'Thanks for your help!', trans: '谢谢你的帮助！' },
                { speaker: 'Crew', text: 'My pleasure. Please keep the aisle clear. Have a good flight!', trans: '不客气。请保持过道畅通。祝您旅途愉快！' }
            ]
        }, {
            id: 5,
            title: '行李阻塞紧急出口',
            scene: '阻塞紧急出口',
            lines: [
                { speaker: 'Crew', text: 'Excuse me, I\'m afraid baggage isn\'t allowed near the emergency exit. It could block the way in case of emergency evacuation.', trans: '您好，紧急出口附近不允许放置行李，会挡住逃生通道。' },
                { speaker: 'Passenger', text: 'Oh, I didn\'t realize that. Where should I put it?', trans: '我没注意到。那我该放哪儿呢？' },
                { speaker: 'Crew', text: 'Don\'t worry — I\'ll help you move it to a safe spot. I can place it in the overhead bin or under a vacant seat for you.', trans: '别担心，我帮您转移到安全位置。可以放进行李架或空闲座椅下方。' },
                { speaker: 'Passenger', text: 'That would be great. Thank you!', trans: '那太好了。谢谢！' },
                { speaker: 'Crew', text: 'You\'re welcome. We appreciate your cooperation.', trans: '不客气。非常感谢您的配合。' },
                { speaker: 'Passenger', text: 'I will. Thanks again!', trans: '我会的。再次感谢！' },
                { speaker: 'Crew', text: 'My pleasure. Have a pleasant flight!', trans: '不客气。祝您旅途愉快！' }
            ]
        }, {
            id: 6,
            title: '易碎品/贵重特殊物品',
            scene: '易碎品',
            lines: [
                { speaker: 'Crew', text: 'Excuse me, do you have any fragile or valuable items in your bag?', trans: '您好，请问您包里有易碎品或贵重物品吗？' },
                { speaker: 'Passenger', text: 'Yes, I have some glass items inside.', trans: '有的，里面有一些玻璃制品。' },
                { speaker: 'Crew', text: 'I see. I\'d recommend keeping fragile items under the seat.', trans: '明白了。我建议易碎品放在座椅下方。' },
                { speaker: 'Passenger', text: 'I\'ll do that.', trans: '那我放下面。' },
                { speaker: 'Crew', text: 'For any small loose items, feel free to store them in the seat pocket.', trans: '零散小件可以收纳在座椅口袋中。' },
                { speaker: 'Passenger', text: 'Thank you so much for your advice!', trans: '非常感谢您的建议！' },
                { speaker: 'Crew', text: 'You\'re very welcome. Please double-check your belongings before you leave the aircraft. Enjoy your flight!', trans: '不客气。下机前请仔细检查随身物品，不要遗漏。祝您旅途愉快！' }
            ]
        }];

        const ROLE_DATA = [
            { id: 'r1', title: '乘务员1 (CA1)', icon: 'fa-user-tie' },
            { id: 'r2', title: '乘务员2 (CA2)', icon: 'fa-user' },
            { id: 'r3', title: '乘务员3 (CA3)', icon: 'fa-user' },
            { id: 'r4', title: '乘务员4 (CA4)', icon: 'fa-user' },
            { id: 'r5', title: '乘务员5 (CA5)', icon: 'fa-user' },
            { id: 'r6', title: '乘务员6 (CA6)', icon: 'fa-user' }
        ];

        const TEACHER_EVAL_ITEMS = [
            { id: 't1', label: '词汇掌握度', desc: '20个核心词汇的认读与发音准确度', weight: 20 },
            { id: 't2', label: '对话理解与应答', desc: '6个对话卡片的理解与跟读熟练度', weight: 30 },
            { id: 't3', label: '模拟展演表现', desc: '角色投入度、语言流畅度、服务礼仪', weight: 50 }
        ];

        const ROLEPLAY_DIMENSIONS = [
            { id: 'rp1', label: '语言流畅度', desc: '英语表达自然、连贯，无明显卡顿' },
            { id: 'rp2', label: '角色投入度', desc: '情感投入、服务态度亲切、有职业感' },
            { id: 'rp3', label: '服务礼仪', desc: '站姿、手势、微笑、眼神交流规范' }
        ];

        function getDefaultData() {
            return {
                groupInfo: { className: '', groupName: '', groupId: '', taskName: '行李放置英语实训', teacher: '' },
                vocabScores: {},
                roles: ROLE_DATA.map(r => ({ ...r, member: '' })),
                scriptSteps: [
                    { roleId: 'r1', phraseIdx: 0, customText: '' },
                    { roleId: 'r2', phraseIdx: 5, customText: '' },
                    { roleId: 'r3', phraseIdx: 10, customText: '' },
                    { roleId: 'r4', phraseIdx: 15, customText: '' },
                    { roleId: 'r5', phraseIdx: 20, customText: '' },
                    { roleId: 'r6', phraseIdx: 25, customText: '' }
                ],
                dialogueRecordings: {},
                roleplayEval: {},
                teacherEval: {},
                teacherComment: '',
                updatedAt: ''
            };
        }

        function loadData() {
            try {
                const raw = localStorage.getItem(STORAGE_KEY);
                if (raw) {
                    const parsed = JSON.parse(raw);
                    if (!parsed.groupInfo) parsed.groupInfo = getDefaultData().groupInfo;
                    if (!parsed.vocabScores) parsed.vocabScores = {};
                    if (!parsed.roles || parsed.roles.length !== 6) {
                        parsed.roles = ROLE_DATA.map(r => ({ ...r, member: '' }));
                    } else {
                        parsed.roles = parsed.roles.map((r, idx) => ({ ...ROLE_DATA[idx], member: r.member || '' }));
                    }
                    if (!parsed.scriptSteps || !Array.isArray(parsed.scriptSteps) || parsed.scriptSteps.length === 0) {
                        parsed.scriptSteps = getDefaultData().scriptSteps;
                    }
                    if (!parsed.dialogueRecordings) parsed.dialogueRecordings = {};
                    if (!parsed.roleplayEval) parsed.roleplayEval = {};
                    if (!parsed.teacherEval) parsed.teacherEval = {};
                    if (parsed.teacherComment === undefined) parsed.teacherComment = '';
                    return parsed;
                }
            } catch (e) { console.warn('加载数据失败', e); }
            return getDefaultData();
        }

        function saveData(data) {
            data.updatedAt = new Date().toLocaleString();
            localStorage.setItem(STORAGE_KEY, JSON.stringify(data));
            return data;
        }

        let appData = loadData();

        function showToast(msg, type = 'success', duration = 2800) {
            const el = document.getElementById('toast');
            el.textContent = msg;
            el.className = 'toast ' + type + ' show';
            clearTimeout(el._timer);
            el._timer = setTimeout(() => el.classList.remove('show'), duration);
        }

        function speakText(text, lang = 'en-US', rate = 0.8, callback) {
            if (!window.speechSynthesis) { showToast('浏览器不支持语音合成', 'error'); return; }
            window.speechSynthesis.cancel();
            const utterance = new SpeechSynthesisUtterance(text);
            utterance.lang = lang;
            utterance.rate = rate;
            utterance.pitch = 1.0;
            utterance.volume = 1;
            utterance.onend = () => {
                document.querySelectorAll('.speaking, .playing').forEach(el => el.classList.remove('speaking', 'playing'));
                if (callback) callback();
            };
            utterance.onerror = () => {
                document.querySelectorAll('.speaking, .playing').forEach(el => el.classList.remove('speaking', 'playing'));
                if (callback) callback();
            };
            window.speechSynthesis.speak(utterance);
        }

        // ===== ★ 将句子拆分为可点击单词 =====
        function buildClickableWords(sentence) {
            const parts = sentence.split(/(\s+)/);
            let html = '';
            parts.forEach(part => {
                if (/^\s+$/.test(part)) {
                    html += ' ';
                } else if (part.trim() === '') {
                    // skip
                } else {
                    const cleanWord = part.replace(/[.,!?;:'"]/g, '').trim();
                    if (cleanWord) {
                        html += `<span class="word-chip" data-word="${cleanWord.replace(/"/g, '&quot;').replace(/'/g, '&#39;')}">${part}</span>`;
                    } else {
                        html += `<span>${part}</span>`;
                    }
                }
            });
            return html;
        }

        // ===== ★ 绑定单词点击事件（发音+释义） =====
        function bindWordClicks(container) {
            container.querySelectorAll('.word-chip').forEach(chip => {
                chip.addEventListener('click', function(e) {
                    e.stopPropagation();
                    const word = this.dataset.word;
                    if (!word) return;
                    const lowerWord = word.toLowerCase();
                    const meaning = WORD_DICT[lowerWord] || WORD_DICT[word] || '';
                    // 移除其他高亮
                    document.querySelectorAll('.word-chip.speaking').forEach(el => el.classList.remove('speaking'));
                    this.classList.add('speaking');
                    speakText(word, 'en-US', 0.75, () => { this.classList.remove('speaking'); });
                    // 显示单词+释义
                    const displayMsg = meaning ? `🔊 ${word} — ${meaning}` : `🔊 ${word}`;
                    showToast(displayMsg, 'info', 2000);
                });
            });
        }

        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', function(e) {
                e.preventDefault();
                const pageId = this.dataset.page;
                document.querySelectorAll('.nav-links a').forEach(l => l.classList.remove('active'));
                this.classList.add('active');
                document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
                document.getElementById(pageId).classList.add('active');
                if (pageId === 'page-info') loadInfoToForm();
                if (pageId === 'page-vocab') renderVocab();
                if (pageId === 'page-phrases') renderPhrases();
                if (pageId === 'page-dialogue') renderDialogues();
                if (pageId === 'page-performance') { renderRoles(); renderScriptEditor(); renderRoleplayEval(); }
                if (pageId === 'page-eval') { renderTeacherEval(); renderScore(); }
            });
        });

        function loadInfoToForm() {
            const info = appData.groupInfo;
            document.getElementById('className').value = info.className || '';
            document.getElementById('groupName').value = info.groupName || '';
            document.getElementById('groupId').value = info.groupId || '';
            document.getElementById('taskName').value = info.taskName || '行李放置英语实训';
            document.getElementById('teacherName').value = info.teacher || '';
        }
        document.getElementById('saveInfoBtn').addEventListener('click', function() {
            appData.groupInfo.className = document.getElementById('className').value.trim();
            appData.groupInfo.groupName = document.getElementById('groupName').value.trim();
            appData.groupInfo.groupId = document.getElementById('groupId').value.trim();
            appData.groupInfo.taskName = document.getElementById('taskName').value.trim();
            appData.groupInfo.teacher = document.getElementById('teacherName').value.trim();
            saveData(appData);
            showToast('小组信息已保存');
        });

        let recognition = null;

        function initSpeechRecognition() {
            if (!('webkitSpeechRecognition' in window) && !('SpeechRecognition' in window)) return null;
            const SR = window.SpeechRecognition || window.webkitSpeechRecognition;
            const rec = new SR();
            rec.lang = 'en-US';
            rec.continuous = false;
            rec.interimResults = false;
            rec.maxAlternatives = 1;
            return rec;
        }

        function calculateScore(recognized, target) {
            recognized = recognized.toLowerCase().trim();
            target = target.toLowerCase().trim();
            if (!recognized || !target) return 0;
            if (recognized === target) return 100;
            if (recognized.includes(target)) return 92;
            if (target.includes(recognized)) return 88;
            const recWords = recognized.split(/\s+/);
            const tarWords = target.split(/\s+/);
            let matchCount = 0;
            tarWords.forEach(tw => { if (recWords.some(rw => rw === tw)) matchCount++; });
            if (tarWords.length > 0) {
                const ratio = matchCount / tarWords.length;
                if (ratio >= 0.8) return 85;
                if (ratio >= 0.6) return 70;
                if (ratio >= 0.4) return 55;
            }
            const dist = levenshteinDistance(recognized, target);
            const maxLen = Math.max(recognized.length, target.length);
            if (maxLen === 0) return 0;
            return Math.round((1 - dist / maxLen) * 60);
        }

        function levenshteinDistance(a, b) {
            const matrix = [];
            for (let i = 0; i <= b.length; i++) matrix[i] = [i];
            for (let j = 0; j <= a.length; j++) matrix[0][j] = j;
            for (let i = 1; i <= b.length; i++) {
                for (let j = 1; j <= a.length; j++) {
                    if (b[i - 1] === a[j - 1]) { matrix[i][j] = matrix[i - 1][j - 1]; } else {
                        matrix[i][j] = Math.min(matrix[i - 1][j - 1] + 1, matrix[i][j - 1] + 1, matrix[i - 1][j] + 1);
                    }
                }
            }
            return matrix[b.length][a.length];
        }

        function getScoreClass(score) {
            if (score >= 80) return 'score-excellent';
            if (score >= 60) return 'score-good';
            if (score >= 40) return 'score-fair';
            if (score > 0) return 'score-poor';
            return 'score-none';
        }

        function getScoreLabel(score) {
            if (score >= 80) return '🌟 优秀';
            if (score >= 60) return '👍 良好';
            if (score >= 40) return '📖 一般';
            if (score > 0) return '💪 需练习';
            return '⏳ 待跟读';
        }

        function renderVocab() {
            const grid = document.getElementById('vocabGrid');
            grid.innerHTML = '';
            VOCAB_DATA.forEach((item, idx) => {
                const scoreData = appData.vocabScores[item.word] || { score: 0, attempts: 0 };
                const div = document.createElement('div');
                div.className = 'vocab-card';
                div.innerHTML = `
                    <div><span class="word">${item.word}</span><span class="phonetic">${item.phonetic}</span></div>
                    <div class="meaning">${item.meaning}</div>
                    <div class="actions">
                        <button class="speak-btn" data-word="${item.word}"><i class="fas fa-volume-up"></i></button>
                        <button class="record-btn" data-word="${item.word}" data-idx="${idx}"><i class="fas fa-microphone"></i></button>
                        <span class="recognition-status" id="status-${idx}">点击🎤开始跟读</span>
                    </div>
                    <div class="score-display">
                        评分：<span class="score-value ${getScoreClass(scoreData.score)}" id="score-${idx}">${scoreData.score > 0 ? scoreData.score : '—'}</span>
                        <span style="font-size:0.7rem;color:#8a9eb0;">${getScoreLabel(scoreData.score)}</span>
                    </div>`;
                grid.appendChild(div);
                div.querySelector('.speak-btn').addEventListener('click', function(e) {
                    e.stopPropagation();
                    const word = this.dataset.word;
                    document.querySelectorAll('.speak-btn.speaking').forEach(b => b.classList.remove('speaking'));
                    this.classList.add('speaking');
                    speakText(word, 'en-US', 0.7, () => { this.classList.remove('speaking'); });
                });
                const recordBtn = div.querySelector('.record-btn');
                const statusEl = document.getElementById(`status-${idx}`);
                const scoreEl = document.getElementById(`score-${idx}`);
                recordBtn.addEventListener('click', function(e) {
                    e.stopPropagation();
                    const word = this.dataset.word;
                    if (this.classList.contains('recording')) {
                        if (recognition) { try { recognition.stop(); } catch (e) {} }
                        this.classList.remove('recording');
                        return;
                    }
                    if (!('webkitSpeechRecognition' in window) && !('SpeechRecognition' in window)) {
                        showToast('当前浏览器不支持语音识别', 'error'); return;
                    }
                    if (!recognition) { recognition = initSpeechRecognition(); if (!recognition) return; }
                    recognition.lang = 'en-US';
                    recognition.continuous = false;
                    recognition.interimResults = false;
                    recognition.onstart = function() {
                        recordBtn.classList.add('recording');
                        statusEl.textContent = '🎤 正在听...';
                        statusEl.className = 'recognition-status active';
                    };
                    recognition.onresult = function(event) {
                        const result = event.results[0];
                        const transcript = result[0].transcript.toLowerCase().trim();
                        const confidence = result[0].confidence || 0;
                        const score = calculateScore(transcript, word);
                        const finalScore = Math.min(100, Math.round(score * 0.85 + confidence * 15));
                        if (!appData.vocabScores[word]) appData.vocabScores[word] = { score: 0, attempts: 0 };
                        appData.vocabScores[word].score = Math.max(appData.vocabScores[word].score, finalScore);
                        appData.vocabScores[word].attempts += 1;
                        saveData(appData);
                        statusEl.textContent = `✅ ${finalScore}分`;
                        statusEl.className = 'recognition-status success';
                        scoreEl.textContent = finalScore;
                        scoreEl.className = `score-value ${getScoreClass(finalScore)}`;
                        recordBtn.classList.remove('recording');
                        updateVocabProgress();
                    };
                    recognition.onerror = function(event) {
                        recordBtn.classList.remove('recording');
                        statusEl.textContent = '❌ 错误';
                        statusEl.className = 'recognition-status error';
                    };
                    recognition.onend = function() { recordBtn.classList.remove('recording'); };
                    try { recognition.start(); } catch (e) { recordBtn.classList.remove('recording'); }
                });
            });
            updateVocabProgress();
        }

        function updateVocabProgress() {
            let learned = 0;
            VOCAB_DATA.forEach(item => {
                const data = appData.vocabScores[item.word];
                if (data && data.score > 0) learned++;
            });
            document.getElementById('vocabProgress').textContent = `已学 ${learned}/${VOCAB_DATA.length} 个词汇`;
        }

        document.getElementById('resetVocabScoresBtn').addEventListener('click', function() {
            if (!confirm('重置所有词汇评分数据？')) return;
            appData.vocabScores = {};
            saveData(appData);
            renderVocab();
            showToast('所有评分已重置');
        });

        // ===== ★ 句型渲染（支持单词发音+整句朗读） =====
        function renderPhrases() {
            const container = document.getElementById('phraseContainer');
            container.innerHTML = '';
            const categoryMap = {
                '行李放置': '🧳 情境一：行李放置 (General Stowage)',
                '行李架已满': '📦 情境二：行李架已满 (Overhead Bin Full)',
                '尺寸过大': '📏 情境三：尺寸过大 (Oversized Baggage)',
                '阻塞通道': '🚶 情境四：阻塞通道 (Blocking the Aisle)',
                '阻塞紧急出口': '🆘 情境五：阻塞紧急出口 (Blocking Emergency Exit)',
                '易碎品': '🎯 情境六：易碎品/特殊物品 (Fragile & Special Items)'
            };
            const groups = {};
            PHRASE_DATA.forEach(p => {
                if (!groups[p.tag]) groups[p.tag] = [];
                groups[p.tag].push(p);
            });
            const order = ['行李放置', '行李架已满', '尺寸过大', '阻塞通道', '阻塞紧急出口', '易碎品'];
            order.forEach(tag => {
                if (!groups[tag]) return;
                const items = groups[tag];
                const section = document.createElement('div');
                section.className = 'phrase-section';
                let itemsHtml = '';
                items.forEach(item => {
                    itemsHtml += `
                        <div class="phrase-item">
                            <div class="en-line">${buildClickableWords(item.en)}</div>
                            <div class="zh-line">${item.zh}</div>
                            <div class="sentence-actions">
                                <button class="btn-sentence" data-sentence="${item.en.replace(/"/g, '&quot;')}"><i class="fas fa-volume-up"></i> 整句朗读</button>
                            </div>
                        </div>
                    `;
                });
                section.innerHTML = `
                    <div class="phrase-section-title">
                        <span>${categoryMap[tag] || tag}</span>
                        <span class="badge">${items.length} 句</span>
                    </div>
                    ${itemsHtml}
                `;
                container.appendChild(section);
                // 绑定单词发音
                bindWordClicks(section);
                // 绑定整句朗读按钮
                section.querySelectorAll('.btn-sentence').forEach(btn => {
                    btn.addEventListener('click', function(e) {
                        e.stopPropagation();
                        const sentence = this.dataset.sentence;
                        document.querySelectorAll('.btn-sentence.playing').forEach(b => b.classList.remove('playing'));
                        this.classList.add('playing');
                        speakText(sentence, 'en-US', 0.8, () => { this.classList.remove('playing'); });
                        showToast('🔊 正在朗读整句...', 'info', 2000);
                    });
                });
            });
        }

        // ===== ★ 对话卡片渲染（支持单词发音+整句朗读） =====
        function renderDialogues() {
            const grid = document.getElementById('dialogueGrid');
            grid.innerHTML = '';
            DIALOGUE_DATA.forEach(dial => {
                const rec = appData.dialogueRecordings[dial.id] || null;
                const card = document.createElement('div');
                card.className = 'dialogue-card';

                let linesHtml = '';
                dial.lines.forEach(line => {
                    const cls = line.speaker === 'Crew' ? 'crew' : 'passenger';
                    const speakerLabel = line.speaker === 'Crew' ? '👩‍✈️ 乘务员' : '🧑 旅客';
                    linesHtml += `
                        <div class="d-line ${cls}">
                            <div class="d-speaker"><i class="fas fa-${line.speaker === 'Crew' ? 'user-tie' : 'user'}"></i> ${speakerLabel}</div>
                            <div class="d-en-line">${buildClickableWords(line.text)}</div>
                            <div class="d-trans">${line.trans}</div>
                            <div class="d-actions">
                                <button class="btn-sentence" data-sentence="${line.text.replace(/"/g, '&quot;').replace(/'/g, '&#39;')}"><i class="fas fa-volume-up"></i> 整句朗读</button>
                            </div>
                        </div>
                    `;
                });

                const fullText = dial.lines.map(l => l.text).join(' ');

                card.innerHTML = `
                    <div class="d-header">
                        <span class="d-num">情境 ${dial.id}</span>
                        <span class="d-title">${dial.title}</span>
                        <span class="d-scene-label">${dial.scene}</span>
                    </div>
                    <div class="d-body">${linesHtml}</div>
                    <div class="d-audio-bar">
                        <button class="btn-audio-sm play-full" data-text="${fullText.replace(/"/g, '&quot;').replace(/'/g, '&#39;')}" title="播放整段对话"><i class="fas fa-play"></i> 整段播放</button>
                        <button class="btn-recording-sm start-rec" data-id="${dial.id}" title="开始录音"><i class="fas fa-circle" style="color:#c0392b;"></i> 录音</button>
                        <button class="btn-recording-sm stop-rec" data-id="${dial.id}" style="display:none;" title="停止录音"><i class="fas fa-stop"></i> 停止</button>
                        <button class="btn-recording-sm play-rec" data-id="${dial.id}" title="播放录音" ${!rec ? 'disabled' : ''}><i class="fas fa-play"></i> 播放</button>
                        <button class="btn-recording-sm delete-rec" data-id="${dial.id}" title="删除录音" ${!rec ? 'disabled' : ''}><i class="fas fa-trash-alt"></i> 删除</button>
                        <span class="d-status" id="dial-status-${dial.id}">${rec ? '✅ 已录音 ' + (rec.duration || 0) + 's' : '⏳ 未录音'}</span>
                    </div>
                `;
                grid.appendChild(card);
                // 绑定单词发音
                bindWordClicks(card);

                // 绑定每句整句朗读按钮
                card.querySelectorAll('.btn-sentence').forEach(btn => {
                    btn.addEventListener('click', function(e) {
                        e.stopPropagation();
                        const sentence = this.dataset.sentence;
                        document.querySelectorAll('.btn-sentence.playing').forEach(b => b.classList.remove('playing'));
                        this.classList.add('playing');
                        speakText(sentence, 'en-US', 0.8, () => { this.classList.remove('playing'); });
                        showToast('🔊 正在朗读整句...', 'info', 2000);
                    });
                });

                card.querySelector('.play-full').addEventListener('click', function(e) {
                    e.stopPropagation();
                    this.classList.add('playing');
                    speakText(this.dataset.text, 'en-US', 0.78, () => { this.classList.remove('playing'); });
                    showToast(`🔊 播放完整对话`, 'info', 2000);
                });

                const startBtn = card.querySelector('.start-rec');
                const stopBtn = card.querySelector('.stop-rec');
                const playBtn = card.querySelector('.play-rec');
                const deleteBtn = card.querySelector('.delete-rec');
                const statusEl = document.getElementById(`dial-status-${dial.id}`);
                let mediaRecorder = null;
                let audioChunks = [];
                let recordingStartTime = 0;

                startBtn.addEventListener('click', async function(e) {
                    e.stopPropagation();
                    if (appData.dialogueRecordings[dial.id] && appData.dialogueRecordings[dial.id].audioData) {
                        if (!confirm('已有录音，重新录音将覆盖之前的内容？')) return;
                    }
                    try {
                        const stream = await navigator.mediaDevices.getUserMedia({ audio: true });
                        mediaRecorder = new MediaRecorder(stream, { mimeType: 'audio/webm' });
                        audioChunks = [];
                        mediaRecorder.ondataavailable = (event) => { if (event.data.size > 0) audioChunks.push(event.data); };
                        mediaRecorder.onstop = () => {
                            const blob = new Blob(audioChunks, { type: 'audio/webm' });
                            const reader = new FileReader();
                            reader.onload = () => {
                                const base64 = reader.result.split(',')[1];
                                const duration = Math.round((Date.now() - recordingStartTime) / 1000);
                                appData.dialogueRecordings[dial.id] = { audioData: base64, duration, timestamp: new Date().toISOString() };
                                saveData(appData);
                                statusEl.textContent = `✅ 已录音 ${duration}s`;
                                statusEl.className = 'd-status done';
                                playBtn.disabled = false;
                                deleteBtn.disabled = false;
                                updateDialogueProgress();
                            };
                            reader.readAsDataURL(blob);
                            stream.getTracks().forEach(track => track.stop());
                            startBtn.style.display = 'inline-flex';
                            stopBtn.style.display = 'none';
                        };
                        mediaRecorder.start();
                        recordingStartTime = Date.now();
                        startBtn.style.display = 'none';
                        stopBtn.style.display = 'inline-flex';
                        showToast('🎤 录音中...', 'info', 2000);
                    } catch (err) { showToast('无法访问麦克风', 'error'); }
                });

                stopBtn.addEventListener('click', function(e) {
                    e.stopPropagation();
                    if (mediaRecorder && mediaRecorder.state === 'recording') mediaRecorder.stop();
                });

                playBtn.addEventListener('click', function(e) {
                    e.stopPropagation();
                    const data = appData.dialogueRecordings[dial.id];
                    if (!data || !data.audioData) return;
                    new Audio(`data:audio/webm;base64,${data.audioData}`).play();
                });

                deleteBtn.addEventListener('click', function(e) {
                    e.stopPropagation();
                    if (!confirm('确定删除此对话的录音吗？')) return;
                    delete appData.dialogueRecordings[dial.id];
                    saveData(appData);
                    statusEl.textContent = '⏳ 未录音';
                    statusEl.className = 'd-status';
                    playBtn.disabled = true;
                    deleteBtn.disabled = true;
                    updateDialogueProgress();
                });
            });
            updateDialogueProgress();
        }

        function updateDialogueProgress() {
            let count = 0;
            DIALOGUE_DATA.forEach(d => {
                if (appData.dialogueRecordings[d.id] && appData.dialogueRecordings[d.id].audioData) count++;
            });
            document.getElementById('dialogueProgress').textContent = `已录音 ${count}/${DIALOGUE_DATA.length} 个对话`;
        }

        document.getElementById('clearDialogueRecordingsBtn').addEventListener('click', function() {
            if (!confirm('确定清除所有对话的录音数据吗？')) return;
            appData.dialogueRecordings = {};
            saveData(appData);
            renderDialogues();
            showToast('所有录音已清除');
        });

        function renderRoles() {
            const grid = document.getElementById('roleGrid');
            grid.innerHTML = '';
            appData.roles.forEach((role, idx) => {
                const div = document.createElement('div');
                div.className = 'role-card';
                div.innerHTML = `
                    <div class="r-title"><span class="icon"><i class="fas ${role.icon}"></i></span> ${role.title}</div>
                    <div class="r-name"><input type="text" class="role-member-input" data-idx="${idx}" value="${role.member}" placeholder="姓名..." /></div>`;
                grid.appendChild(div);
                div.querySelector('.role-member-input').addEventListener('change', function() {
                    appData.roles[parseInt(this.dataset.idx)].member = this.value.trim();
                    saveData(appData);
                    renderScriptEditor();
                });
            });
        }

        document.getElementById('saveRolesBtn').addEventListener('click', function() {
            document.querySelectorAll('.role-member-input').forEach(inp => {
                appData.roles[parseInt(inp.dataset.idx)].member = inp.value.trim();
            });
            saveData(appData);
            renderScriptEditor();
            showToast('角色分配已保存');
        });

        function renderScriptEditor() {
            const container = document.getElementById('scriptStepsContainer');
            const steps = appData.scriptSteps || [];
            container.innerHTML = '';
            steps.forEach((step, idx) => {
                const div = document.createElement('div');
                div.className = 'script-step';
                const roleSelect = document.createElement('select');
                appData.roles.forEach(r => {
                    const opt = document.createElement('option');
                    opt.value = r.id;
                    opt.textContent = r.member ? `${r.title} (${r.member})` : r.title;
                    if (r.id === step.roleId) opt.selected = true;
                    roleSelect.appendChild(opt);
                });
                const phraseSelect = document.createElement('select');
                const defaultOpt = document.createElement('option');
                defaultOpt.value = '-1';
                defaultOpt.textContent = '✏️ 自定义';
                phraseSelect.appendChild(defaultOpt);
                PHRASE_DATA.forEach((p, pi) => {
                    const opt = document.createElement('option');
                    opt.value = pi;
                    opt.textContent = p.en.substring(0, 40) + '...';
                    if (pi === step.phraseIdx) opt.selected = true;
                    phraseSelect.appendChild(opt);
                });
                const customInput = document.createElement('input');
                customInput.type = 'text';
                customInput.placeholder = '自定义台词...';
                customInput.value = step.customText || '';
                const numSpan = document.createElement('span');
                numSpan.className = 'step-num';
                numSpan.textContent = `#${idx+1}`;
                const delBtn = document.createElement('button');
                delBtn.className = 'btn-remove-step';
                delBtn.innerHTML = '<i class="fas fa-trash-alt"></i>';
                delBtn.addEventListener('click', function() {
                    if (steps.length <= 1) return;
                    steps.splice(idx, 1);
                    saveData(appData);
                    renderScriptEditor();
                });
                div.appendChild(numSpan);
                div.appendChild(roleSelect);
                div.appendChild(phraseSelect);
                div.appendChild(customInput);
                div.appendChild(delBtn);
                container.appendChild(div);
                const saveStep = () => {
                    appData.scriptSteps[idx].roleId = roleSelect.value;
                    appData.scriptSteps[idx].phraseIdx = parseInt(phraseSelect.value);
                    appData.scriptSteps[idx].customText = customInput.value.trim();
                    saveData(appData);
                };
                roleSelect.addEventListener('change', saveStep);
                phraseSelect.addEventListener('change', saveStep);
                customInput.addEventListener('input', saveStep);
            });
            document.getElementById('stepCount').textContent = steps.length;
        }

        document.getElementById('addStepBtn').addEventListener('click', function() {
            appData.scriptSteps.push({ roleId: 'r1', phraseIdx: -1, customText: '' });
            saveData(appData);
            renderScriptEditor();
            showToast('已添加新步骤');
        });

        document.getElementById('resetScriptBtn').addEventListener('click', function() {
            if (!confirm('重置为默认对话流程？')) return;
            appData.scriptSteps = getDefaultData().scriptSteps;
            saveData(appData);
            renderScriptEditor();
        });

        function generatePreview() {
            const steps = appData.scriptSteps || [];
            const previewContainer = document.getElementById('scriptPreviewContainer');
            const previewText = document.getElementById('scriptPreviewText');
            if (steps.length === 0) { previewText.textContent = '暂无步骤。'; previewContainer.style.display = 'block'; return; }
            const groupInfo = appData.groupInfo;
            let lines = `客舱行李放置英语对话脚本\n小组：${groupInfo.groupName || '未命名'} (${groupInfo.groupId || ''})\n${'='.repeat(40)}\n\n`;
            steps.forEach((step) => {
                const role = appData.roles.find(r => r.id === step.roleId);
                const roleName = role ? `${role.title} (${role.member || '未分配'})` : '未知角色';
                let phrase = '';
                if (step.phraseIdx >= 0 && step.phraseIdx < PHRASE_DATA.length) phrase = PHRASE_DATA[step.phraseIdx].en;
                else phrase = step.customText || '（未填写）';
                lines += `【${roleName}】${phrase}\n`;
            });
            previewText.textContent = lines;
            previewContainer.style.display = 'block';
            return lines;
        }

        document.getElementById('previewScriptBtn').addEventListener('click', function() {
            generatePreview();
            showToast('对话预览已更新');
        });

        document.getElementById('downloadScriptBtn').addEventListener('click', function() {
            const fullText = generatePreview();
            if (!fullText) return;
            const blob = new Blob([fullText], { type: 'text/plain;charset=utf-8' });
            const url = URL.createObjectURL(blob);
            const a = document.createElement('a');
            a.href = url;
            a.download = `行李放置对话_${appData.groupInfo.groupId || '小组'}.txt`;
            document.body.appendChild(a);
            a.click();
            document.body.removeChild(a);
            URL.revokeObjectURL(url);
            showToast('✅ 已下载');
        });

        function renderRoleplayEval() {
            const container = document.getElementById('roleplayEvalContainer');
            let html = '';
            ROLEPLAY_DIMENSIONS.forEach(item => {
                const score = appData.roleplayEval[item.id] || 0;
                html += `<div class="eval-item">
                    <span class="e-label">${item.label}</span>
                    <span class="e-desc">${item.desc}</span>
                    <div class="e-score-input">
                        <select class="roleplay-score" data-id="${item.id}">
                            ${[0,10,20,30,40,50,60,70,80,90,100].map(v => `<option value="${v}" ${score===v?'selected':''}>${v}</option>`).join('')}
                        </select><span>/ 100</span>
                    </div>
                </div>`;
            });
            const total = ROLEPLAY_DIMENSIONS.reduce((sum, item) => sum + (appData.roleplayEval[item.id] || 0), 0);
            const avg = Math.round(total / ROLEPLAY_DIMENSIONS.length);
            html += `<div style="margin-top:8px;padding:8px 14px;background:#f7faff;border-radius:8px;font-weight:700;color:#1a3a2e;">模拟展演平均分：<span id="roleplayAvg">${avg}</span> / 100</div>`;
            container.innerHTML = html;
            container.querySelectorAll('.roleplay-score').forEach(sel => {
                sel.addEventListener('change', function() {
                    appData.roleplayEval[this.dataset.id] = parseInt(this.value);
                    saveData(appData);
                    const newAvg = Math.round(ROLEPLAY_DIMENSIONS.reduce((s, item) => s + (appData.roleplayEval[item.id] || 0), 0) / ROLEPLAY_DIMENSIONS.length);
                    document.getElementById('roleplayAvg').textContent = newAvg;
                    renderScore();
                });
            });
        }

        document.getElementById('saveRoleplayEvalBtn').addEventListener('click', function() {
            saveData(appData);
            showToast('模拟展演评分已保存');
            renderScore();
        });

        function renderTeacherEval() {
            const container = document.getElementById('teacherEvalContainer');
            let html = '';
            TEACHER_EVAL_ITEMS.forEach(item => {
                const score = appData.teacherEval[item.id] || 0;
                html += `<div class="eval-item">
                    <span class="e-label">${item.label}</span>
                    <span class="e-desc">${item.desc}（权重 ${item.weight}%）</span>
                    <div class="e-score-input">
                        <select class="teacher-score" data-id="${item.id}">
                            ${[0,10,20,30,40,50,60,70,80,90,100].map(v => `<option value="${v}" ${score===v?'selected':''}>${v}</option>`).join('')}
                        </select><span>/ 100</span>
                    </div>
                </div>`;
            });
            const weightedTotal = TEACHER_EVAL_ITEMS.reduce((sum, item) => sum + (appData.teacherEval[item.id] || 0) * (item.weight / 100), 0);
            html += `<div style="margin-top:10px;padding:8px 14px;background:#f7faff;border-radius:8px;font-weight:700;color:#1a3a2e;">师评加权总分：<span id="teacherWeightedTotal">${Math.round(weightedTotal)}</span> / 100</div>`;
            html += `<div style="margin-top:10px;"><label style="font-weight:600;font-size:0.8rem;color:#1a3a2e;display:block;margin-bottom:3px;"><i class="fas fa-comment"></i> 教师评语</label><textarea id="teacherComment" rows="3" style="width:100%;padding:8px 12px;border-radius:8px;border:1px solid #dce4ec;font-size:0.85rem;font-family:inherit;resize:vertical;">${appData.teacherComment || ''}</textarea></div>`;
            container.innerHTML = html;
            container.querySelectorAll('.teacher-score').forEach(sel => {
                sel.addEventListener('change', function() {
                    appData.teacherEval[this.dataset.id] = parseInt(this.value);
                    saveData(appData);
                    const newWeighted = TEACHER_EVAL_ITEMS.reduce((sum, item) => sum + (appData.teacherEval[item.id] || 0) * (item.weight / 100), 0);
                    document.getElementById('teacherWeightedTotal').textContent = Math.round(newWeighted);
                    renderScore();
                });
            });
            const commentArea = document.getElementById('teacherComment');
            if (commentArea) commentArea.addEventListener('input', function() { appData.teacherComment = this.value; saveData(appData); });
        }

        document.getElementById('saveTeacherEvalBtn').addEventListener('click', function() {
            const comment = document.getElementById('teacherComment');
            if (comment) appData.teacherComment = comment.value;
            saveData(appData);
            showToast('师评已保存');
            renderScore();
        });

        function renderScore() {
            const container = document.getElementById('scoreSummary');
            const detailContainer = document.getElementById('scoreDetail');
            let vocabTotal = 0, vocabCount = 0;
            VOCAB_DATA.forEach(item => {
                const data = appData.vocabScores[item.word];
                if (data && data.score > 0) { vocabTotal += data.score; vocabCount++; }
            });
            const vocabAvg = vocabCount > 0 ? Math.round(vocabTotal / vocabCount) : 0;
            const dialogueScore = appData.teacherEval['t2'] || 0;
            const rpTotal = ROLEPLAY_DIMENSIONS.reduce((sum, item) => sum + (appData.roleplayEval[item.id] || 0), 0);
            const rpAvg = ROLEPLAY_DIMENSIONS.length > 0 ? Math.round(rpTotal / ROLEPLAY_DIMENSIONS.length) : 0;
            const teacherWeighted = TEACHER_EVAL_ITEMS.reduce((sum, item) => sum + (appData.teacherEval[item.id] || 0) * (item.weight / 100), 0);
            const finalScore = Math.round(teacherWeighted);
            let grade = '待评定', gradeColor = '#8a9eb0';
            if (finalScore >= 90) { grade = '优秀'; gradeColor = '#2d7d5a'; }
            else if (finalScore >= 80) { grade = '良好'; gradeColor = '#2d7d5a'; }
            else if (finalScore >= 70) { grade = '中等'; gradeColor = '#c99f4a'; }
            else if (finalScore >= 60) { grade = '及格'; gradeColor = '#c99f4a'; }
            else if (finalScore > 0) { grade = '待提高'; gradeColor = '#c0392b'; }

            container.innerHTML = `
                <div class="score-box"><div class="label">词汇掌握</div><div class="value">${vocabAvg}</div><div class="weight">${vocabCount}/${VOCAB_DATA.length} 个已评分</div></div>
                <div class="score-box"><div class="label">对话理解</div><div class="value gold">${dialogueScore}</div><div class="weight">权重 30%</div></div>
                <div class="score-box"><div class="label">模拟展演</div><div class="value gold">${rpAvg}</div><div class="weight">权重 50%</div></div>
                <div class="score-box" style="background:#fdf8ee;border-color:#c99f4a;"><div class="label">最终成绩</div><div class="value green" style="font-size:2rem;">${finalScore}</div><div class="weight" style="color:${gradeColor};font-weight:700;font-size:0.85rem;">${grade}</div></div>`;
            let detailHtml = `<h4 style="color:#1a3a2e;margin:10px 0 6px;">📋 评分明细</h4>
                <table><thead><tr><th>评价维度</th><th>得分</th><th>权重</th><th>加权得分</th></tr></thead><tbody>
                    <tr><td>词汇掌握度</td><td>${vocabAvg}</td><td>—</td><td>—</td></tr>
                    <tr><td>对话理解与应答</td><td>${dialogueScore}</td><td>30%</td><td>${Math.round(dialogueScore * 0.3)}</td></tr>
                    <tr><td>模拟展演表现</td><td>${rpAvg}</td><td>50%</td><td>${Math.round(rpAvg * 0.5)}</td></tr>
                    <tr style="font-weight:700;background:#f7faff;"><td><strong>师评加权总分</strong></td><td colspan="3"><strong>${Math.round(teacherWeighted)}</strong> 分（${grade}）</td></tr>
                </tbody></table>`;
            detailContainer.innerHTML = detailHtml;
        }

        function init() {
            loadInfoToForm();
            renderVocab();
            renderPhrases();
            renderDialogues();
            renderRoles();
            renderScriptEditor();
            renderRoleplayEval();
            renderTeacherEval();
            renderScore();
            showToast('✈ 客舱行李放置英语实训系统 v4 已加载', 'success');
        }

        setInterval(() => { saveData(appData); }, 30000);
        window.addEventListener('beforeunload', () => { saveData(appData); });

        if (document.readyState === 'complete') init();
        else window.addEventListener('load', init);
    </script>
</body>
</html>
