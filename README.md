<!DOCTYPE html>
<html lang="hi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=yes">
    <title>UPSC सूरज सिंह - 365 दिन चैलेंज</title>
    
    <!-- Font Awesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    
    <style>
        /* रूट वेरिएबल्स */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', 'Segoe UI', sans-serif;
        }

        body {
            background: linear-gradient(145deg, #f3f6fb 0%, #e9eef5 100%);
            min-height: 100vh;
            padding: 15px;
        }

        /* मेन कंटेनर */
        .container {
            max-width: 1200px;
            margin: 0 auto;
        }

        /* हेडर सेक्शन */
        .header {
            background: linear-gradient(135deg, #1e3c72 0%, #2a5298 100%);
            color: white;
            padding: 25px 20px;
            border-radius: 30px 30px 30px 30px;
            margin-bottom: 25px;
            box-shadow: 0 20px 30px rgba(0,0,0,0.2);
            position: relative;
            overflow: hidden;
        }

        .header::before {
            content: "📚";
            position: absolute;
            right: 20px;
            bottom: 20px;
            font-size: 80px;
            opacity: 0.1;
        }

        .header h1 {
            font-size: 28px;
            margin-bottom: 5px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        .header h2 {
            font-size: 22px;
            margin-bottom: 10px;
            color: #ffd700;
        }

        .date-badge {
            background: rgba(255,255,255,0.2);
            display: inline-block;
            padding: 8px 20px;
            border-radius: 50px;
            font-size: 16px;
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255,255,255,0.3);
        }

        /* डे ट्रैकर */
        .day-tracker {
            background: white;
            border-radius: 60px;
            padding: 10px;
            margin: 15px 0 5px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .day-number {
            background: #1e3c72;
            color: white;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 20px;
            font-weight: bold;
        }

        .day-progress {
            flex: 1;
            height: 10px;
            background: #e0e0e0;
            border-radius: 10px;
            overflow: hidden;
        }

        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, #4CAF50, #8BC34A);
            width: 0%;
            transition: width 0.5s;
        }

        .day-text {
            padding-right: 15px;
            font-weight: bold;
            color: #1e3c72;
        }

        /* ग्रिड सिस्टम */
        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-bottom: 20px;
        }

        /* कार्ड स्टाइल */
        .card {
            background: white;
            border-radius: 30px;
            padding: 20px;
            box-shadow: 0 10px 20px rgba(0,0,0,0.05);
            transition: all 0.3s;
            border: 1px solid rgba(255,255,255,0.8);
            backdrop-filter: blur(10px);
        }

        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 30px rgba(0,0,0,0.1);
        }

        .card-header {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 15px;
            padding-bottom: 10px;
            border-bottom: 2px dashed #e0e0e0;
        }

        .card-header i {
            font-size: 24px;
            width: 40px;
            height: 40px;
            background: linear-gradient(135deg, #1e3c72, #2a5298);
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 15px;
        }

        .card-header h3 {
            flex: 1;
            font-size: 18px;
            color: #1e3c72;
        }

        .card-header span {
            background: #f0f0f0;
            padding: 5px 10px;
            border-radius: 20px;
            font-size: 12px;
            color: #666;
        }

        /* टू-डू लिस्ट */
        .todo-list {
            list-style: none;
        }

        .todo-item {
            display: flex;
            align-items: center;
            gap: 12px;
            padding: 12px 0;
            border-bottom: 1px solid #f0f0f0;
        }

        .todo-item:last-child {
            border-bottom: none;
        }

        .todo-item input[type="checkbox"] {
            width: 22px;
            height: 22px;
            accent-color: #1e3c72;
            cursor: pointer;
        }

        .todo-item label {
            flex: 1;
            font-size: 15px;
            color: #444;
        }

        .todo-item .subject-tag {
            background: #e3f2fd;
            color: #1e3c72;
            padding: 3px 8px;
            border-radius: 15px;
            font-size: 11px;
            font-weight: bold;
        }

        .delete-btn {
            color: #ff4444;
            background: none;
            border: none;
            font-size: 16px;
            cursor: pointer;
            opacity: 0.5;
            transition: opacity 0.3s;
        }

        .delete-btn:hover {
            opacity: 1;
        }

        .add-todo {
            display: flex;
            gap: 10px;
            margin-top: 15px;
        }

        .add-todo input {
            flex: 1;
            padding: 12px 15px;
            border: 1px solid #e0e0e0;
            border-radius: 25px;
            font-size: 14px;
            outline: none;
            transition: border 0.3s;
        }

        .add-todo input:focus {
            border-color: #1e3c72;
        }

        .add-todo button {
            width: 50px;
            height: 50px;
            background: linear-gradient(135deg, #1e3c72, #2a5298);
            color: white;
            border: none;
            border-radius: 25px;
            font-size: 20px;
            cursor: pointer;
            transition: transform 0.3s;
        }

        .add-todo button:hover {
            transform: scale(1.1);
        }

        /* प्रोग्रेस बार */
        .subject-progress {
            margin: 15px 0;
        }

        .subject-item {
            margin-bottom: 15px;
        }

        .subject-info {
            display: flex;
            justify-content: space-between;
            margin-bottom: 5px;
            font-size: 14px;
            color: #444;
        }

        .subject-info span:last-child {
            color: #1e3c72;
            font-weight: bold;
        }

        .progress-bg {
            height: 12px;
            background: #f0f0f0;
            border-radius: 20px;
            overflow: hidden;
        }

        .progress-fill-subject {
            height: 100%;
            background: linear-gradient(90deg, #1e3c72, #2a5298);
            border-radius: 20px;
            width: 0%;
            transition: width 0.5s;
        }

        /* कोट सेक्शन */
        .quote-box {
            text-align: center;
            padding: 10px;
        }

        .quote-text {
            font-size: 18px;
            line-height: 1.6;
            color: #333;
            font-style: italic;
            margin-bottom: 10px;
        }

        .quote-author {
            color: #666;
            font-size: 14px;
        }

        .refresh-quote {
            background: none;
            border: none;
            color: #1e3c72;
            font-size: 20px;
            cursor: pointer;
            margin-top: 10px;
            padding: 5px 15px;
            border-radius: 20px;
            background: #f0f0f0;
        }

        /* न्यूज सेक्शन */
        .news-item {
            padding: 12px 0;
            border-bottom: 1px solid #f0f0f0;
            display: flex;
            gap: 10px;
        }

        .news-cat {
            background: #1e3c72;
            color: white;
            padding: 3px 8px;
            border-radius: 5px;
            font-size: 11px;
            white-space: nowrap;
        }

        .news-title {
            flex: 1;
            color: #444;
            font-size: 14px;
        }

        /* हेल्थ ट्रैकर */
        .health-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 15px;
        }

        .health-item {
            background: #f8f9fa;
            border-radius: 20px;
            padding: 15px;
            text-align: center;
        }

        .health-item i {
            font-size: 24px;
            color: #1e3c72;
            margin-bottom: 5px;
        }

        .health-value {
            font-size: 22px;
            font-weight: bold;
            color: #1e3c72;
            margin: 5px 0;
        }

        .health-unit {
            font-size: 12px;
            color: #666;
        }

        .health-btn {
            background: #1e3c72;
            color: white;
            border: none;
            padding: 5px 15px;
            border-radius: 15px;
            font-size: 12px;
            cursor: pointer;
            margin-top: 5px;
        }

        /* नॉलेज बूस्टर */
        .fact-box {
            background: linear-gradient(135deg, #fff3e0, #ffe0b2);
            border-radius: 20px;
            padding: 20px;
            text-align: center;
            margin: 10px 0;
        }

        .fact-icon {
            font-size: 40px;
            margin-bottom: 10px;
        }

        .fact-text {
            font-size: 16px;
            line-height: 1.5;
            color: #333;
            margin-bottom: 15px;
        }

        .next-fact {
            background: #1e3c72;
            color: white;
            border: none;
            padding: 10px 25px;
            border-radius: 25px;
            font-size: 14px;
            cursor: pointer;
        }

        /* फिजिकल इवोल्यूशन */
        .stats-card {
            background: #1e3c72;
            color: white;
            border-radius: 20px;
            padding: 15px;
            margin: 10px 0;
        }

        .stat-row {
            display: flex;
            justify-content: space-between;
            padding: 8px 0;
        }

        /* बटन */
        .btn-primary {
            background: linear-gradient(135deg, #1e3c72, #2a5298);
            color: white;
            border: none;
            padding: 12px 20px;
            border-radius: 25px;
            font-size: 14px;
            cursor: pointer;
            width: 100%;
            margin-top: 10px;
        }

        /* रिस्पॉन्सिव */
        @media (max-width: 600px) {
            body { padding: 10px; }
            .header h1 { font-size: 24px; }
            .header h2 { font-size: 18px; }
            .grid { grid-template-columns: 1fr; }
        }

        /* एनिमेशन */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .card {
            animation: fadeIn 0.5s ease-out;
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- हेडर सेक्शन -->
        <div class="header">
            <h1>📚 UPSC Clear 1 Year</h1>
            <h2>सूरज सिंह, उत्तराखंड 🇮🇳</h2>
            <div class="date-badge" id="currentDate"></div>
            
            <!-- डे ट्रैकर -->
            <div class="day-tracker">
                <div class="day-number" id="dayCount">1</div>
                <div class="day-progress">
                    <div class="progress-fill" id="dayProgress" style="width: 0.27%"></div>
                </div>
                <div class="day-text" id="dayText">Day 1/365</div>
            </div>
        </div>

        <!-- मेन ग्रिड -->
        <div class="grid">
            <!-- टू-डू लिस्ट कार्ड -->
            <div class="card">
                <div class="card-header">
                    <i class="fas fa-tasks"></i>
                    <h3>आज का टू-डू लिस्ट</h3>
                    <span id="todoDate"></span>
                </div>
                <div class="todo-list" id="todoList">
                    <!-- टास्क यहां जावास्क्रिप्ट से आएंगे -->
                </div>
                <div class="add-todo">
                    <input type="text" id="newTodo" placeholder="नया टास्क लिखें...">
                    <button onclick="addTodo()"><i class="fas fa-plus"></i></button>
                </div>
            </div>

            <!-- सिलेबस प्रोग्रेस कार्ड -->
            <div class="card">
                <div class="card-header">
                    <i class="fas fa-chart-line"></i>
                    <h3>सिलेबस प्रोग्रेस</h3>
                    <span id="progressUpdate"></span>
                </div>
                <div class="subject-progress" id="subjectProgress">
                    <!-- सब्जेक्ट यहां जावास्क्रिप्ट से आएंगे -->
                </div>
                <button class="btn-primary" onclick="updateProgress()">
                    <i class="fas fa-sync-alt"></i> अपडेट प्रोग्रेस
                </button>
            </div>

            <!-- मोटिवेशनल कोट कार्ड -->
            <div class="card">
                <div class="card-header">
                    <i class="fas fa-quote-right"></i>
                    <h3>आज की प्रेरणा</h3>
                    <span>✨ नया</span>
                </div>
                <div class="quote-box" id="quoteBox">
                    <!-- कोट यहां जावास्क्रिप्ट से आएगा -->
                </div>
                <button class="refresh-quote" onclick="newQuote()">
                    <i class="fas fa-sync-alt"></i> नया कोट
                </button>
            </div>

            <!-- डेली न्यूज कार्ड -->
            <div class="card">
                <div class="card-header">
                    <i class="fas fa-newspaper"></i>
                    <h3>मुख्य समाचार</h3>
                    <span id="newsDate"></span>
                </div>
                <div id="newsList">
                    <!-- न्यूज यहां जावास्क्रिप्ट से आएंगे -->
                </div>
                <button class="btn-primary" onclick="refreshNews()">
                    <i class="fas fa-redo-alt"></i> रिफ्रेश न्यूज
                </button>
            </div>

            <!-- हेल्थ ट्रैकर कार्ड -->
            <div class="card">
                <div class="card-header">
                    <i class="fas fa-heartbeat"></i>
                    <h3>हेल्थ ट्रैकर</h3>
                    <span>💪 फिट</span>
                </div>
                <div class="health-grid" id="healthTracker">
                    <!-- हेल्थ आइटम यहां जावास्क्रिप्ट से आएंगे -->
                </div>
            </div>

            <!-- नॉलेज बूस्टर कार्ड -->
            <div class="card">
                <div class="card-header">
                    <i class="fas fa-brain"></i>
                    <h3>नॉलेज बूस्टर</h3>
                    <span>💡 Did You Know?</span>
                </div>
                <div class="fact-box" id="factBox">
                    <!-- फैक्ट यहां जावास्क्रिप्ट से आएगा -->
                </div>
                <button class="next-fact" onclick="nextFact()">
                    <i class="fas fa-forward"></i> अगला फैक्ट
                </button>
            </div>

            <!-- फिजिकल इवोल्यूशन कार्ड -->
            <div class="card">
                <div class="card-header">
                    <i class="fas fa-running"></i>
                    <h3>फिजिकल इवोल्यूशन</h3>
                    <span>📊 ट्रैकर</span>
                </div>
                <div class="stats-card" id="physicalStats">
                    <!-- स्टैट्स यहां जावास्क्रिप्ट से आएंगे -->
                </div>
                <button class="btn-primary" onclick="updateWeight()">
                    <i class="fas fa-weight"></i> वजन अपडेट करें
                </button>
            </div>
        </div>

        <!-- फूटर -->
        <div style="text-align: center; padding: 30px; color: #666; font-size: 14px;">
            <p>© 2024 UPSC Clear 1 Year - सूरज सिंह, उत्तराखंड</p>
            <p>हिंदी मीडियम से UPSC की तैयारी | 365 दिन चैलेंज</p>
            <p>🚀 हर दिन नया अपडेट | 💪 संघर्ष ही सफलता है</p>
        </div>
    </div>

    <!-- जावास्क्रिप्ट -->
    <script>
        // ==================== डेट और टाइम सेटिंग्स ====================
        function updateDateTime() {
            const now = new Date();
            
            // डेट फॉर्मेट
            const options = { 
                weekday: 'long', 
                year: 'numeric', 
                month: 'long', 
                day: 'numeric' 
            };
            document.getElementById('currentDate').innerHTML = 
                `<i class="fas fa-calendar"></i> ${now.toLocaleDateString('hi-IN', options)}`;
            
            // टू-डू डेट
            document.getElementById('todoDate').innerHTML = 
                now.toLocaleDateString('hi-IN', { day: 'numeric', month: 'short' });
            
            // न्यूज डेट
            document.getElementById('newsDate').innerHTML = 
                now.toLocaleDateString('hi-IN', { day: 'numeric', month: 'short' });
            
            // डे काउंट (1 जनवरी से)
            const start = new Date(now.getFullYear(), 0, 1);
            const diff = now - start;
            const oneDay = 1000 * 60 * 60 * 24;
            const dayNumber = Math.floor(diff / oneDay) + 1;
            
            document.getElementById('dayCount').innerHTML = dayNumber;
            document.getElementById('dayText').innerHTML = `Day ${dayNumber}/365`;
            
            const progressPercent = (dayNumber / 365) * 100;
            document.getElementById('dayProgress').style.width = progressPercent + '%';
            
            document.getElementById('progressUpdate').innerHTML = 
                `Day ${dayNumber}`;
        }

        // ==================== टू-डू लिस्ट ====================
        let todos = [];

        function loadTodos() {
            const saved = localStorage.getItem('todos');
            if (saved) {
                todos = JSON.parse(saved);
            } else {
                // डिफॉल्ट टास्क
                todos = [
                    { id: 1, text: 'इतिहास - प्राचीन सभ्यताएं पढ़ें', subject: 'इतिहास', completed: false },
                    { id: 2, text: 'भूगोल - जलवायु अध्याय रिवीजन', subject: 'भूगोल', completed: false },
                    { id: 3, text: 'राजनीति - अनुच्छेद 1-4 याद करें', subject: 'राजनीति', completed: false },
                    { id: 4, text: 'अर्थव्यवस्था - बजट 2024 पढ़ें', subject: 'अर्थव्यवस्था', completed: false },
                ];
            }
            renderTodos();
        }

        function renderTodos() {
            const list = document.getElementById('todoList');
            list.innerHTML = '';
            
            // डेट के हिसाब से फिल्टर (आज की डेट वाले)
            const todayTodos = todos.filter(t => {
                if (!t.date) return true;
                const today = new Date().toDateString();
                return new Date(t.date).toDateString() === today;
            });
            
            (todayTodos.length ? todayTodos : todos).forEach(todo => {
                const item = document.createElement('div');
                item.className = 'todo-item';
                item.innerHTML = `
                    <input type="checkbox" ${todo.completed ? 'checked' : ''} 
                    
