# nothing 期刊
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>nothing 期刊</title>
    <style>
        /* 基本的页面样式 */
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f9f9f9;
            color: #333;
            margin: 0;
            padding: 0;
            line-height: 1.6;
        }

        header {
            background-color: #333;
            color: white;
            text-align: center;
            padding: 20px;
        }

        h1 {
            margin: 0;
            font-size: 3em;
        }

        /* 页面主要内容 */
        .content {
            max-width: 900px;
            margin: 30px auto;
            padding: 20px;
            background-color: white;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            border-radius: 8px;
        }

        p {
            font-size: 1.2em;
            line-height: 1.8;
        }

        /* 文章和链接的样式 */
        a {
            color: #007bff;
            text-decoration: none;
        }

        a:hover {
            text-decoration: underline;
        }

        footer {
            text-align: center;
            padding: 10px;
            background-color: #333;
            color: white;
            position: fixed;
            bottom: 0;
            width: 100%;
        }

        /* 响应式设计 */
        @media (max-width: 768px) {
            h1 {
                font-size: 2.5em;
            }

            .content {
                padding: 15px;
            }

            p {
                font-size: 1.1em;
            }
        }
    </style>
</head>
<body>

    <header>
        <h1>nothing 期刊</h1>
        <p>没有标准答案，只有真实声音。</p>
    </header>

    <div class="content">
        <h2>欢迎来到 nothing 期刊</h2>
        <p>在这里，你可以表达任何想法，无论是随笔、故事、哲学讨论，还是感悟。</p>
        <p>我们鼓励自由、独立的思想。大家的声音，才是我们期刊的精髓。</p>

        <h3>如何投稿？</h3>
        <p>如果你想分享你的思想，只需联系管理员，我们会安排你发表文章。每篇文章将会有独立的页面，供你表达自我。</p>

        <h3>我们的目标</h3>
        <p>nothing 期刊的目标是提供一个平台，让每个人都有机会发表自己的声音。没有界限，只有无限的可能。</p>

        <p><a href="#">了解更多</a></p>
    </div>

    <footer>
        <p>&copy; 2026 nothing 期刊 | 由您和我一起创造</p>
    </footer>

</body>
</html>
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>nothing 期刊</title>
    <style>
        /* 基本的页面样式 */
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f9f9f9;
            color: #333;
            margin: 0;
            padding: 0;
            line-height: 1.6;
        }

        header {
            background-color: #333;
            color: white;
            text-align: center;
            padding: 20px;
        }

        h1 {
            margin: 0;
            font-size: 3em;
        }

        /* 页面主要内容 */
        .content {
            max-width: 900px;
            margin: 30px auto;
            padding: 20px;
            background-color: white;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            border-radius: 8px;
        }

        p {
            font-size: 1.2em;
            line-height: 1.8;
        }

        /* 表单样式 */
        .submit-form {
            background-color: #f1f1f1;
            padding: 20px;
            border-radius: 8px;
            margin-top: 30px;
        }

        input, textarea {
            width: 100%;
            padding: 10px;
            margin-bottom: 15px;
            border-radius: 5px;
            border: 1px solid #ddd;
        }

        button {
            background-color: #007bff;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        button:hover {
            background-color: #0056b3;
        }

        /* 响应式设计 */
        @media (max-width: 768px) {
            h1 {
                font-size: 2.5em;
            }

            .content {
                padding: 15px;
            }

            p {
                font-size: 1.1em;
            }
        }
    </style>
</head>
<body>

    <header>
        <h1>nothing 期刊</h1>
        <p>没有标准答案，只有真实声音。</p>
    </header>

    <div class="content">
        <h2>欢迎来到 nothing 期刊</h2>
        <p>在这里，你可以表达任何想法，无论是随笔、故事、哲学讨论，还是感悟。</p>
        <p>我们鼓励自由、独立的思想。大家的声音，才是我们期刊的精髓。</p>

        <h3>如何投稿？</h3>
        <p>如果你想分享你的思想，只需填写下面的表单，我们会安排你发表文章。每篇文章将会有独立的页面，供你表达自我。</p>

        <div class="submit-form">
            <h3>投稿表单</h3>
            <form action="submit_article.php" method="POST">
                <input type="text" name="title" placeholder="文章标题" required>
                <textarea name="content" rows="5" placeholder="请输入文章内容" required></textarea>
                <button type="submit">提交文章</button>
            </form>
        </div>
    </div>

    <footer>
        <p>&copy; 2026 nothing 期刊 | 由您和我一起创造</p>
    </footer>

</body>
</html>
<!-- 在每篇文章下面增加评论功能 -->
<div class="comments-section">
    <h3>评论区</h3>
    <form id="commentForm">
        <input type="text" id="commenterName" placeholder="你的名字" required>
        <textarea id="commentText" rows="4" placeholder="你的评论..." required></textarea>
        <button type="submit">发表评论</button>
    </form>
    
    <div id="commentsList">
        <!-- 评论会显示在这里 -->
    </div>
</div>

<script>
    document.getElementById('commentForm').addEventListener('submit', function(e) {
        e.preventDefault();

        const name = document.getElementById('commenterName').value;
        const comment = document.getElementById('commentText').value;

        const commentBox = document.createElement('div');
        commentBox.classList.add('comment-box');
        commentBox.innerHTML = `<strong>${name}</strong>: <p>${comment}</p>`;

        document.getElementById('commentsList').appendChild(commentBox);

        // 清空表单
        document.getElementById('commenterName').value = '';
        document.getElementById('commentText').value = '';
    });
</script>
<div class="vote-section">
    <h3>你的意见</h3>
    <p>你认为 “nothing 期刊” 更偏向于哪个方向？</p>
    <form id="voteForm">
        <label>
            <input type="radio" name="vote" value="思想/随笔"> 思想/随笔
        </label><br>
        <label>
            <input type="radio" name="vote" value="吐槽/日记"> 吐槽/日记
        </label><br>
        <label>
            <input type="radio" name="vote" value="哲学/艺术"> 哲学/艺术
        </label><br>
        <button type="submit">提交投票</button>
    </form>

    <div id="voteResult"></div>
</div>

<script>
    document.getElementById('voteForm').addEventListener('submit', function(e) {
        e.preventDefault();
        const vote = document.querySelector('input[name="vote"]:checked');
        if (vote) {
            document.getElementById('voteResult').innerHTML = `感谢您的投票，您选择了：${vote.value}`;
        } else {
            document.getElementById('voteResult').innerHTML = '请先选择一个选项！';
        }
    });
</script>
/* 滚动动画效果 */
@keyframes fadeIn {
    0% { opacity: 0; }
    100% { opacity: 1; }
}

.content {
    animation: fadeIn 1s ease-in-out;
}
