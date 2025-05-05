<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>绥棱县第六中学 四年十一班 成绩生成器</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 40px;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
        }
        table, th, td {
            border: 1px solid black;
        }
        th, td {
            padding: 10px;
            text-align: center;
        }
        button {
            padding: 10px 20px;
            font-size: 16px;
            background-color: #4CAF50;
            color: white;
            border: none;
            cursor: pointer;
        }
        button:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>

    <h1>绥棱县第六中学 四年十一班 成绩生成器</h1>
    <p>设计者：Ront</p>
    <button onclick="generateGrades()">生成成绩</button>
    
    <table id="gradesTable">
        <thead>
            <tr>
                <th>学生姓名</th>
                <th>数学</th>
                <th>语文</th>
                <th>英语</th>
                <th>物理</th>
                <th>化学</th>
            </tr>
        </thead>
        <tbody>
        </tbody>
    </table>

    <script>
        // 只有指定的学生名字
        const validStudents = ["贾雨萌", "荣佳晋", "冯祥瑞"];

        // 生成成绩
        function generateGrades() {
            const tableBody = document.querySelector("#gradesTable tbody");
            tableBody.innerHTML = '';  // 清空表格内容

            // 只生成指定学生的成绩
            validStudents.forEach(student => {
                const row = document.createElement("tr");
                row.innerHTML = `
                    <td>${student}</td>
                    <td>${getRandomGrade()}</td>
                    <td>${getRandomGrade()}</td>
                    <td>${getRandomGrade()}</td>
                    <td>${getRandomGrade()}</td>
                    <td>${getRandomGrade()}</td>
                `;
                tableBody.appendChild(row);
            });
        }

        // 随机生成成绩
        function getRandomGrade() {
            return Math.floor(Math.random() * 101);  // 随机生成0-100的成绩
        }
    </script>

</body>
</html>
