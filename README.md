from pathlib import Path

html = r'''<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Happy Birthday Madhu 🎂</title>
<style>
*{box-sizing:border-box}
html,body{margin:0;width:100%;height:100%;overflow:hidden;font-family:Arial,sans-serif}
body{
  display:flex;align-items:center;justify-content:center;
  background:linear-gradient(135deg,#ff9a9e,#fad0c4,#a18cd1,#fbc2eb);
  background-size:400% 400%;animation:bg 12s ease infinite;
}
@keyframes bg{0%{background-position:0 50%}50%{background-position:100% 50%}100%{background-position:0 50%}}
.card{
  width:min(90%,600px);padding:45px 25px;text-align:center;
  border-radius:30px;background:rgba(255,255,255,.18);
  backdrop-filter:blur(14px);border:1px solid rgba(255,255,255,.4);
  box-shadow:0 20px 60px rgba(0,0,0,.2);color:white;z-index:5;
}
h1{font-size:clamp(42px,10vw,78px);margin:0 0 15px;text-shadow:0 5px 20px rgba(0,0,0,.2)}
h2{font-size:clamp(28px,7vw,48px);margin:0 0 20px}
p{font-size:20px;line-height:1.6;margin:10px}
.cake{font-size:75px;animation:bounce 1.5s infinite}
@keyframes bounce{50%{transform:translateY(-12px)}}
.balloon{position:absolute;bottom:-130px;font-size:55px;animation:float linear infinite}
.b1{left:8%;animation-duration:9s}.b2{left:25%;animation-duration:12s;animation-delay:2s}
.b3{left:70%;animation-duration:10s;animation-delay:1s}.b4{left:88%;animation-duration:13s;animation-delay:3s}
@keyframes float{to{transform:translateY(-120vh) rotate(12deg)}}
button{
  border:0;border-radius:30px;padding:14px 28px;font-size:17px;
  color:#9b2c64;background:white;cursor:pointer;margin-top:18px;
  box-shadow:0 8px 20px rgba(0,0,0,.15)
}
#msg{display:none;margin-top:20px;font-size:20px}
.confetti{position:absolute;top:-20px;width:9px;height:16px;animation:fall 4s linear infinite}
@keyframes fall{to{transform:translateY(110vh) rotate(720deg)}}
</style>
</head>
<body>
<div class="balloon b1">🎈</div><div class="balloon b2">🎈</div>
<div class="balloon b3">🎈</div><div class="balloon b4">🎈</div>

<div class="card">
  <div class="cake">🎂</div>
  <h1>Happy Birthday</h1>
  <h2>Madhu! 🎉</h2>
  <p>Wishing you a beautiful day filled with happiness, smiles and unforgettable moments. 💖</p>
  <button onclick="showWish()">Open Your Wish 💌</button>
  <div id="msg">May all your dreams come true and may every year bring you more happiness! ✨🥳</div>
</div>

<script>
function showWish(){
  document.getElementById("msg").style.display="block";
  for(let i=0;i<80;i++){
    const c=document.createElement("div"); c.className="confetti";
    c.style.left=Math.random()*100+"vw";
    c.style.animationDelay=Math.random()*2+"s";
    c.style.transform="rotate("+Math.random()*360+"deg)";
    c.style.background=["#fff","#ffd166","#ff6b9a","#7bdff2","#b8f2e6"][Math.floor(Math.random()*5)];
    document.body.appendChild(c);
    setTimeout(()=>c.remove(),5000);
  }
}
</script>
</body>
</html>'''

path = Path("/mnt/data/happy_birthday_madhu.html")
path.write_text(html, encoding="utf-8")
print(f"[Open the Birthday Website](sandbox:{path})")

