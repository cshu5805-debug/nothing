<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>nothing  | 无界之声</title>
    <style>
        :root {
            --bg-color: #f4f4f4;
            --card-bg: #ffffff;
            --text-color: #333333;
            --accent-color: #000000;
            --secondary-text: #666666;
            --border-radius: 12px;
            --shadow: 0 4px 20px rgba(0,0,0,0.05);
            --transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
            --highlight: #ffeb3b;
        }

        [data-theme="dark"] {
            --bg-color: #121212;
            --card-bg: #1e1e1e;
            --text-color: #e0e0e0;
            --accent-color: #ffffff;
            --secondary-text: #a0a0a0;
            --shadow: 0 4px 20px rgba(0,0,0,0.3);
            --highlight: #ffc107;
        }

        * {
            box-sizing: border-box;
        }

        body {
            font-family: 'Helvetica Neue', Arial, sans-serif;
            background-color: var(--bg-color);
            color: var(--text-color);
            margin: 0;
            padding: 0;
            line-height: 1.6;
            transition: var(--transition);
        }

        /* 导航栏 */
        nav {
            background-color: var(--card-bg);
            padding: 15px 30px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 2px 10px rgba(0,0,0,0.05);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .nav-logo {
            font-weight: 900;
            font-size: 1.5em;
            letter-spacing: -1px;
            color: var(--text-color);
        }

        .nav-links {
            display: flex;
            gap: 10px;
        }

        .nav-links button {
            background: none;
            border: none;
            color: var(--secondary-text);
            font-size: 1em;
            padding: 8px 16px;
            cursor: pointer;
            transition: var(--transition);
            font-weight: 500;
            border-radius: 20px;
        }

        .nav-links button:hover, .nav-links button.active {
            color: var(--accent-color);
            background-color: var(--bg-color);
        }

        .theme-toggle {
            font-size: 1.2em;
            cursor: pointer;
            margin-left: 20px;
            padding: 8px;
            border-radius: 50%;
            transition: var(--transition);
        }

        .theme-toggle:hover {
            background-color: var(--bg-color);
        }

        /* 头部 Hero */
        header {
            text-align: center;
            padding: 80px 20px;
            background: linear-gradient(135deg, var(--card-bg) 0%, var(--bg-color) 100%);
            position: relative;
            overflow: hidden;
        }

        header h1 {
            font-size: 4em;
            margin: 0;
            letter-spacing: -2px;
            color: var(--text-color);
            animation: fadeInDown 0.8s ease;
        }

        header p {
            color: var(--secondary-text);
            font-size: 1.2em;
            margin-top: 10px;
            animation: fadeInUp 0.8s ease 0.2s backwards;
        }

        .header-stats {
            display: flex;
            justify-content: center;
            gap: 40px;
            margin-top: 30px;
            animation: fadeInUp 0.8s ease 0.4s backwards;
        }

        .stat-item {
            text-align: center;
        }

        .stat-number {
            font-size: 2em;
            font-weight: bold;
            color: var(--accent-color);
        }

        .stat-label {
            font-size: 0.9em;
            color: var(--secondary-text);
        }

        /* 主要内容区域 */
        .container {
            max-width: 900px;
            margin: 0 auto;
            padding: 20px;
            min-height: 60vh;
        }

        .section {
            display: none;
            animation: fadeIn 0.5s ease;
        }

        .section.active {
            display: block;
        }

        /* 搜索和过滤 */
        .search-bar {
            margin-bottom: 20px;
            display: flex;
            gap: 10px;
            align-items: center;
        }

        .search-bar input {
            flex: 1;
            padding: 12px 20px;
            border: 1px solid #ddd;
            border-radius: 25px;
            background-color: var(--card-bg);
            color: var(--text-color);
            font-size: 1em;
        }

        .filter-tags {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
            margin-bottom: 20px;
        }

        .tag {
            padding: 6px 16px;
            background-color: var(--bg-color);
            border: 1px solid var(--secondary-text);
            border-radius: 20px;
            font-size: 0.85em;
            cursor: pointer;
            transition: var(--transition);
        }

        .tag:hover, .tag.active {
            background-color: var(--accent-color);
            color: var(--card-bg);
            border-color: var(--accent-color);
        }

        /* 卡片样式 */
        .card {
            background-color: var(--card-bg);
            padding: 30px;
            margin-bottom: 25px;
            border-radius: var(--border-radius);
            box-shadow: var(--shadow);
            border: 1px solid transparent;
            transition: var(--transition);
            position: relative;
        }

        .card:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 25px rgba(0,0,0,0.1);
        }

        .article-header {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            margin-bottom: 15px;
        }

        .article-title {
            font-size: 1.5em;
            font-weight: bold;
            margin-bottom: 5px;
            cursor: pointer;
            transition: var(--transition);
        }

        .article-title:hover {
            color: var(--accent-color);
        }

        .article-meta {
            font-size: 0.85em;
            color: var(--secondary-text);
            margin-bottom: 15px;
            display: flex;
            gap: 15px;
            flex-wrap: wrap;
        }

        .article-actions {
            display: flex;
            gap: 15px;
            margin-top: 15px;
            padding-top: 15px;
            border-top: 1px solid rgba(0,0,0,0.05);
        }

        .action-btn {
            background: none;
            border: none;
            color: var(--secondary-text);
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 5px;
            font-size: 0.9em;
            transition: var(--transition);
        }

        .action-btn:hover {
            color: var(--accent-color);
        }

        .action-btn.liked {
            color: #e91e63;
        }

        /* 表单样式 */
        input, textarea, select {
            width: 100%;
            padding: 15px;
            margin-bottom: 15px;
            border: 1px solid #ddd;
            border-radius: 8px;
            background-color: var(--bg-color);
            color: var(--text-color);
            font-family: inherit;
            transition: var(--transition);
            font-size: 1em;
        }

        input:focus, textarea:focus, select:focus {
            outline: none;
            border-color: var(--accent-color);
            box-shadow: 0 0 0 3px rgba(0,0,0,0.05);
        }

        button.primary-btn {
            background-color: var(--accent-color);
            color: var(--card-bg);
            padding: 12px 30px;
            border: none;
            border-radius: 30px;
            font-size: 1em;
            cursor: pointer;
            transition: var(--transition);
            width: 100%;
            font-weight: bold;
        }

        button.primary-btn:hover {
            opacity: 0.8;
            transform: scale(0.98);
        }

        button.primary-btn:active {
            transform: scale(0.95);
        }

        /* 标签选择 */
        .tag-selector {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
            margin-bottom: 15px;
        }

        .tag-selector .tag {
            cursor: pointer;
        }

        /* 投票条样式 */
        .vote-option {
            margin-bottom: 15px;
            cursor: pointer;
            position: relative;
            transition: var(--transition);
        }

        .vote-option:hover {
            transform: translateX(5px);
        }

        .progress-bg {
            background-color: var(--bg-color);
            height: 50px;
            border-radius: 8px;
            overflow: hidden;
            position: relative;
            border: 1px solid rgba(0,0,0,0.05);
        }

        .progress-fill {
            background: linear-gradient(90deg, var(--accent-color) 0%, rgba(0,0,0,0.3) 100%);
            height: 100%;
            width: 0%;
            transition: width 1s ease-out;
        }

        .vote-text {
            position: absolute;
            top: 50%;
            left: 15px;
            transform: translateY(-50%);
            z-index: 2;
            pointer-events: none;
            display: flex;
            justify-content: space-between;
            width: calc(100% - 30px);
            font-weight: 500;
        }

        .vote-count {
            font-size: 0.85em;
            color: var(--secondary-text);
        }

        /* 评论样式 */
        .comment-item {
            border-bottom: 1px solid rgba(0,0,0,0.05);
            padding: 15px 0;
            display: flex;
            gap: 15px;
            animation: slideIn 0.3s ease;
        }
        
        .avatar {
            width: 45px;
            height: 45px;
            background-color: var(--secondary-text);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
            font-size: 0.9em;
            flex-shrink: 0;
        }

        .comment-content {
            flex: 1;
        }

        .comment-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 5px;
        }

        .comment-author {
            font-weight: bold;
            font-size: 0.95em;
        }

        .comment-time {
            font-size: 0.8em;
            color: var(--secondary-text);
        }

        /* 随机名言 */
        .quote-box {
            background: linear-gradient(135deg, var(--accent-color) 0%, #333 100%);
            color: white;
            padding: 40px;
            border-radius: var(--border-radius);
            text-align: center;
            margin-bottom: 25px;
            cursor: pointer;
            transition: var(--transition);
        }

        .quote-box:hover {
            transform: scale(1.02);
        }

        .quote-text {
            font-size: 1.3em;
            font-style: italic;
            margin-bottom: 10px;
            line-height: 1.5;
        }

        .quote-author {
            font-size: 0.9em;
            opacity: 0.8;
        }

        /* 阅读统计 */
        .reading-stats {
            background-color: var(--bg-color);
            padding: 20px;
            border-radius: 8px;
            margin-bottom: 20px;
        }

        .stat-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 15px;
            margin-top: 15px;
        }

        .stat-card {
            background-color: var(--card-bg);
            padding: 15px;
            border-radius: 8px;
            text-align: center;
        }

        /* 情绪标签 */
        .mood-selector {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
            margin-bottom: 15px;
        }

        .mood-emoji {
            font-size: 2em;
            cursor: pointer;
            padding: 10px;
            border-radius: 50%;
            transition: var(--transition);
            border: 2px solid transparent;
        }

        .mood-emoji:hover, .mood-emoji.selected {
            background-color: var(--bg-color);
            border-color: var(--accent-color);
            transform: scale(1.2);
        }

        /* 加载动画 */
        .loading {
            text-align: center;
            padding: 40px;
            color: var(--secondary-text);
        }

        .loading::after {
            content: '...';
            animation: dots 1.5s infinite;
        }

        /* 空状态 */
        .empty-state {
            text-align: center;
            padding: 60px 20px;
            color: var(--secondary-text);
        }

        .empty-state-icon {
            font-size: 4em;
            margin-bottom: 20px;
            opacity: 0.5;
        }

        /* Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0,0,0,0.7);
            z-index: 2000;
            align-items: center;
            justify-content: center;
            animation: fadeIn 0.3s ease;
        }

        .modal.active {
            display: flex;
        }

        .modal-content {
            background-color: var(--card-bg);
            padding: 40px;
            border-radius: var(--border-radius);
            max-width: 600px;
            width: 90%;
            max-height: 80vh;
            overflow-y: auto;
            position: relative;
            animation: slideUp 0.3s ease;
        }

        .modal-close {
            position: absolute;
            top: 15px;
            right: 15px;
            font-size: 1.5em;
            cursor: pointer;
            color: var(--secondary-text);
            transition: var(--transition);
        }

        .modal-close:hover {
            color: var(--accent-color);
        }

        footer {
            text-align: center;
            padding: 40px;
            color: var(--secondary-text);
            font-size: 0.9em;
            border-top: 1px solid rgba(0,0,0,0.05);
            margin-top: 40px;
        }

        /* 动画 */
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes fadeInDown {
            from { opacity: 0; transform: translateY(-20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes slideIn {
            from { opacity: 0; transform: translateX(-20px); }
            to { opacity: 1; transform: translateX(0); }
        }

        @keyframes slideUp {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes dots {
            0%, 20% { content: '.'; }
            40% { content: '..'; }
            60%, 100% { content: '...'; }
        }

        /* 响应式 */
        @media (max-width: 768px) {
            header h1 { font-size: 2.5em; }
            .header-stats { flex-direction: column; gap: 20px; }
            .nav-links { display: none; }
            .container { padding: 10px; }
            .card { padding: 20px; }
            .search-bar { flex-direction: column; }
        }
    </style>
</head>
<body>

    <nav>
        <div class="nav-logo">nothing.</div>
        <div class="nav-links">
            <button onclick="switchTab('home')" class="active" id="btn-home">阅读</button>
            <button onclick="switchTab('write')" id="btn-write">投稿</button>
            <button onclick="switchTab('community')" id="btn-community">社区</button>
            <button onclick="switchTab('discover')" id="btn-discover">发现</button>
        </div>
        <div class="theme-toggle" onclick="toggleTheme()">🌓</div>
    </nav>

    <header>
        <h1>nothing 期刊</h1>
        <p>没有标准答案，只有真实声音。</p>
        <div class="header-stats">
            <div class="stat-item">
                <div class="stat-number" id="totalArticles">0</div>
                <div class="stat-label">篇文章</div>
            </div>
            <div class="stat-item">
                <div class="stat-number" id="totalReaders">1,247</div>
                <div class="stat-label">位读者</div>
            </div>
            <div class="stat-item">
                <div class="stat-number" id="totalWords">0</div>
                <div class="stat-label">个文字</div>
            </div>
        </div>
    </header>

    <div class="container">
        
        <!-- 阅读页面 -->
        <div id="home" class="section active">
            <div class="search-bar">
                <input type="text" id="searchInput" placeholder="🔍 搜索文章标题、作者或内容..." onkeyup="searchArticles()">
            </div>
            
            <div class="filter-tags" id="filterTags"></div>
            
            <div id="article-feed"></div>
        </div>

        <!-- 投稿页面 -->
        <div id="write" class="section">
            <div class="card">
                <h2>✍️ 发布你的思想</h2>
                <p style="color:var(--secondary-text)">无需审核，即刻生成。在这里，你是自由的。</p>
                
                <form id="submissionForm">
                    <input type="text" id="articleTitle" placeholder="标题（也许不需要标题）" required>
                    <input type="text" id="articleAuthor" placeholder="笔名" required>
                    
                    <label style="display:block; margin-bottom:10px; color:var(--secondary-text);">选择文章类型：</label>
                    <select id="articleCategory">
                        <option value="随笔">随笔</option>
                        <option value="故事">故事</option>
                        <option value="诗歌">诗歌</option>
                        <option value="思考">思考</option>
                        <option value="日记">日记</option>
                        <option value="其他">其他</option>
                    </select>
                    
                    <label style="display:block; margin-bottom:10px; color:var(--secondary-text);">此刻的心情：</label>
                    <div class="mood-selector">
                        <span class="mood-emoji" data-mood="开心" onclick="selectMood(this)">😊</span>
                        <span class="mood-emoji" data-mood="平静" onclick="selectMood(this)">😌</span>
                        <span class="mood-emoji" data-mood="思考" onclick="selectMood(this)">🤔</span>
                        <span class="mood-emoji" data-mood="忧郁" onclick="selectMood(this)">😔</span>
                        <span class="mood-emoji" data-mood="愤怒" onclick="selectMood(this)">😠</span>
                        <span class="mood-emoji" data-mood="惊讶" onclick="selectMood(this)">😲</span>
                    </div>
                    <input type="hidden" id="articleMood" value="平静">
                    
                    <textarea id="articleContent" rows="10" placeholder="在这里写下你的随笔、故事或仅仅是此刻的情绪..." required></textarea>
                    
                    <div style="display:flex; gap:10px;">
                        <button type="submit" class="primary-btn">📮 发布文章</button>
                    </div>
                </form>
            </div>

            <!-- 写作提示 -->
            <div class="card">
                <h3>💡 写作灵感</h3>
                <p id="writingPrompt" style="font-style:italic; color:var(--secondary-text); cursor:pointer;" onclick="generatePrompt()">
                    点击获取随机写作提示...
                </p>
            </div>
        </div>

        <!-- 社区页面 -->
        <div id="community" class="section">
            <div class="card">
                <h2>📊 本周议题</h2>
                <p>你认为 "nothing" 代表着什么？</p>
                <div id="voteArea">
                    <div class="vote-option" onclick="castVote(0)">
                        <div class="progress-bg">
                            <div class="progress-fill" id="fill-0"></div>
                            <div class="vote-text">
                                <span>一种虚无主义</span> 
                                <span><span id="percent-0">0%</span> <span class="vote-count" id="count-0">(0票)</span></span>
                            </div>
                        </div>
                    </div>
                    <div class="vote-option" onclick="castVote(1)">
                        <div class="progress-bg">
                            <div class="progress-fill" id="fill-1"></div>
                            <div class="vote-text">
                                <span>无限的可能性</span>
                                <span><span id="percent-1">0%</span> <span class="vote-count" id="count-1">(0票)</span></span>
                            </div>
                        </div>
                    </div>
                    <div class="vote-option" onclick="castVote(2)">
                        <div class="progress-bg">
                            <div class="progress-fill" id="fill-2"></div>
                            <div class="vote-text">
                                <span>拒绝被定义</span>
                                <span><span id="percent-2">0%</span> <span class="vote-count" id="count-2">(0票)</span></span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <div class="card">
                <h2>💬 公共留言墙</h2>
                <div id="commentsList"></div>
                <form id="commentForm" style="margin-top: 20px;">
                    <div style="display:flex; gap:10px;">
                        <input type="text" id="commenterName" placeholder="昵称" style="width:30%; margin-bottom:0;" required>
                        <input type="text" id="commentText" placeholder="留下一句话..." style="margin-bottom:0;" required>
                    </div>
                    <button type="submit" class="primary-btn" style="margin-top:15px;">💬 发送留言</button>
                </form>
            </div>
        </div>

        <!-- 发现页面 -->
        <div id="discover" class="section">
            <div class="quote-box" onclick="generateQuote()">
                <div class="quote-text" id="quoteText">"沉默有时是最响亮的回答。"</div>
                <div class="quote-author" id="quoteAuthor">— 点击更换名言</div>
            </div>

            <div class="card">
                <h2>📈 阅读统计</h2>
                <div class="stat-grid">
                    <div class="stat-card">
                        <div style="font-size:1.5em; font-weight:bold;" id="readingTime">0</div>
                        <div style="font-size:0.85em; color:var(--secondary-text);">分钟阅读</div>
                    </div>
                    <div class="stat-card">
                        <div style="font-size:1.5em; font-weight:bold;" id="articlesRead">0</div>
                        <div style="font-size:0.85em; color:var(--secondary-text);">篇已读</div>
                    </div>
                    <div class="stat-card">
                        <div style="font-size:1.5em; font-weight:bold;" id="likesGiven">0</div>
                        <div style="font-size:0.85em; color:var(--secondary-text);">个赞</div>
                    </div>
                    <div class="stat-card">
                        <div style="font-size:1.5em; font-weight:bold;" id="commentsCount">0</div>
                        <div style="font-size:0.85em; color:var(--secondary-text);">条评论</div>
                    </div>
                </div>
            </div>

            <div class="card">
                <h2>🏆 热门作者</h2>
                <div id="topAuthors"></div>
            </div>

            <div class="card">
                <h2>🎯 编辑推荐</h2>
                <p style="color:var(--secondary-text);">精选本周最佳文章</p>
                <div id="editorPicks"></div>
            </div>
        </div>

    </div>

    <!-- Modal for full article -->
    <div id="articleModal" class="modal">
        <div class="modal-content">
            <span class="modal-close" onclick="closeModal()">&times;</span>
            <div id="modalArticleContent"></div>
        </div>
    </div>

    <footer>
        <p>&copy; 2026 nothing  | 由代码构建的虚空</p>
        <p style="margin-top:10px; font-size:0.85em;">在这里，每个声音都值得被听见 🎭</p>
    </footer>

    <script>
        // ============= 数据初始化 =============
        let articles = [
            {
                id: 1,
                title: "关于发呆的艺术",
                author: "匿名观察者",
                content: "在这个快节奏的时代，什么都不做变成了一种奢侈。昨天下午我盯着墙上的光斑看了整整一个小时，那是我这周最充实的时刻。我们总是被告知要高效、要生产力最大化，但有时候，最大的生产力就是允许自己什么都不做。发呆不是浪费时间，而是让大脑重启的必要过程。",
                date: "2026-01-30",
                category: "随笔",
                mood: "平静",
                likes: 23,
                comments: [],
                views: 156
            },
            {
                id: 2,
                title: "为什么我们害怕沉默？",
                author: "Philosopher_K",
                content: "对话中的停顿总是让人尴尬，但恰恰是在那些停顿里，真实的思考正在发生。nothing 并不是空无，而是等待被填满的空间。我们的社会教会我们害怕沉默，因为沉默意味着未知，而未知让我们不安。但如果我们学会拥抱沉默，我们会发现那里藏着最真实的自己。",
                date: "2026-01-29",
                category: "思考",
                mood: "思考",
                likes: 45,
                comments: [],
                views: 234
            },
            {
                id: 3,
                title: "深夜食堂的故事",
                author: "夜行者",
                content: "凌晨三点，街角的小店还亮着灯。老板娘永远不问你为什么这么晚还不回家，只是默默端上一碗热腾腾的面。有些温暖不需要言语，just nothing but presence。",
                date: "2026-01-28",
                category: "故事",
                mood: "温暖",
                likes: 67,
                comments: [],
                views: 321
            }
        ];

        let votes = [12, 45, 23];
        let selectedMood = "平静";
        let userStats = {
            readingTime: 0,
            articlesRead: 0,
            likesGiven: 0,
            commentsCount: 0
        };

        const categories = ["全部", "随笔", "故事", "诗歌", "思考", "日记", "其他"];
        const quotes = [
            { text: "沉默有时是最响亮的回答。", author: "萨特" },
            { text: "我思故我在，但有时不思也是一种存在。", author: "笛卡尔(改)" },
            { text: "空无不是虚无，而是无限可能的起点。", author: "老子" },
            { text: "当你凝视深渊时，深渊也在凝视你。", author: "尼采" },
            { text: "最深刻的话语往往是未说出口的。", author: "海明威" },
            { text: "留白是艺术中最重要的部分。", author: "佚名" }
        ];

        const writingPrompts = [
            "写下你今天遇到的一个陌生人的故事",
            "如果可以对10年前的自己说一句话...",
            "描述一个让你感到平静的瞬间",
            "你最近一次哭是因为什么？",
            "写一封永远不会寄出的信",
            "你觉得什么是真正的自由？",
            "描述一个反复出现在梦中的场景",
            "如果明天是世界末日，你会做什么？"
        ];

        // ============= 初始化函数 =============
        window.onload = function() {
            renderArticles();
            renderFilterTags();
            loadComments();
            updateStats();
            updateVotes();
            loadUserStats();
            generateQuote();
            generatePrompt();
        };

        // ============= 文章相关 =============
        function renderArticles(filter = "全部") {
            const feed = document.getElementById('article-feed');
            feed.innerHTML = '';
            
            let filteredArticles = filter === "全部" ? articles : articles.filter(a => a.category === filter);
            
            if (filteredArticles.length === 0) {
                feed.innerHTML = `
                    <div class="empty-state">
                        <div class="empty-state-icon">📭</div>
                        <p>暂无此类文章，来写第一篇吧！</p>
                    </div>
                `;
                return;
            }
            
            filteredArticles.forEach(article => {
                const card = document.createElement('div');
                card.className = 'card';
                card.innerHTML = `
                    <div class="article-header">
                        <div>
                            <div class="article-title" onclick="openArticle(${article.id})">${article.title}</div>
                            <div class="article-meta">
                                <span>✍️ ${article.author}</span>
                                <span>📅 ${article.date}</span>
                                <span>📁 ${article.category}</span>
                                <span>${getMoodEmoji(article.mood)} ${article.mood}</span>
                                <span>👁️ ${article.views} 阅读</span>
                            </div>
                        </div>
                    </div>
                    <p>${article.content.substring(0, 150)}${article.content.length > 150 ? '...' : ''}</p>
                    <div class="article-actions">
                        <button class="action-btn" onclick="likeArticle(${article.id}, event)">
                            <span>❤️</span> <span id="likes-${article.id}">${article.likes}</span>
                        </button>
                        <button class="action-btn" onclick="openArticle(${article.id})">
                            <span>💬</span> ${article.comments.length} 评论
                        </button>
                        <button class="action-btn" onclick="shareArticle(${article.id})">
                            <span>🔗</span> 分享
                        </button>
                    </div>
                `;
                feed.appendChild(card);
            });
        }

        function renderFilterTags() {
            const container = document.getElementById('filterTags');
            container.innerHTML = '';
            
            categories.forEach(cat => {
                const tag = document.createElement('span');
                tag.className = 'tag' + (cat === '全部' ? ' active' : '');
                tag.textContent = cat;
                tag.onclick = () => {
                    document.querySelectorAll('.filter-tags .tag').forEach(t => t.classList.remove('active'));
                    tag.classList.add('active');
                    renderArticles(cat);
                };
                container.appendChild(tag);
            });
        }

        function searchArticles() {
            const query = document.getElementById('searchInput').value.toLowerCase();
            const feed = document.getElementById('article-feed');
            feed.innerHTML = '';
            
            const results = articles.filter(a => 
                a.title.toLowerCase().includes(query) ||
                a.author.toLowerCase().includes(query) ||
                a.content.toLowerCase().includes(query)
            );
            
            if (results.length === 0) {
                feed.innerHTML = `
                    <div class="empty-state">
                        <div class="empty-state-icon">🔍</div>
                        <p>没有找到相关文章</p>
                    </div>
                `;
                return;
            }
            
            results.forEach(article => {
                const card = document.createElement('div');
                card.className = 'card';
                card.innerHTML = `
                    <div class="article-title" onclick="openArticle(${article.id})">${article.title}</div>
                    <div class="article-meta">
                        <span>✍️ ${article.author}</span>
                        <span>📅 ${article.date}</span>
                        <span>📁 ${article.category}</span>
                    </div>
                    <p>${article.content.substring(0, 150)}...</p>
                `;
                feed.appendChild(card);
            });
        }

        function openArticle(id) {
            const article = articles.find(a => a.id === id);
            if (!article) return;
            
            article.views++;
            userStats.articlesRead++;
            saveUserStats();
            
            const modal = document.getElementById('articleModal');
            const content = document.getElementById('modalArticleContent');
            
            content.innerHTML = `
                <h1>${article.title}</h1>
                <div class="article-meta">
                    <span>✍️ ${article.author}</span>
                    <span>📅 ${article.date}</span>
                    <span>📁 ${article.category}</span>
                    <span>${getMoodEmoji(article.mood)} ${article.mood}</span>
                    <span>👁️ ${article.views} 阅读</span>
                </div>
                <div style="margin: 30px 0; line-height: 2; font-size: 1.1em;">
                    ${article.content.replace(/\n/g, '<br>')}
                </div>
                <div class="article-actions">
                    <button class="action-btn ${article.liked ? 'liked' : ''}" onclick="likeArticle(${article.id}, event)">
                        <span>❤️</span> <span id="modal-likes-${article.id}">${article.likes}</span>
                    </button>
                    <button class="action-btn" onclick="shareArticle(${article.id})">
                        <span>🔗</span> 分享
                    </button>
                </div>
                <hr style="margin: 30px 0;">
                <h3>💬 评论区</h3>
                <div id="articleComments"></div>
            `;
            
            modal.classList.add('active');
        }

        function closeModal() {
            document.getElementById('articleModal').classList.remove('active');
        }

        function likeArticle(id, event) {
            const article = articles.find(a => a.id === id);
            if (!article) return;
            
            const btn = event.currentTarget;
            if (btn.classList.contains('liked')) {
                article.likes--;
                btn.classList.remove('liked');
                userStats.likesGiven--;
            } else {
                article.likes++;
                btn.classList.add('liked');
                userStats.likesGiven++;
            }
            
            document.getElementById(`likes-${id}`).textContent = article.likes;
            const modalLikes = document.getElementById(`modal-likes-${id}`);
            if (modalLikes) modalLikes.textContent = article.likes;
            
            saveUserStats();
        }

        function shareArticle(id) {
            const article = articles.find(a => a.id === id);
            alert(`📋 已复制分享链接：\n"${article.title}" by ${article.author}`);
        }

        // ============= 投稿相关 =============
        document.getElementById('submissionForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            const newArticle = {
                id: articles.length + 1,
                title: document.getElementById('articleTitle').value,
                author: document.getElementById('articleAuthor').value,
                content: document.getElementById('articleContent').value,
                date: new Date().toISOString().split('T')[0],
                category: document.getElementById('articleCategory').value,
                mood: document.getElementById('articleMood').value,
                likes: 0,
                comments: [],
                views: 0
            };

            articles.unshift(newArticle);
            renderArticles();
            updateStats();
            
            switchTab('home');
            e.target.reset();
            document.querySelectorAll('.mood-emoji').forEach(m => m.classList.remove('selected'));
            
            alert('🎉 投稿成功！你的声音已被收录。');
        });

        function selectMood(elem) {
            document.querySelectorAll('.mood-emoji').forEach(m => m.classList.remove('selected'));
            elem.classList.add('selected');
            document.getElementById('articleMood').value = elem.dataset.mood;
        }

        function generatePrompt() {
            const prompt = writingPrompts[Math.floor(Math.random() * writingPrompts.length)];
            document.getElementById('writingPrompt').textContent = `💡 ${prompt}`;
        }

        // ============= 投票相关 =============
        function castVote(index) {
            votes[index]++;
            updateVotes();
        }

        function updateVotes() {
            const total = votes.reduce((a, b) => a + b, 0);
            
            votes.forEach((count, i) => {
                const percent = total > 0 ? Math.round((count / total) * 100) : 0;
                document.getElementById(`fill-${i}`).style.width = percent + "%";
                document.getElementById(`percent-${i}`).innerText = percent + "%";
                document.getElementById(`count-${i}`).innerText = `(${count}票)`;
            });
        }

        // ============= 评论相关 =============
        function loadComments() {
            const list = document.getElementById('commentsList');
            if(list.children.length === 0) {
                addCommentToDom("NothingBot", "欢迎来到这里，留下你的痕迹。🌟");
            }
        }

        document.getElementById('commentForm').addEventListener('submit', function(e) {
            e.preventDefault();
            const name = document.getElementById('commenterName').value;
            const text = document.getElementById('commentText').value;
            
            addCommentToDom(name, text);
            userStats.commentsCount++;
            saveUserStats();
            e.target.reset();
        });

        function addCommentToDom(name, text) {
            const list = document.getElementById('commentsList');
            const item = document.createElement('div');
            item.className = 'comment-item';
            const color = '#' + Math.floor(Math.random()*16777215).toString(16);
            const time = new Date().toLocaleTimeString('zh-CN', { hour: '2-digit', minute: '2-digit' });
            
            item.innerHTML = `
                <div class="avatar" style="background-color:${color}">${name[0].toUpperCase()}</div>
                <div class="comment-content">
                    <div class="comment-header">
                        <span class="comment-author">${name}</span>
                        <span class="comment-time">${time}</span>
                    </div>
                    <div>${text}</div>
                </div>
            `;
            list.prepend(item);
        }

        // ============= 发现页相关 =============
        function generateQuote() {
            const quote = quotes[Math.floor(Math.random() * quotes.length)];
            document.getElementById('quoteText').textContent = `"${quote.text}"`;
            document.getElementById('quoteAuthor').textContent = `— ${quote.author}`;
        }

        function updateStats() {
            const totalWords = articles.reduce((sum, a) => sum + a.content.length, 0);
            document.getElementById('totalArticles').textContent = articles.length;
            document.getElementById('totalWords').textContent = totalWords.toLocaleString();
        }

        function loadUserStats() {
            const saved = localStorage.getItem('nothingUserStats');
            if (saved) {
                userStats = JSON.parse(saved);
            }
            updateUserStats();
        }

        function saveUserStats() {
            localStorage.setItem('nothingUserStats', JSON.stringify(userStats));
            updateUserStats();
        }

        function updateUserStats() {
            document.getElementById('readingTime').textContent = userStats.readingTime;
            document.getElementById('articlesRead').textContent = userStats.articlesRead;
            document.getElementById('likesGiven').textContent = userStats.likesGiven;
            document.getElementById('commentsCount').textContent = userStats.commentsCount;
            
            // 更新热门作者
            const authorCounts = {};
            articles.forEach(a => {
                authorCounts[a.author] = (authorCounts[a.author] || 0) + 1;
            });
            
            const topAuthorsHtml = Object.entries(authorCounts)
                .sort((a, b) => b[1] - a[1])
                .slice(0, 5)
                .map(([ author, count], index) => `
                    <div style="padding: 10px 0; border-bottom: 1px solid rgba(0,0,0,0.05);">
                        <span style="font-size:1.2em; margin-right:10px;">${['🥇', '🥈', '🥉', '4️⃣', '5️⃣'][index]}</span>
                        <strong>${author}</strong> - ${count} 篇文章
                    </div>
                `).join('');
            
            document.getElementById('topAuthors').innerHTML = topAuthorsHtml;
            
            // 更新编辑推荐
            const editorPicks = articles
                .sort((a, b) => b.likes - a.likes)
                .slice(0, 3)
                .map(article => `
                    <div style="padding: 15px 0; border-bottom: 1px solid rgba(0,0,0,0.05); cursor: pointer;" onclick="openArticle(${article.id})">
                        <div style="font-weight: bold; margin-bottom: 5px;">📌 ${article.title}</div>
                        <div style="font-size: 0.85em; color: var(--secondary-text);">
                            ${article.author} · ❤️ ${article.likes} · 👁️ ${article.views}
                        </div>
                    </div>
                `).join('');
            
            document.getElementById('editorPicks').innerHTML = editorPicks;
        }

        // ============= 工具函数 =============
        function switchTab(tabId) {
            document.querySelectorAll('.section').forEach(el => el.classList.remove('active'));
            document.querySelectorAll('.nav-links button').forEach(el => el.classList.remove('active'));
            
            document.getElementById(tabId).classList.add('active');
            const btn = document.getElementById('btn-' + tabId);
            if (btn) btn.classList.add('active');
        }

        function toggleTheme() {
            const body = document.body;
            const currentTheme = body.getAttribute('data-theme');
            if (currentTheme === 'dark') {
                body.removeAttribute('data-theme');
                localStorage.setItem('theme', 'light');
            } else {
                body.setAttribute('data-theme', 'dark');
                localStorage.setItem('theme', 'dark');
            }
        }

        function getMoodEmoji(mood) {
            const moodMap = {
                '开心': '😊',
                '平静': '😌',
                '思考': '🤔',
                '忧郁': '😔',
                '愤怒': '😠',
                '惊讶': '😲',
                '温暖': '🤗'
            };
            return moodMap[mood] || '😌';
        }

        // 加载主题
        const savedTheme = localStorage.getItem('theme');
        if (savedTheme === 'dark') {
            document.body.setAttribute('data-theme', 'dark');
        }

        // 模拟阅读时间增加
        setInterval(() => {
            if (document.getElementById('home').classList.contains('active')) {
                userStats.readingTime++;
                saveUserStats();
            }
        }, 60000); // 每分钟增加

        // 点击模态框外部关闭
        document.getElementById('articleModal').addEventListener('click', function(e) {
            if (e.target === this) {
                closeModal();
            }
        });
    </script>
</body>
</html>
