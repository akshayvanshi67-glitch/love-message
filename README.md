# love-message
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>💖 Ishq Message 💖</title>
<link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Poppins:wght@300;400&display=swap" rel="stylesheet">

<style>
body {
    margin:0; font-family:'Poppins',sans-serif;
    background:linear-gradient(135deg,#ff9a9e,#fad0c4);
    min-height:100vh; display:flex; justify-content:center; align-items:center;
    color:white; overflow-x:hidden;
}

.container { text-align:center; width:90%; max-width:750px; padding: 20px 0; }
.hidden { display:none; }

.card {
    background:rgba(255,255,255,0.15); backdrop-filter:blur(12px);
    border-radius:25px; padding:25px; box-shadow:0 0 40px rgba(255,255,255,0.4);
    animation:float 4s ease-in-out infinite; position:relative;
    max-height: 85vh; overflow-y: auto;
}

/* Profile Photo Style */
.profile-pic {
    width: 150px; height: 150px;
    border-radius: 50%; border: 4px solid white;
    margin: 0 auto 15px; display: block;
    object-fit: cover; box-shadow: 0 0 20px rgba(0,0,0,0.2);
}

.card::-webkit-scrollbar { width: 5px; }
.card::-webkit-scrollbar-thumb { background: rgba(255,255,255,0.3); border-radius: 10px; }

@keyframes float { 0%, 100% {transform:translateY(0);} 50% {transform:translateY(-10px);} }

h1 { font-family:'Great Vibes',cursive; font-size:42px; margin-bottom: 15px; }
button { padding:12px 28px; border:none; border-radius:25px; font-size:18px; cursor:pointer; margin:10px; transition: 0.3s; }
.yes { background:#ff4d6d; color:white; }
.no { background:gray; color:white; }

input { padding:10px; border-radius:20px; border:none; outline:none; text-align:center; font-size: 16px; margin-bottom: 10px; }

p { white-space:pre-line; line-height:1.8; font-size:16px; text-align: left; }

.heart { position:fixed; bottom:-20px; font-size:20px; animation:rise 6s linear infinite; z-index: -1; }
@keyframes rise { to {transform:translateY(-110vh); opacity:0;} }

.unlocked-video {
    width: 100%; border-radius: 15px; margin-top: 15px;
}

.whatsapp-link {
    display: inline-block; background: #25D366; color: white;
    padding: 10px 20px; border-radius: 20px; text-decoration: none;
    font-weight: bold; margin-top: 15px;
}
</style>
</head>

<body>

<div class="container" id="pass1">
    <div class="card">
        <h1>🔐 Enter Password</h1>
        <input type="password" id="p1" placeholder="Type password...">
        <br>
        <button class="yes" onclick="check1()">Open</button>
    </div>
</div>

<div class="container hidden" id="q1">
    <div class="card">
        <h1>You really want to read this?</h1>
        <button class="yes" onclick="goQ2()">YES</button>
        <button class="no" onclick="grow(this)">NO</button>
    </div>
</div>

<div class="container hidden" id="q2">
    <div class="card">
        <h1>Are you sure 😊</h1>
        <button class="yes" onclick="showMsg()">YES</button>
        <button class="no" onclick="grow(this)">NO</button>
    </div>
</div>

<div class="container hidden" id="msg">
    <div class="card">
        <img src="https://i.ibb.co/S7m4Z8p/photo.jpg" class="profile-pic" alt="Meenakshi">
        <h1>Ishq Message</h1>
        <p>
        Aaj ak special day hai 💖. Pr mujhe lagta hai mere to har saal ke 365 din .🤔 Tumse ishq karne ke liye bane hai. Pr kisi ne mujhse kaha apne dill❤️ ki baat bta deni chahiye kahi etni derr na ho jaye ki wo insaan kisi or ka ho jaye. To mujhe ye kahna hai jitne tumhe fool 💐pasand hai utni mujhe tum. Jitne tumhe pahad pasand 🏔️hai utni mujhe tum. Main kase batau tum mere liye kya ho sayad tum ye nhi janti ki kisi saksh se mane tumhari cute si video clip 📷li hai jise kam se kam ak dafa dekhta hu to dil ko sukun milta hai .
        
        Main tumhari khush hone ki bajah banna chahta hu . Hasti raho 😀 . smile karti raho🙂. Main hamesha tumhara sath dena chahta hoon.
        </p>
        <h2>I have a video you want to see – Who is she?</h2>
        <button class="yes" onclick="videoPass()">YES</button>
        <br>
        <a href="https://wa.me/919084598604" class="whatsapp-link" target="_blank">📲 Message on WhatsApp</a>
    </div>
</div>

<div class="container hidden" id="pass2">
    <div class="card">
        <h1>tumhe pta hai uska naam</h1>
        <input type="password" id="p2" placeholder="Enter her name...">
        <br>
        <button class="yes" onclick="check2()">Unlock Video</button>
    </div>
</div>

<div class="container hidden" id="videoArea">
    <div class="card">
        <h1>💖 Video for You 💖</h1>
        <video id="myVideo" class="unlocked-video" controls>
            <source src="lv_7597739004963884289_20260208104433.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>
        <br>
        <button class="yes" onclick="location.reload()">Restart</button>
    </div>
</div>

<script>
function check1(){
    if(document.getElementById("p1").value==="Dekhti hu"){
        document.getElementById("pass1").classList.add("hidden");
        document.getElementById("q1").classList.remove("hidden");
    }
}

function goQ2(){
    document.getElementById("q1").classList.add("hidden");
    document.getElementById("q2").classList.remove("hidden");
}

function showMsg(){
    document.getElementById("q2").classList.add("hidden");
    document.getElementById("msg").classList.remove("hidden");
    hearts();
}

function grow(btn){
    let yes = btn.parentElement.querySelector(".yes");
    yes.style.fontSize = (parseInt(window.getComputedStyle(yes).fontSize) + 10) + "px";
}

function videoPass(){
    document.getElementById("msg").classList.add("hidden");
    document.getElementById("pass2").classList.remove("hidden");
}

function check2(){
    if(document.getElementById("p2").value==="Meenakshi"){
        document.getElementById("pass2").classList.add("hidden");
        document.getElementById("videoArea").classList.remove("hidden");
        document.getElementById("myVideo").play();
    }
}

function hearts(){
    setInterval(()=>{
        let h=document.createElement("div");
        h.className="heart"; h.innerHTML="💖";
        h.style.left=Math.random()*100+"vw";
        document.body.appendChild(h);
        setTimeout(()=>h.remove(),7000);
    },400);
}
</script>
</body>
</html>
