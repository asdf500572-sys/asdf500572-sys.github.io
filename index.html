<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>7-7 Routine Challenge</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        :root {
            --primary: #2563eb; /* 기본 테마 색상 */
            --sidebar-bg: #1e293b; /* 사이드바 배경색 */
            --main-bg: #f3f4f6;
            --card-bg: #ffffff;
            --text-dark: #334155;
            --text-light: #94a3b8;
            --orange: #f97316;
            --lime: #84cc16;
        }

        body { 
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif; 
            background: var(--main-bg); margin: 0; color: var(--text-dark);
            overflow-x: hidden; /* 사이드바 열릴 때 가로 스크롤 방지 */
        }

        /* 앱 전체 컨테이너 */
        .app-layout {
            display: flex;
            min-height: 100vh;
            position: relative;
            max-width: 600px; /* 모바일 너비 제한 */
            margin: 0 auto;
            background: var(--main-bg);
            box-shadow: 0 0 20px rgba(0,0,0,0.05);
        }

        /* --- 사이드바 (Sidebar) --- */
        .sidebar {
            width: 260px;
            background: var(--sidebar-bg);
            color: #fff;
            position: fixed;
            top: 0;
            left: 0;
            height: 100%;
            z-index: 1000;
            transform: translateX(-100%);
            transition: transform 0.3s ease-in-out;
            padding: 20px;
            box-sizing: border-box;
        }
        .sidebar.open { transform: translateX(0); }
        .sidebar-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
            font-size: 1.2rem;
            font-weight: bold;
        }
        .close-sidebar-btn { background: none; border: none; color: #fff; font-size: 1.5rem; cursor: pointer; }
        
        .menu-group { margin-bottom: 25px; }
        .menu-title {
            font-size: 0.8rem; color: #64748b; font-weight: bold; margin-bottom: 10px;
            text-transform: uppercase; letter-spacing: 1px;
        }
        .menu-item {
            display: flex; align-items: center; padding: 12px; border-radius: 10px;
            cursor: pointer; transition: 0.2s; color: #cbd5e1; margin-bottom: 5px;
            font-weight: 500;
        }
        .menu-item:hover, .menu-item.active { background: rgba(255,255,255,0.1); color: #fff; }
        .menu-item i { margin-right: 15px; width: 20px; text-align: center; }
        .menu-item .active-indicator {
            margin-left: auto; width: 8px; height: 8px; border-radius: 50%;
            background: var(--primary); display: none;
        }
        .menu-item.active .active-indicator { display: block; }

        /* 오버레이 (사이드바 열릴 때 배경 어둡게) */
        .overlay {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0,0,0,0.5); z-index: 900; display: none;
        }
        .overlay.active { display: block; }


        /* --- 메인 콘텐츠 영역 --- */
        .main-content { flex: 1; padding-bottom: 40px; }

        /* 상단 바 */
        .top-bar { display: flex; justify-content: space-between; align-items: center; padding: 15px 20px; background: var(--card-bg); border-bottom: 1px solid #eee; position: sticky; top: 0; z-index: 100; }
        .menu-btn { background: none; border: none; font-size: 1.3rem; cursor: pointer; color: var(--text-dark); }
        .top-bar h2 { margin: 0; font-size: 1.1rem; font-weight: 800; color: var(--primary); letter-spacing: -0.5px; }

        /* 섹션 공통 */
        .section { padding: 15px 20px; }
        .card { background: var(--card-bg); border-radius: 16px; padding: 15px; border: 1px solid #f1f5f9; box-shadow: 0 4px 6px -1px rgba(0,0,0,0.05); }
        .card-title { font-size: 0.9rem; font-weight: bold; margin-bottom: 15px; color: var(--text-dark); display: flex; align-items: center; }
        .card-title i { margin-right: 8px; color: var(--primary); }

        /* 달력 */
        .calendar-grid { display: grid; grid-template-columns: repeat(7, 1fr); gap: 6px; text-align: center; }
        .day-label { font-size: 0.7rem; color: var(--text-light); font-weight: bold; padding-bottom: 5px; }
        .day-cell { aspect-ratio: 1/1.1; border-radius: 12px; display: flex; flex-direction: column; align-items: center; justify-content: center; cursor: pointer; transition: 0.2s; border: 2px solid transparent; }
        .day-cell.selected { border-color: var(--primary); background: #f0f7ff; }
        .day-num { font-size: 0.9rem; font-weight: 600; }
        .day-pct { font-size: 0.65rem; font-weight: 800; margin-top: 2px; }

        /* 그래프 */
        .chart-wrapper { height: 180px; width: 100%; }

        /* 리스트 */
        .routine-item { display: flex; align-items: center; padding: 14px; background: var(--card-bg); border-radius: 12px; margin-bottom: 8px; border: 1px solid #f1f5f9; box-shadow: 0 2px 4px rgba(0,0,0,0.02); }
        .routine-item input { width: 22px; height: 22px; margin-right: 15px; accent-color: var(--primary); cursor: pointer; }
        .completed { opacity: 0.5; background: #f8fafc; }
        .completed span { text-decoration: line-through; color: var(--text-light); }

        /* --- 설정 화면 (모달 -> 카드형 UI) --- */
        #settings-modal { position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.5); z-index: 1100; display: none; align-items: center; justify-content: center; padding: 20px; box-sizing: border-box; }
        .settings-card { background: #fff; width: 100%; max-width: 450px; border-radius: 20px; overflow: hidden; box-shadow: 0 10px 25px rgba(0,0,0,0.1); }
        .settings-header { display: flex; justify-content: space-between; align-items: center; padding: 20px; background: var(--sidebar-bg); color: #fff; }
        .btn-close-settings { background: none; border: none; color: #fff; font-size: 1.5rem; cursor: pointer; }
        
        .settings-body { padding: 20px; max-height: 70vh; overflow-y: auto; }
        
        /* 테마 컬러 피커 (이미지 스타일) */
        .color-picker-list { list-style: none; padding: 0; margin: 0 0 25px 0; }
        .color-option {
            display: flex; align-items: center; padding: 12px; border-radius: 10px;
            border: 1px solid #f1f5f9; margin-bottom: 8px; cursor: pointer;
            transition: 0.2s;
        }
        .color-option:hover { background: #f8fafc; }
        .color-dot { width: 24px; height: 24px; border-radius: 50%; margin-right: 15px; }
        .color-name { flex: 1; font-weight: 500; color: var(--text-dark); }
        .color-check { width: 20px; height: 20px; border: 2px solid #cbd5e1; border-radius: 50%; display: flex; align-items: center; justify-content: center; transition: 0.2s; }
        .color-check i { color: #fff; font-size: 0.7rem; opacity: 0; transition: 0.2s; }
        
        /* 선택된 컬러 스타일 */
        .color-option.selected .color-check { background: var(--primary); border-color: var(--primary); }
        .color-option.selected .color-check i { opacity: 1; }

        /* 루틴 입력 */
        .input-group { margin-bottom: 12px; }
        .input-group label { display: block; font-size: 0.8rem; margin-bottom: 6px; color: var(--text-light); font-weight: bold; }
        .input-group input { width: 100%; padding: 12px; border: 1px solid #e2e8f0; border-radius: 10px; box-sizing: border-box; font-size: 0.95rem; background: #f8fafc; }
        
        .btn-save { background: var(--primary); color: #fff; border: none; padding: 18px; width: 100%; border-radius: 14px; font-weight: bold; margin-top: 10px; cursor: pointer; font-size: 1rem; transition: 0.2s; }
        .btn-save:hover { opacity: 0.9; }
    </style>
</head>
<body>

<div class="app-layout">
    <div class="sidebar" id="sidebar">
        <div class="sidebar-header">
            <span>Routine Master</span>
            <button class="close-sidebar-btn" onclick="toggleSidebar()">&times;</button>
        </div>
        
        <div class="menu-group">
            <div class="menu-title">Main</div>
            <div class="menu-item active" onclick="showSection('dashboard')">
                <i class="fas fa-home"></i> Dashboard
                <div class="active-indicator"></div>
            </div>
        </div>
        
        <div class="menu-group">
            <div class="menu-title">Settings</div>
            <div class="menu-item" onclick="openSettings('goals')">
                <i class="fas fa-list-check"></i> Edit 7 Goals
            </div>
            <div class="menu-item" onclick="openSettings('theme')">
                <i class="fas fa-palette"></i> Theme Color
            </div>
        </div>
    </div>
    <div class="overlay" id="overlay" onclick="toggleSidebar()"></div>

    <div class="main-content">
        <div class="top-bar">
            <button class="menu-btn" onclick="toggleSidebar()"><i class="fas fa-bars"></i></button>
            <h2 id="month-title">7-7 CHALLENGE</h2>
            <div style="display: flex; gap: 10px;">
                <button onclick="changeMonth(-1)" class="menu-btn"><i class="fas fa-chevron-left"></i></button>
                <button onclick="changeMonth(1)" class="menu-btn"><i class="fas fa-chevron-right"></i></button>
            </div>
        </div>

        <div id="dashboard-section">
            <div class="section">
                <div class="card">
                    <div class="card-title"><i class="far fa-calendar-alt"></i> Monthly Progress</div>
                    <div class="calendar-grid" id="calendar-grid"></div>
                </div>
            </div>

            <div class="section">
                <div class="card">
                    <div class="card-title"><i class="fas fa-chart-line"></i> Weekly Trend</div>
                    <div class="chart-wrapper"><canvas id="weeklyChart"></canvas></div>
                </div>
            </div>

            <div class="section">
                <div class="card-title" style="font-size: 1.1rem; margin-bottom: 15px;">
                    <span id="selected-date-text">TODAY'S 7 GOALS</span>
                </div>
                <div id="routine-list"></div>
            </div>
        </div>
    </div>
</div>

<div id="settings-modal">
    <div class="settings-card">
        <div class="settings-header">
            <h3 style="margin:0;" id="settings-title">Settings</h3>
            <button class="btn-close-settings" onclick="closeSettings()">&times;</button>
        </div>
        <div class="settings-body" id="settings-body">
            </div>
    </div>
</div>

<script>
    let viewDate = new Date();
    let selectedDateStr = new Date().toISOString().split('T')[0];
    let myChart;
    const FIXED_COUNT = 7;

    let myRoutines = JSON.parse(localStorage.getItem('myRoutines_v7')) || [
        "아침 물 한잔", "침구 정리", "30분 독서", "영양제 섭취", "운동 20분", "일기 쓰기", "자정 전 취침"
    ];
    let themeColor = localStorage.getItem('themeColor') || '#2563eb';

    const themeColors = [
        { name: 'Ocean Blue', color: '#2563eb' },
        { name: 'Emerald Green', color: '#10b981' },
        { name: 'Sunset Orange', color: '#f97316' },
        { name: 'Royal Purple', color: '#7c3aed' },
        { name: 'Rose Pink', color: '#db2777' },
        { name: 'Dark Slate', color: '#334155' }
    ];

    function init() {
        applyTheme();
        renderCalendar();
        renderRoutines();
        initChart();
    }

    // --- 사이드바 & UI 로직 ---
    function toggleSidebar() {
        document.getElementById('sidebar').classList.toggle('open');
        document.getElementById('overlay').classList.toggle('active');
    }
    function showSection(sectionId) { toggleSidebar(); /* 추후 다른 섹션 추가 시 구현 */ }

    // --- 테마 로직 ---
    function applyTheme() {
        document.documentElement.style.setProperty('--primary', themeColor);
        if(myChart) {
            myChart.data.datasets[0].borderColor = themeColor;
            myChart.data.datasets[0].backgroundColor = themeColor + '15';
            myChart.update();
        }
    }

    // --- 달력 시스템 ---
    function renderCalendar() {
        const grid = document.getElementById('calendar-grid');
        grid.innerHTML = '';
        const year = viewDate.getFullYear();
        const month = viewDate.getMonth();
        document.getElementById('month-title').innerText = `${year}.${String(month+1).padStart(2,'0')}`;

        ['SUN','MON','TUE','WED','THU','FRI','SAT'].forEach(d => grid.innerHTML += `<div class="day-label">${d}</div>`);
        const firstDay = new Date(year, month, 1).getDay();
        const lastDate = new Date(year, month + 1, 0).getDate();

        for(let i=0; i<firstDay; i++) grid.innerHTML += `<div></div>`;
        for(let d=1; d<=lastDate; d++) {
            const dStr = `${year}-${String(month+1).padStart(2,'0')}-${String(d).padStart(2,'0')}`;
            const isSelected = dStr === selectedDateStr ? 'selected' : '';
            
            const data = JSON.parse(localStorage.getItem(dStr)) || new Array(FIXED_COUNT).fill(false);
            const done = data.filter(v => v).length;
            const pct = Math.round((done / FIXED_COUNT) * 100);
            const pctColor = pct > 0 ? (pct < 50 ? 'var(--orange)' : 'var(--lime)') : 'transparent';

            grid.innerHTML += `
                <div class="day-cell ${isSelected}" onclick="selectDate('${dStr}')">
                    <span class="day-num">${d}</span>
                    <span class="day-pct" style="color: ${pctColor}">${pct > 0 ? pct + '%' : ''}</span>
                </div>`;
        }
    }

    function selectDate(dateStr) {
        selectedDateStr = dateStr;
        renderCalendar();
        renderRoutines();
        updateChart();
    }

    // --- 루틴 리스트 시스템 ---
    function renderRoutines() {
        const list = document.getElementById('routine-list');
        document.getElementById('selected-date-text').innerText = `${selectedDateStr} 루틴`;
        
        let data = JSON.parse(localStorage.getItem(selectedDateStr)) || new Array(FIXED_COUNT).fill(false);
        if(data.length !== FIXED_COUNT) data = new Array(FIXED_COUNT).fill(false);

        list.innerHTML = myRoutines.map((r, i) => `
            <div class="routine-item ${data[i] ? 'completed' : ''}">
                <input type="checkbox" ${data[i] ? 'checked' : ''} onchange="toggleTask(${i})">
                <span>${r}</span>
            </div>
        `).join('');
    }

    function toggleTask(idx) {
        let data = JSON.parse(localStorage.getItem(selectedDateStr)) || new Array(FIXED_COUNT).fill(false);
        data[idx] = !data[idx];
        localStorage.setItem(selectedDateStr, JSON.stringify(data));
        renderRoutines();
        renderCalendar();
        updateChart();
    }

    // --- 차트 시스템 (추세선) ---
    function initChart() {
        const ctx = document.getElementById('weeklyChart').getContext('2d');
        myChart = new Chart(ctx, {
            type: 'line',
            data: {
                labels: ['Mon','Tue','Wed','Thu','Fri','Sat','Sun'],
                datasets: [{
                    data: getWeeklyScores(),
                    borderColor: themeColor,
                    backgroundColor: themeColor + '15',
                    fill: true, tension: 0.4, pointRadius: 4, pointBackgroundColor: '#fff', pointBorderWidth: 2
                }]
            },
            options: { 
                maintainAspectRatio: false, 
                plugins: { legend: { display: false } }, 
                scales: { 
                    y: { beginAtZero: true, max: 100, display: false }, 
                    x: { grid: { display: false }, ticks: { font: { size: 11, weight: '600' }, color: '#94a3b8' } } 
                } 
            }
        });
    }

    function updateChart() { myChart.data.datasets[0].data = getWeeklyScores(); myChart.update(); }

    function getWeeklyScores() {
        const curr = new Date(selectedDateStr);
        const day = curr.getDay();
        const diff = curr.getDate() - day + (day === 0 ? -6 : 1);
        const monday = new Date(new Date(selectedDateStr).setDate(diff));
        
        return Array.from({length: 7}, (_, i) => {
            const d = new Date(new Date(monday).setDate(monday.getDate() + i)).toISOString().split('T')[0];
            const data = JSON.parse(localStorage.getItem(d)) || [];
            if(data.length === 0) return 0;
            return Math.round((data.filter(v => v).length / FIXED_COUNT) * 100);
        });
    }

    // --- 설정 모달 시스템 (이미지 스타일 적용) ---
    function openSettings(type) {
        toggleSidebar(); // 사이드바 닫기
        const modal = document.getElementById('settings-modal');
        const title = document.getElementById('settings-title');
        const body = document.getElementById('settings-body');
        modal.style.display = 'flex';

        if(type === 'goals') {
            title.innerText = 'Edit 7 Goals';
            body.innerHTML = myRoutines.map((r, i) => `
                <div class="input-group">
                    <label>Goal ${i+1}</label>
                    <input type="text" value="${r}" class="routine-input-field">
                </div>
            `).join('') + `<button class="btn-save" onclick="saveRoutines()">Save Changes</button>`;
        } else if (type === 'theme') {
            title.innerText = 'Theme Color';
            body.innerHTML = `
                <ul class="color-picker-list">
                    ${themeColors.map(tc => `
                        <li class="color-option ${tc.color === themeColor ? 'selected' : ''}" onclick="selectTheme('${tc.color}')">
                            <div class="color-dot" style="background: ${tc.color};"></div>
                            <span class="color-name">${tc.name}</span>
                            <div class="color-check"><i class="fas fa-check"></i></div>
                        </li>
                    `).join('')}
                </ul>
                <button class="btn-save" onclick="saveTheme()">Apply Theme</button>
            `;
        }
    }

    function closeSettings() { document.getElementById('settings-modal').style.display = 'none'; }

    // 테마 선택 로직
    let tempThemeColor = themeColor;
    function selectTheme(color) {
        tempThemeColor = color;
        // UI 업데이트 (선택 표시 이동)
        document.querySelectorAll('.color-option').forEach(el => el.classList.remove('selected'));
        event.currentTarget.classList.add('selected');
    }

    function saveTheme() {
        themeColor = tempThemeColor;
        localStorage.setItem('themeColor', themeColor);
        applyTheme();
        closeSettings();
    }

    function saveRoutines() {
        const inputs = document.querySelectorAll('.routine-input-field');
        myRoutines = Array.from(inputs).map(input => input.value);
        localStorage.setItem('myRoutines_v7', JSON.stringify(myRoutines));
        renderRoutines();
        closeSettings();
    }

    function changeMonth(diff) {
        viewDate.setMonth(viewDate.getMonth() + diff);
        renderCalendar();
    }

    init();
</script>
</body>
</html>
