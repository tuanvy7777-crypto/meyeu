<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>8/3 Cho Mẹ</title>

<audio id="bg-music" loop>
<source src="mp3.mp4" type="audio/mpeg">
</audio>

<style>
body{
margin:0;
font-family:Arial
}

/* ===== LOGIN ===== */
#login{
position:fixed;
top:0;
left:0;
width:100%;
height:100%;
background:#0a0a0a;
color:white;
display:flex;
justify-content:center;
align-items:center;
z-index:10;
}

.box{
background:rgba(255,255,255,0.1);
padding:30px;
border-radius:20px;
text-align:center;
}

.numpad{
display:grid;
grid-template-columns:repeat(3,60px);
gap:10px;
margin-top:10px;
}

.numpad button{
width:60px;
height:60px;
border:none;
border-radius:50%;
background:rgba(255,255,255,0.2);
color:white;
font-size:20px;
cursor:pointer;
}

/* ===== MAIN PAGE ===== */
#main{
display:none;
background:#fff0f5;
min-height:100vh;
text-align:center;
padding:30px;
}

.container{
display:flex;
justify-content:center;
gap:40px;
flex-wrap:wrap;
margin-top:20px;
}

.card{
width:180px;
height:230px;
background:white;
border-radius:15px;
box-shadow:0 6px 15px rgba(0,0,0,0.2);
cursor:pointer;
transition:0.3s;
}

.card:hover{
transform:scale(1.05)
}

.card img{
width:100%;
height:140px;
object-fit:cover
}

.card p{
font-weight:bold;
color:#ff1493
}

.wish{
max-width:700px;
margin:30px auto;
font-size:20px;
color:#333;
line-height:1.6;
}
</style>
</head>
<body>

<!-- LOGIN -->
<div id="login">
<div class="box">
<h3>Nhập mật khẩu</h3>
<div id="display" style="height:30px;margin-bottom:10px;"></div>

<div class="numpad">
<button onclick="press(1)">1</button>
<button onclick="press(2)">2</button>
<button onclick="press(3)">3</button>
<button onclick="press(4)">4</button>
<button onclick="press(5)">5</button>
<button onclick="press(6)">6</button>
<button onclick="press(7)">7</button>
<button onclick="press(8)">8</button>
<button onclick="press(9)">9</button>
<button onclick="clearPass()">X</button>
<button onclick="press(0)">0</button>
<button onclick="check()">✓</button>
</div>
</div>
</div>

<!-- MAIN PAGE -->
<div id="main">
<h1>🌸 Chúc Mừng ngày 8/3 của Mẹ 🌸</h1>

<div class="container">

<div class="card" onclick="alert('8/3 này con chúc mẹ luôn mạnh khỏe và hạnh phúc. Con cảm ơn mẹ vì tất cả những gì mẹ đã hy sinh cho con. Hiện tại con chưa làm được nhiều, nhưng sau này con nhất định sẽ thành công để bù đắp cho mẹ. ❤️')">
<img src="anh1.jpg">
<p>Món quà 1</p>
</div>

<div class="card" onclick="location.href='heart.html'">
<img src="anh2.jpg">
<p>Món quà 2</p>
</div>

<div class="card" onclick="location.href='galaxy.html'">
<img src="anh3.jpg">
<p>Món quà 3</p>
</div>

</div>
</div>

<script>
let input=""
const pass="0803"
const display=document.getElementById("display")

/* ===== KIỂM TRA TRẠNG THÁI LOGIN KHI LOAD ===== */
window.addEventListener("DOMContentLoaded",function(){
if(sessionStorage.getItem("loggedIn")==="true"){
document.getElementById("login").style.display="none"
document.getElementById("main").style.display="block"
}
})

function press(n){
if(input.length<4){
input+=n
display.innerText="*".repeat(input.length)
}
}

function clearPass(){
input=""
display.innerText=""
}

function check(){
if(input===pass){
sessionStorage.setItem("loggedIn","true")
document.getElementById("login").style.display="none"
document.getElementById("main").style.display="block"
}else{
alert("Sai mật khẩu")
clearPass()
}
}

/* autoplay fix */
document.addEventListener("click",function(){
document.getElementById("bg-music").play()
},{once:true})
</script>

</body>
</html>
