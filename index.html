<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Routine Master 2026</title>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        :root {
            --primary: #2563eb;
            --bg: #f3f4f6;
            --card: #ffffff;
            --success-low: #f97316; /* 50% 미만 주황색 */
            --success-high: #84cc16; /* 50% 이상 연두색 */
        }

        body { 
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif; 
            background: var(--bg); margin: 0; display: flex; justify-content: center; color: #1e293b;
        }

        .app-container { width: 100%; max-width: 500px; min-height: 100vh; background: var(--card); position: relative; padding-bottom: 40px; box-shadow: 0 0 20px rgba(0,0,0,0.05); }

        /* 헤더 */
        .top-bar { display: flex; justify-content: space-between; align-items: center; padding: 20px; border-bottom: 1px solid #eee; position: sticky; top: 0; background: #fff; z-index: 100; }
        .top-bar h2 { margin: 0; font-size: 1.1rem; font-weight: 800; color: var(--primary); }

        /* 섹션 */
        .section { padding: 15px 20px; }
        .card { background: #f8fafc; border-radius: 16px; padding: 15px; border: 1px solid #f1f5f9; }
        .section-title { font-size: 1rem; font-weight: bold; margin-bottom: 12px; display: flex; justify-content: space-between; align-items: center; }

        /* 달력 */
        .calendar-grid { display: grid; grid-template-columns: repeat(7, 1fr); gap: 6px; text-align: center; }
        .day-label { font-size: 0.7rem; color: #94a3b8; font-weight: bold; padding-bottom: 5px; }
        .day-cell { aspect-ratio: 1/1.2; border-radius: 12px; display: flex; flex-direction: column; align-items: center; justify-content: center; cursor: pointer; transition: 0.2s; border: 2px solid transparent; }
        .day-cell.selected { border-color: var(--primary); background: #fff; }
        .day-num { font-size: 0.9rem; font-weight: 500; }
        .day-pct { font-size: 0.65rem; font-weight: 800; margin-top: 2px; }

        /* 그래프 */
        .chart-wrapper { height: 160px; width: 100%; }

        /* 체크리스트 */
        .routine-item { display: flex; align-items: center; padding: 14px; background: #fff; border-radius: 12px; margin-bottom: 8px; border: 1px solid #f1f5f9; box-shadow: 0 2px 4px rgba(0,0,0,0.02); }
        .routine-item input { width: 22px; height: 22px; margin-right: 15px; accent-color: var(--primary); cursor: pointer; }
        .completed { opacity: 0.5; background: #f8fafc; }
        .completed span { text-decoration: line-through; color: #94a3b8; }

        /* 설정 화면 */
        #settings-overlay { position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: #fff; z-index: 1000; display: none; padding: 20px; box-sizing: border-box; overflow-y: auto; }
        .settings-header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 25px; border-bottom: 1px solid #eee; padding-bottom: 15px; }
        .color-dot { width: 35px; height: 35px; border-radius: 50%; cursor: pointer; border: 3px solid transparent; transition: 0.2s; }
        .color-dot:hover { transform: scale(1.1); }
        .input-group { margin-bottom: 12px; }
        .input-group label { display: block; font-size: 0.85rem; margin-bottom: 5px; color: #64748b; font-weight: 600; }
        .input-group input { width: 100%; padding: 12px; border: 1px solid #e2e8f0; border-radius: 10px; box-sizing: border-box; font-size: 0.9rem; }
        .btn-save { background: var(--primary); color: #fff; border: none; padding: 16px; width: 100%; border-radius: 12px; font-weight: bold; margin-top: 20px; font-size: 1rem; cursor: pointer; }
    </style>
</head>
<body>

<div class="app-container">
    <div class="top-bar">
        <button onclick="changeMonth(-1)" style="background:none; border:none; cursor:pointer; font-size:1.2rem;">◀</button>
        <h2 id="month-title">2026년 1월</h2>
        <button onclick="changeMonth(1)" style="background:none; border:none; cursor:pointer; font-size:1.2rem;">▶</button>
        <button onclick="openSettings()" style="background:none; border:none; font-size: 1.3rem; cursor:pointer;">⚙️</button>
    </div>

    <div class="section">
        <div class="calendar-grid" id="calendar-grid"></div>
    </div>

    <div class="section">
        <div class="card">
            <div style="font-size: 0.85rem; font-weight: bold; margin-bottom: 10px; color: #64748b;">주간 성취 추세</div>
            <div class="chart-wrapper"><canvas id="weeklyChart"></canvas></div>
        </div>
    </div>

    <div class="section">
        <div class="section-title">
            <span id="selected-date-text">오늘의 루틴</span>
        </div>
        <div id="routine-list"></div>
    </div>
</div>

<div id="settings-overlay">
    <div class="settings-header">
        <h2 style="margin:0;">Settings</h2>
        <button onclick="closeSettings()" style="background:none; border:none; font-size: 1.8rem; cursor:pointer;">&times;</button>
    </div>

    <div class="input-group">
        <label>테마 포인트 컬러</label>
        <div style="display: flex; gap: 12px; margin-top: 10px;">
            <div class="color-dot" style="background:#2563eb;" onclick="setTheme('#2563eb')"></div>
            <div class="color-dot" style="background:#7c3aed;" onclick="setTheme('#7c3aed')"></div>
            <div class="color-dot" style="background:#0891b2;" onclick="setTheme('#0891b2')"></div>
            <div class="color-dot" style="background:#db2777;" onclick="setTheme('#db2777')"></div>
            <div class="color-dot" style="background:#1e293b;" onclick="setTheme('#1e293b')"></div>
        </div>
    </div>

    <div class="input-group" style="margin-top: 30px;">
        <label>매일 목표 (10가지)</label>
        <div id="routine-inputs"></div>
    </div>

    <button class="btn-save" onclick="saveAllSettings()">설정 저장 및 적용</button>
</div>

<script>
    let viewDate = new Date();
    let selectedDateStr = new Date().toISOString().split('T')[0];
    let myChart;
    
    // 데이터 로드
    let myRoutines = JSON.parse(localStorage.getItem('myRoutines')) || ["운동", "아침 루틴", "30분 독서", "물 2L 마시기", "영양제 섭취", "명상", "외국어 공부", "일기 기록", "스트레칭", "취침 시간 준수"];
    let themeColor = localStorage.getItem('themeColor') || '#2563eb';

    function applyTheme() {
        document.documentElement.style.setProperty('--primary', themeColor);
        if(myChart) {
            myChart.data.datasets[0].borderColor = themeColor;
            myChart.data.datasets[0].backgroundColor = themeColor + '15';
            myChart.update();
        }
    }

    function init() {
        applyTheme();
        renderCalendar();
        renderRoutines();
        initChart();
        renderRoutineInputs();
    }

    // 달력 렌더링
    function renderCalendar() {
        const grid = document.getElementById('calendar-grid');
        grid.innerHTML = '';
        const year = viewDate.getFullYear();
        const month = viewDate.getMonth();
        document.getElementById('month-title').innerText = `${year}년 ${month + 1}월`;

        ['일','월','화','수','목','금','토'].forEach(d => grid.innerHTML += `<div class="day-label">${d}</div>`);
        const firstDay = new Date(year, month, 1).getDay();
        const lastDate = new Date(year, month + 1, 0).getDate();

        for(let i=0; i<firstDay; i++) grid.innerHTML += `<div></div>`;
        for(let d=1; d<=lastDate; d++) {
            const dStr = `${year}-${String(month+1).padStart(2,'0')}-${String(d).padStart(2,'0')}`;
            const isSelected = dStr === selectedDateStr ? 'selected' : '';
            
            const data = JSON.parse(localStorage.getItem(dStr)) || new Array(10).fill(false);
            const pct = (data.filter(v => v).length / 10) * 100;
            const pctColor = pct > 0 ? (pct < 50 ? 'var(--success-low)' : 'var(--success-high)') : 'transparent';

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

    function renderRoutines() {
        const list = document.getElementById('routine-list');
        document.getElementById('selected-date-text').innerText = `${selectedDateStr} 루틴`;
        const data = JSON.parse(localStorage.getItem(selectedDateStr)) || new Array(10).fill(false);
        list.innerHTML = myRoutines.map((r, i) => `
            <div class="routine-item ${data[i] ? 'completed' : ''}">
                <input type="checkbox" ${data[i] ? 'checked' : ''} onchange="toggleTask(${i})">
                <span>${r}</span>
            </div>
        `).join('');
    }

    function toggleTask(idx) {
        const data = JSON.parse(localStorage.getItem(selectedDateStr)) || new Array(10).fill(false);
        data[idx] = !data[idx];
        localStorage.setItem(selectedDateStr, JSON.stringify(data));
        renderRoutines();
        renderCalendar();
        updateChart();
    }

    // 차트 로직
    function initChart() {
        const ctx = document.getElementById('weeklyChart').getContext('2d');
        myChart = new Chart(ctx, {
            type: 'line',
            data: {
                labels: ['월','화','수','목','금','토','일'],
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
                    x: { grid: { display: false }, ticks: { font: { size: 10 } } }
                } 
            }
        });
    }

    function updateChart() {
        myChart.data.datasets[0].data = getWeeklyScores();
        myChart.update();
    }

    function getWeeklyScores() {
        const curr = new Date(selectedDateStr);
        const day = curr.getDay();
        const diff = curr.getDate() - day + (day === 0 ? -6 : 1);
        const monday = new Date(curr.setDate(diff));
        
        return Array.from({length: 7}, (_, i) => {
            const d = new Date(new Date(monday).setDate(monday.getDate() + i)).toISOString().split('T')[0];
            const data = JSON.parse(localStorage.getItem(d)) || [];
            return (data.filter(v => v).length / 10) * 100;
        });
    }

    // 설정 제어
    function openSettings() { 
        renderRoutineInputs();
        document.getElementById('settings-overlay').style.display = 'block'; 
    }
    function closeSettings() { document.getElementById('settings-overlay').style.display = 'none'; }
    function setTheme(color) { themeColor = color; applyTheme(); }
    function renderRoutineInputs() {
        const container = document.getElementById('routine-inputs');
        container.innerHTML = myRoutines.map((r, i) => `
            <div class="input-group"><input type="text" value="${r}" id="edit-routine-${i}"></div>
        `).join('');
    }

    function saveAllSettings() {
        myRoutines = Array.from({length: 10}, (_, i) => document.getElementById(`edit-routine-${i}`).value);
        localStorage.setItem('myRoutines', JSON.stringify(myRoutines));
        localStorage.setItem('themeColor', themeColor);
        renderRoutines();
        renderCalendar();
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
