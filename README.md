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

html{
  scroll-behavior:smooth;
}

body{
  min-height:100vh;
  padding:25px 0 60px;
  font-family:Arial,sans-serif;
  overflow-x:hidden;

  /* BACKGROUND */
  background:
    radial-gradient(circle at 20% 20%, #ffffff80, transparent 25%),
    radial-gradient(circle at 80% 80%, #ffffff70, transparent 25%),
    linear-gradient(135deg,#ffd6e7,#d8e7ff,#e7d7ff);
}

.card{
  width:min(94%,470px);
  margin:auto;
  padding:28px 16px 35px;
  text-align:center;

  background:rgba(255,255,255,.78);
  backdrop-filter:blur(15px);

  border-radius:28px;

  box-shadow:
    0 20px 60px rgba(70,40,100,.25);
}

/* START SCREEN */

.start{
  padding:10px;
}

.cake{
  font-size:70px;
  animation:bounce 1.8s infinite;
}

h1{
  margin:12px 0;
  font-size:34px;
  color:#70449d;
}

.start p{
  color:#666;
  font-size:16px;
  margin-bottom:22px;
}

button{
  border:0;
  border-radius:999px;
  padding:14px 25px;

  color:white;
  background:
    linear-gradient(90deg,#ff69a6,#8d6bff);

  font-size:16px;
  font-weight:bold;

  cursor:pointer;

  box-shadow:
    0 8px 20px rgba(141,107,255,.3);
}

button:active{
  transform:scale(.95);
}

/* PHOTO AREA */

#gallery{
  display:none;
  margin-top:20px;
}

#gallery.show{
  display:block;
  animation:pop .5s ease;
}

.photo{
  display:none;
}

.photo.active{
  display:block;
  animation:photoIn .5s ease;
}

.count{
  color:#76548e;
  font-size:13px;
  font-weight:bold;
  margin-bottom:10px;
}

/* PHOTOS */

.photo img{
  width:100%;
  height:auto;

  max-height:72vh;

  object-fit:contain;

  display:block;

  border-radius:20px;

  background:#111;

  box-shadow:
    0 12px 35px rgba(0,0,0,.25);
}

/* MESSAGE PLACE */

.message{
  margin:15px 0;

  padding:14px;

  border-radius:15px;

  background:white;

  border:1px dashed #c5a8df;

  color:#888;

  font-size:15px;
}

/* BUTTONS */

.buttons{
  margin-top:10px;
}

.back{
  background:
    linear-gradient(90deg,#777,#9b7bb8);
}

/* FINAL */

#final{
  display:none;
}

#final.show{
  display:block;
  animation:pop .7s ease;
}

.final-emoji{
  font-size:70px;
  margin-bottom:10px;
}

#final h2{
  font-size:36px;
  color:#ff5f9e;
  margin:15px 0;
}

#final p{
  color:#666;
  font-size:17px;
  line-height:1.6;
}

/* BALLOONS */

.balloon{
  position:fixed;
  font-size:42px;
  z-index:-1;
  pointer-events:none;
  animation:float 7s linear infinite;
}

.b1{
  left:5%;
  bottom:-60px;
}

.b2{
  right:7%;
  bottom:-60px;
  animation-delay:2s;
}

.b3{
  left:45%;
  bottom:-60px;
  animation-delay:4s;
}

/* ANIMATIONS */

@keyframes bounce{
  50%{
    transform:translateY(-10px) rotate(3deg);
  }
}

@keyframes pop{
  from{
    transform:scale(.75);
    opacity:0;
  }

  to{
    transform:scale(1);
    opacity:1;
  }
}

@keyframes photoIn{
  from{
    opacity:0;
    transform:translateX(25px);
  }

  to{
    opacity:1;
    transform:translateX(0);
  }
}

@keyframes float{
  to{
    transform:translateY(-115vh) rotate(20deg);
  }
}
</style>
</head>


<body>

<!-- BACKGROUND BALLOONS -->

<div class="balloon b1">🎈</div>
<div class="balloon b2">🎈</div>
<div class="balloon b3">🎈</div>


<div class="card">


<!-- START -->

<div class="start" id="start">

  <div class="cake">🎂</div>

  <h1>Birthday Surprise</h1>

  <p>
    एक छोटा सा surprise आपके लिए 💖
  </p>

  <button onclick="openSurprise()">
    🎁 Open Surprise
  </button>

</div>



<!-- PHOTO GALLERY -->

<div id="gallery">


<!-- PHOTO 1 -->

<section class="photo active">

  <div class="count">
    PHOTO 1 / 5
  </div>

  <img src="photo1.jpg" alt="Birthday Photo 1">

  <div class="message">
    यहाँ अपना मैसेज लिखें...
  </div>

  <div class="buttons">

    <button onclick="nextPhoto()">
      Next ➜
    </button>

  </div>

</section>



<!-- PHOTO 2 -->

<section class="photo">

  <div class="count">
    PHOTO 2 / 5
  </div>

  <img src="photo2.jpg" alt="Birthday Photo 2">

  <div class="message">
    यहाँ अपना मैसेज लिखें...
  </div>

  <div class="buttons">

    <button class="back" onclick="previousPhoto()">
      ← Back
    </button>

    <button onclick="nextPhoto()">
      Next ➜
    </button>

  </div>

</section>



<!-- PHOTO 3 -->

<section class="photo">

  <div class="count">
    PHOTO 3 / 5
  </div>

  <img src="photo3.jpg" alt="Birthday Photo 3">

  <div class="message">
    यहाँ अपना मैसेज लिखें...
  </div>

  <div class="buttons">

    <button class="back" onclick="previousPhoto()">
      ← Back
    </button>

    <button onclick="nextPhoto()">
      Next ➜
    </button>

  </div>

</section>



<!-- PHOTO 4 -->

<section class="photo">

  <div class="count">
    PHOTO 4 / 5
  </div>

  <img src="photo4.jpg" alt="Birthday Photo 4">

  <div class="message">
    यहाँ अपना मैसेज लिखें...
  </div>

  <div class="buttons">

    <button class="back" onclick="previousPhoto()">
      ← Back
    </button>

    <button onclick="nextPhoto()">
      Next ➜
    </button>

  </div>

</section>



<!-- PHOTO 5 -->

<section class="photo">

  <div class="count">
    PHOTO 5 / 5
  </div>

  <img src="photo5.jpg" alt="Birthday Photo 5">

  <div class="message">
    यहाँ अपना मैसेज लिखें...
  </div>

  <div class="buttons">

    <button class="back" onclick="previousPhoto()">
      ← Back
    </button>

    <button onclick="finishBirthday()">
      💖 Finish
    </button>

  </div>

</section>


</div>



<!-- FINAL HAPPY BIRTHDAY -->

<div id="final">

  <div class="final-emoji">
    🎉🎂🎉
  </div>

  <h2>
    Happy Birthday! 💖
  </h2>

  <p>
    Wishing you lots of happiness,<br>
    smiles and beautiful memories. ✨
  </p>

</div>


</div>



<script>

let currentPhoto = 0;

const photos =
document.querySelectorAll(".photo");


function openSurprise(){

  document
  .getElementById("start")
  .style.display = "none";

  document
  .getElementById("gallery")
  .classList.add("show");

  scrollToGallery();

}


function nextPhoto(){

  if(currentPhoto < photos.length - 1){

    photos[currentPhoto]
    .classList.remove("active");

    currentPhoto++;

    photos[currentPhoto]
    .classList.add("active");

    scrollToGallery();

  }

}


function previousPhoto(){

  if(currentPhoto > 0){

    photos[currentPhoto]
    .classList.remove("active");

    currentPhoto--;

    photos[currentPhoto]
    .classList.add("active");

    scrollToGallery();

  }

}


function scrollToGallery(){

  document
  .getElementById("gallery")
  .scrollIntoView({
    behavior:"smooth",
    block:"start"
  });

}


function finishBirthday(){

  document
  .getElementById("gallery")
  .style.display = "none";

  document
  .getElementById("final")
  .classList.add("show");

  document
  .getElementById("final")
  .scrollIntoView({
    behavior:"smooth",
    block:"center"
  });

}

</script>

</body>
</html>
index.html
photo1.jpg
photo2.jpg
photo3.jpg
photo4.jpg
photo5.jpg
