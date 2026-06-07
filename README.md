# Shadow

<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>CHEESE 인트라넷</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:'Segoe UI',sans-serif;
}

body{
    display:flex;
    background:#111827;
    color:white;
}

.sidebar{
    width:250px;
    height:100vh;
    background:#1f2937;
    padding:20px;
}

.logo{
    font-size:24px;
    font-weight:bold;
    margin-bottom:30px;
    text-align:center;
}

.menu button{
    width:100%;
    padding:12px;
    margin-bottom:10px;
    border:none;
    border-radius:10px;
    background:#374151;
    color:white;
    cursor:pointer;
    font-size:15px;
}

.menu button:hover{
    background:#4b5563;
}

.main{
    flex:1;
    padding:30px;
}

.page{
    display:none;
}

.page.active{
    display:block;
}

.card-container{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(220px,1fr));
    gap:20px;
}

.card{
    background:#1f2937;
    padding:20px;
    border-radius:15px;
}

.card h2{
    font-size:15px;
    color:#9ca3af;
}

.card h1{
    margin-top:10px;
}

table{
    width:100%;
    margin-top:20px;
    border-collapse:collapse;
    background:#1f2937;
    border-radius:15px;
    overflow:hidden;
}

th{
    background:#374151;
}

th,td{
    padding:15px;
    text-align:left;
}
</style>
</head>

<body>

<div class="sidebar">

    <div class="logo">🏢 CHEESE</div>

    <div class="menu">
        <button onclick="showPage('dashboard')">🏠 대시보드</button>
        <button onclick="showPage('members')">👥 조직원</button>
        <button onclick="showPage('money')">💰 자금관리</button>
        <button onclick="showPage('reports')">📝 보고서</button>
        <button onclick="showPage('settings')">⚙️ 설정</button>
    </div>

</div>

<div class="main">

    <!-- 대시보드 -->
    <div id="dashboard" class="page active">

        <h1>대시보드</h1>

        <br>

        <div class="card-container">

            <div class="card">
                <h2>총 조직원</h2>
                <h1>0명</h1>
            </div>

            <div class="card">
                <h2>조직 자금</h2>
                <h1>₩0</h1>
            </div>

            <div class="card">
                <h2>이번 주 수익</h2>
                <h1>₩0</h1>
            </div>

        </div>

    </div>

    <!-- 조직원 -->
    <div id="members" class="page">

        <h1>조직원 관리</h1>

        <table>
            <tr>
                <th>닉네임</th>
                <th>직급</th>
                <th>활동횟수</th>
                <th>경고</th>
            </tr>

            <tr>
                <td>CHEESE</td>
                <td>대표이사</td>
                <td>0</td>
                <td>0</td>
            </tr>

            <tr>
                <td>홍길동</td>
                <td>부장</td>
                <td>0</td>
                <td>0</td>
            </tr>
        </table>

    </div>

    <!-- 자금 -->
    <div id="money" class="page">

        <h1>자금 관리</h1>

        <table>
            <tr>
                <th>날짜</th>
                <th>내용</th>
                <th>금액</th>
            </tr>

            <tr>
                <td>2026-06-06</td>
                <td>조직 수익</td>
                <td>₩0</td>
            </tr>
        </table>

    </div>

    <!-- 보고서 -->
    <div id="reports" class="page">

        <h1>보고서</h1>

        <table>
            <tr>
                <th>작성자</th>
                <th>제목</th>
                <th>날짜</th>
            </tr>

            <tr>
                <td>MOCHI</td>
                <td>주간 활동 보고서</td>
                <td>2026-06-06</td>
            </tr>
        </table>

    </div>

    <!-- 설정 -->
    <div id="settings" class="page">

        <h1>설정</h1>

        <p>관리자 설정 페이지</p>

    </div>

</div>

<script>
function showPage(pageId){

    const pages = document.querySelectorAll('.page');

    pages.forEach(page=>{
        page.classList.remove('active');
    });

    document.getElementById(pageId).classList.add('active');
}
</script>

</body>
</html>
