# Happy-birthday- <!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Birthday Surprise 🎂</title>

<style>
*{
  box-sizing:border-box;
  margin:0;
  padding:0;
}

body{
  min-height:100vh;
  display:flex;
  justify-content:center;
  align-items:center;
  overflow:hidden;
  font-family:Arial,sans-serif;
  background:linear-gradient(135deg,#ffd6e7,#d8e7ff,#e7d7ff);
}

.card{
  width:min(92%,430px);
  padding:32px 24px;
  text-align:center;
  border-radius:28px;
  background:rgba(255,255,255,.72);
  backdrop-filter:blur(14px);
  box-shadow:0 20px 60px rgba(70,40,100,.22);
  position:relative;
  z-index:2;
}

.emoji{
  font-size:64px;
  animation:bounce 1.8s infinite;
}

h1{
  margin:10px 0;
  color:#6d3fa0;
  font-size:34px;
}

.name{
  display:inline-block;
  min-width:180px;
  margin:8px 0 18px;
  padding:10px 16px;
  border-radius:14px;
  background:#fff;
  color:#ff5f9e;
  font-size:25px;
  font-weight:bold;
}

p{
  color:#555;
  line-height:1.6;
  font-size:16px;
}

button{
  margin-top:24px;
  border:0;
  border-radius:999px;
  padding:14px 25px;
  font-size:16px;
  font-weight:bold;
  color:white;
  cursor:pointer;
  background:linear-gradient(90deg,#ff69a6,#8d6bff);
  box-shadow:0 8px 20px rgba(141,107,255,.3);
}

#surprise{
  display:none;
  margin-top:22px;
  padding:18px;
  border-radius:18px;
  background:#fff;
}

#surprise.show{
  display:block;
  animation:pop .5s ease;
}

/* नीचे आने वाली प्यारी lines */
#birthdayLines{
  display:none;
  margin-top:18px;
  max-height:180px;
  overflow:hidden;
}

#birthdayLines.show{
  display:block;
}

.birthday-line{
  opacity:0;
  transform:translateY(20px);
  margin:12px 0;
  color:#7a4bb5;
  font-size:17px;
  font-weight:bold;
  animation:lineIn .8s ease forwards;
}

/* धीरे-धीरे नीचे जाने वाला effect */
@keyframes lineIn{
  to{
    opacity:1;
    transform:translateY(0);
  }
}

.balloon{
  position:absolute;
  font-size:42px;
  animation:float 6s linear infinite;
}

.b1{
  left:7%;
  bottom:-60px;
}

.b2{
  right:8%;
  bottom:-70px;
  animation-delay:2s;
}

.b3{
  left:25%;
  bottom:-70px;
  animation-delay:4s;
}

.confetti{
  position:absolute;
  top:-20px;
  width:8px;
  height:14px;
  border-radius:3px;
  animation:fall 4s linear infinite;
}

@keyframes bounce{
  50%{
    transform:translateY(-10px) rotate(3deg);
  }
}

@keyframes pop{
  from{
    transform:scale(.7);
    opacity:0;
  }
  to{
    transform:scale(1);
    opacity:1;
  }
}

@keyframes float{
  to{
    transform:translateY(-115vh) rotate(20deg);
  }
}

@keyframes fall{
  to{
    transform:translateY(110vh) rotate(500deg);
  }
}
</style>
</head>

<body>

<div class="balloon b1">🎈</div>
<div class="balloon b2">🎈</div>
<div class="balloon b3">🎈</div>

<div class="card">

  <div class="emoji">🎂</div>

  <h1>Happy Birthday!</h1>

  <!-- यहाँ नाम बदलें -->
  <div class="name">Anubhav</div>

  <p>
    Today is all about smiles, happiness and beautiful memories. 💖<br>
    Wishing you an amazing birthday filled with lots of fun,
    laughter and surprises! ✨
  </p>

  <button onclick="showSurprise()">
    🎁 Open Your Surprise
  </button>

  <div id="surprise">

    <h2>💖 A Little Surprise 💖</h2>

    <p style="margin-top:10px">
      May your special day be as awesome and wonderful as you are! 🌸✨
    </p>

    <!-- प्यारी lines यहाँ आएंगी -->
    <div id="birthdayLines">

      <div class="birthday-line">
        🌸 May your smile always stay this beautiful. 💖
      </div>

      <div class="birthday-line">
        ✨ May every moment of your life be filled with happiness.
      </div>

      <div class="birthday-line">
        🥰 You deserve all the love, laughter and happiness in the world.
      </div>

      <div class="birthday-line">
        🎂 Keep smiling, keep shining and enjoy your special day!
      </div>

      <div class="birthday-line">
        💕 Once again, Happy Birthday! Have the most beautiful day. 🎉
      </div>

    </div>

  </div>

</div>

<script>

function showSurprise(){

  document.getElementById("surprise").classList.add("show");

  /* Birthday lines को धीरे-धीरे दिखाना */
  const lines = document.querySelectorAll(".birthday-line");

  document.getElementById("birthdayLines").classList.add("show");

  lines.forEach((line,index)=>{
    line.style.animationDelay = (index * 1.5) + "s";
  });

  /* Confetti */
  for(let i=0;i<35;i++){

    const c=document.createElement("div");

    c.className="confetti";

    c.style.left=Math.random()*100+"%";

    c.style.animationDelay=
      (Math.random()*1.5)+"s";

    c.style.animationDuration=
      (2.5+Math.random()*2)+"s";

    document.body.appendChild(c);

    setTimeout(()=>{
      c.remove();
    },5000);

  }

}

</script>

</body>
</html>
