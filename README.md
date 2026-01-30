<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>nothing 期刊 | 无界之声</title>
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
        }

        [data-theme="dark"] {
            --bg-color: #121212;
            --card-bg: #1e1e1e;
            --text-color: #e0e0e0;
            --accent-color: #ffffff;
            --secondary-text: #a0a0a0;
            --shadow: 0 4px 20px rgba(0,0,0,0.3);
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

        .nav-links button {
            background: none;
            border: none;
            color: var(--secondary-text);
            font-size: 1em;
            margin-left: 20px;
            cursor: pointer;
            transition: var(--transition);
            font-weight: 500;
        }

        .nav-links button:hover, .nav-links button.active {
            color: var(--accent-color);
        }

        .theme-toggle {
            font-size: 1.2em;
            cursor: pointer;
            margin-left: 20px;
        }

        /* 头部 Hero */
        header {
            text-align: center;
            padding: 80px 20px;
            background: linear-gradient(135deg, var(--card-bg) 0%, var(--bg-color) 100%);
        }

        header h1 {
            font-size: 4em;
            margin: 0;
            letter-spacing: -2px;
            color: var(--text-color);
        }

        header p {
            color: var(--secondary-text);
            font-size: 1.2em;
            margin-top: 10px;
        }

        /* 主要内容区域 */
        .container {
            max-width: 800px;
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

        /* 卡片样式 */
        .card {
            background-color: var(--card-bg);
            padding: 30px;
            margin-bottom: 25px;
            border-radius: var(--border-radius);
            box-shadow: var(--shadow);
            border: 1px solid transparent;
            transition: var(--transition);
        }

        .card:hover {
            transform: translateY(-3px);
            border-color: rgba(0,0,0,0.1);
        }

        .article-title {
            font-size: 1.5em;
            font-weight: bold;
            margin-bottom: 10px;
        }

        .article-meta {
            font-size: 0.85em;
            color: var(--secondary-text);
            margin-bottom: 15px;
        }

        /* 表单样式 */
        input, textarea {
            width: 100%;
            padding: 15px;
            margin-bottom: 15px;
            border: 1px solid #ddd;
            border-radius: 8px;
            background-color: var(--bg-color);
            color: var(--text-color);
            box-sizing: border-box;
            font-family: inherit;
            transition: var(--transition);
        }

        input:focus, textarea:focus {
            outline: none;
            border-color: var(--accent-color);
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

        /* 投票条样式 */
        .vote-option {
            margin-bottom: 15px;
            cursor: pointer;
            position: relative;
        }

        .progress-bg {
            background-color: var(--bg-color);
            height: 40px;
            border-radius: 8px;
            overflow: hidden;
            position: relative;
        }

        .progress-fill {
            background-color: #e0e0e0;
            height: 100%;
            width: 0%;
            transition: width 1s ease-out;
        }

        [data-theme="dark"] .progress-fill { background-color: #333; }

        .vote-text {
            position: absolute;
            top: 50%;
            left: 15px;
            transform: translateY(-50%);
            z-index: 2;
            pointer-events: none;
            display: flex;
            justify-content: space-between;
            width: 90%;
        }

        /* 评论样式 */
        .comment-item {
            border-bottom: 1px solid rgba(0,0,0,0.05);
            padding: 15px 0;
            display: flex;
            gap: 10px;
        }
        
        .avatar {
            width: 40px;
            height: 40px;
            background-color: var(--secondary-text);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
            font-size: 0.8em;
        }

        footer {
            text-align: center;
            padding: 40px;
            color: var(--secondary-text);
            font-size: 0.9em;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* 响应式 */
        @media (max-width: 600px) {
            header h1 { font-size: 2.5em; }
            .nav-links { display: none; } /* 简化处理，移动端隐藏导航 */
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
        </div>
        <div class="theme-toggle" onclick="toggleTheme()">🌓</div>
    </nav>

    <header>
        <h1>nothing 期刊</h1>
        <p>没有标准答案，只有真实声音。</p>
    </header>

    <div class="container">
        
        <div id="home" class="section active">
            <div id="article-feed">
                </div>
        </div>

        <div id="write" class="section">
            <div class="card">
                <h2>发布你的思想</h2>
                <p style="color:var(--secondary-text)">无需审核，即刻生成。在这里，你是自由的。</p>
                <form id="submissionForm">
                    <input type="text" id="articleTitle" placeholder="标题（也许不需要标题）" required>
                    <input type="text" id="articleAuthor" placeholder="笔名" required>
                    <textarea id="articleContent" rows="8" placeholder="在这里写下你的随笔、故事或仅仅是此刻的情绪..." required></textarea>
                    <button type="submit" class="primary-btn">发布文章</button>
                </form>
            </div>
        </div>

        <div id="community" class="section">
            <div class="card">
                <h2>本周议题</h2>
                <p>你认为 “nothing” 代表着什么？</p>
                <div id="voteArea">
                    <div class="vote-option" onclick="castVote(0)">
                        <div class="progress-bg"><div class="progress-fill" id="fill-0"></div></div>
                        <div class="vote-text"><span>一种虚无主义</span> <span id="percent-0"></span></div>
                    </div>
                    <div class="vote-option" onclick="castVote(1)">
                        <div class="progress-bg"><div class="progress-fill" id="fill-1"></div></div>
                        <div class="vote-text"><span>无限的可能性</span> <span id="percent-1"></span></div>
                    </div>
                    <div class="vote-option" onclick="castVote(2)">
                        <div class="progress-bg"><div class="progress-fill" id="fill-2"></div></div>
                        <div class="vote-text"><span>拒绝被定义</span> <span id="percent-2"></span></div>
                    </div>
                </div>
            </div>

            <div class="card">
                <h2>公共留言墙</h2>
                <div id="commentsList">
                    </div>
                <form id="commentForm" style="margin-top: 20px;">
                    <div style="display:flex; gap:10px;">
                        <input type="text" id="commenterName" placeholder="昵称" style="width:30%;" required>
                        <input type="text" id="commentText" placeholder="留下一句话..." required>
                    </div>
                    <button type="submit" class="primary-btn">发送留言</button>
                </form>
            </div>
        </div>

    </div>

    <footer>
        <p>&copy; 2026 nothing 期刊 | 由代码构建的虚空</p>
    </footer>

    <script>
        // 1. 初始化数据
        const initialArticles = [
            {
                title: "关于发呆的艺术",
                author: "匿名观察者",
                content: "在这个快节奏的时代，什么都不做变成了一种奢侈。昨天下午我盯着墙上的光斑看了整整一个小时，那是我这周最充实的时刻。",
                date: "2026-01-30"
            },
            {
                title: "为什么我们害怕沉默？",
                author: "Philosopher_K",
                content: "对话中的停顿总是让人尴尬，但恰恰是在那些停顿里，真实的思考正在发生。nothing 并不是空无，而是等待被填满的空间。",
                date: "2026-01-29"
            }
        ];

        // 2. 页面加载时渲染
        window.onload = function() {
            renderArticles();
            loadComments();
        };

        // 3. 渲染文章列表函数
        function renderArticles() {
            const feed = document.getElementById('article-feed');
            feed.innerHTML = ''; // 清空
            
            initialArticles.forEach(article => {
                const card = document.createElement('div');
                card.className = 'card';
                card.innerHTML = `
                    <div class="article-title">${article.title}</div>
                    <div class="article-meta">作者: ${article.author} | 时间: ${article.date}</div>
                    <p>${article.content}</p>
                `;
                feed.appendChild(card);
            });
        }

        // 4. 切换标签页 (Tab Switching)
        function switchTab(tabId) {
            // 隐藏所有板块
            document.querySelectorAll('.section').forEach(el => el.classList.remove('active'));
            document.querySelectorAll('.nav-links button').forEach(el => el.classList.remove('active'));
            
            // 显示目标板块
            document.getElementById(tabId).classList.add('active');
            document.getElementById('btn-' + tabId).classList.add('active');
        }

        // 5. 处理投稿 (模拟后端)
        document.getElementById('submissionForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            const newArticle = {
                title: document.getElementById('articleTitle').value,
                author: document.getElementById('articleAuthor').value,
                content: document.getElementById('articleContent').value,
                date: new Date().toISOString().split('T')[0]
            };

            // 添加到数组开头
            initialArticles.unshift(newArticle);
            
            // 重新渲染
            renderArticles();
            
            // 切换回主页并清空表单
            switchTab('home');
            e.target.reset();
            alert('投稿成功！你的声音已被收录。');
        });

        // 6. 投票逻辑
        let votes = [12, 45, 23]; // 模拟初始票数
        function castVote(index) {
            votes[index]++;
            const total = votes.reduce((a, b) => a + b, 0);
            
            votes.forEach((count, i) => {
                const percent = Math.round((count / total) * 100);
                document.getElementById(`fill-${i}`).style.width = percent + "%";
                document.getElementById(`percent-${i}`).innerText = percent + "%";
            });
        }

        // 7. 留言墙逻辑
        function loadComments() {
            const list = document.getElementById('commentsList');
            // 预置一条评论
            if(list.children.length === 0) {
                addCommentToDom("NothingBot", "欢迎来到这里，留下你的痕迹。");
            }
        }

        document.getElementById('commentForm').addEventListener('submit', function(e) {
            e.preventDefault();
            const name = document.getElementById('commenterName').value;
            const text = document.getElementById('commentText').value;
            
            addCommentToDom(name, text);
            e.target.reset();
        });

        function addCommentToDom(name, text) {
            const list = document.getElementById('commentsList');
            const item = document.createElement('div');
            item.className = 'comment-item';
            // 生成随机颜色头像
            const color = '#' + Math.floor(Math.random()*16777215).toString(16);
            
            item.innerHTML = `
                <div class="avatar" style="background-color:${color}">${name[0].toUpperCase()}</div>
                <div>
                    <div style="font-weight:bold; font-size:0.9em">${name}</div>
                    <div style="font-size:0.95em">${text}</div>
                </div>
            `;
            list.prepend(item); // 最新消息在最上面
        }

        // 8. 深色模式切换
        function toggleTheme() {
            const body = document.body;
            const currentTheme = body.getAttribute('data-theme');
            if (currentTheme === 'dark') {
                body.removeAttribute('data-theme');
            } else {
                body.setAttribute('data-theme', 'dark');
            }
        }
    </script>
</body>
</html>
