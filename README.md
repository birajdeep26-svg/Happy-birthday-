# Happy-birthday- from pathlib import Path
import zipfile, shutil

base = Path("/mnt/data/birthday_website")
base.mkdir(exist_ok=True)

# Copy uploaded photos into the website folder with simple names.
srcs = [
    Path("/mnt/data/1000041429.jpg"),
    Path("/mnt/data/1000041425.jpg"),
    Path("/mnt/data/1000041426.jpg"),
    Path("/mnt/data/1000041427.jpg"),
    Path("/mnt/data/1000041428.jpg"),
]
for i, src in enumerate(srcs, 1):
    shutil.copy2(src, base / f"photo{i}.jpg")

html = r'''<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Birthday Surprise 🎂</title>

<style>
*{box-sizing:border-box;margin:0;padding:0}

html{scroll-behavior:smooth}

body{
  min-height:100vh;
  font-family:Arial,sans-serif;
  background:linear-gradient(135deg,#ffd6e7,#d8e7ff,#e7d7ff);
  overflow-x:hidden;
  padding:25px 0 60px;
}

.card{
  width:min(94%,460px);
  margin:0 auto;
  padding:28px 18px 35px;
  text-align:center;
  border-radius:28px;
  background:rgba(255,255,255,.75);
  backdrop-filter:blur(14px);
  box-shadow:0 20px 60px rgba(70,40,100,.22);
}

.emoji{
  font-size:58px;
  animation:bounce 1.8s infinite;
}

h1{
  margin:10px 0 22px;
  color:#6d3fa0;
  font-size:32px;
}

button{
  border:0;
  border-radius:999px;
  padding:14px 27px;
  font-size:16px;
  font-weight:bold;
  color:white;
  cursor:pointer;
  background:linear-gradient(90deg,#ff69a6,#8d6bff);
  box-shadow:0 8px 20px rgba(141,107,255,.3);
}

#gallery{
  display:none;
  margin-top:25px;
}

#gallery.show{
  display:block;
  animation:pop .5s ease;
}

.photo-page{
  display:none;
  animation:photoIn .5s ease;
}

.photo-page.active{
  display:block;
}

.photo{
  width:100%;
  max-height:75vh;
  object-fit:contain;
  border-radius:20px;
  display:block;
  margin:0 auto 18px;
  background:#111;
  box-shadow:0 12px 35px rgba(0,0,0,.22);
}

.message{
  margin:0 auto 18px;
  padding:14px;
  border-radius:15px;
  background:rgba(255,255,255,.8);
  color:#777;
  font-size:15px;
  line-height:1.5;
  border:1px dashed #c5a8df;
}

/* यहाँ अपना मैसेज लिखें */
.message span{
  color:#999;
}

.counter{
  margin:8px 0 14px;
  color:#76548e;
  font-size:14px;
  font-weight:bold;
}

.next-btn{
  display:none;
}

.next-btn.show{
  display:inline-block;
}

.back-btn{
  display:none;
  margin-left:7px;
  background:linear-gradient(90deg,#777,#9b7bb8);
}

.back-btn.show{
  display:inline-block;
}

@keyframes bounce{
  50%{transform:translateY(-10px) rotate(3deg)}
}

@keyframes pop{
  from{transform:scale(.7);opacity:0}
  to{transform:scale(1);opacity:1}
}

@keyframes photoIn{
  from{opacity:0;transform:translateY(25px)}
  to{opacity:1;transform:translateY(0)}
}
</style>
</head>

<body>

<div class="card">

  <div class="emoji">🎂</div>
  <h1>Birthday Surprise</h1>

  <button id="openBtn" onclick="openSurprise()">🎁 Open</button>

  <div id="gallery">

    <div class="photo-page active">
      <div class="counter">Photo 1 / 5</div>
      <img class="photo" src="photo1.jpg" alt="Birthday photo 1">
      <div class="message">
        <span>यहाँ अपना मैसेज लिखें...</span>
      </div>
      <button class="next-btn show" onclick="nextPhoto()">Next ➜</button>
    </div>

    <div class="photo-page">
      <div class="counter">Photo 2 / 5</div>
      <img class="photo" src="photo2.jpg" alt="Birthday photo 2">
      <div class="message">
        <span>यहाँ अपना मैसेज लिखें...</span>
      </div>
      <button class="back-btn show" onclick="prevPhoto()">← Back</button>
      <button class="next-btn show" onclick="nextPhoto()">Next ➜</button>
    </div>

    <div class="photo-page">
      <div class="counter">Photo 3 / 5</div>
      <img class="photo" src="photo3.jpg" alt="Birthday photo 3">
      <div class="message">
        <span>यहाँ अपना मैसेज लिखें...</span>
      </div>
      <button class="back-btn show" onclick="prevPhoto()">← Back</button>
      <button class="next-btn show" onclick="nextPhoto()">Next ➜</button>
    </div>

    <div class="photo-page">
      <div class="counter">Photo 4 / 5</div>
      <img class="photo" src="photo4.jpg" alt="Birthday photo 4">
      <div class="message">
        <span>यहाँ अपना मैसेज लिखें...</span>
      </div>
      <button class="back-btn show" onclick="prevPhoto()">← Back</button>
      <button class="next-btn show" onclick="nextPhoto()">Next ➜</button>
    </div>

    <div class="photo-page">
      <div class="counter">Photo 5 / 5</div>
      <img class="photo" src="photo5.jpg" alt="Birthday photo 5">
      <div class="message">
        <span>यहाँ अपना मैसेज लिखें...</span>
      </div>
      <button class="back-btn show" onclick="prevPhoto()">← Back</button>
    </div>

  </div>
</div>

<script>
let current = 0;
const pages = document.querySelectorAll(".photo-page");

function openSurprise(){
  document.getElementById("openBtn").style.display = "none";
  document.getElementById("gallery").classList.add("show");

  document.getElementById("gallery").scrollIntoView({
    behavior:"smooth",
    block:"start"
  });
}

function showPhoto(index){
  pages[current].classList.remove("active");
  current = index;
  pages[current].classList.add("active");

  pages[current].scrollIntoView({
    behavior:"smooth",
    block:"start"
  });
}

function nextPhoto(){
  if(current < pages.length - 1){
    showPhoto(current + 1);
  }
}

function prevPhoto(){
  if(current > 0){
    showPhoto(current - 1);
  }
}
</script>

</body>
</html>
'''

(base / "index.html").write_text(html, encoding="utf-8")

zip_path = Path("/mnt/data/Birthday_Surprise_Website.zip")
with zipfile.ZipFile(zip_path, "w", zipfile.ZIP_DEFLATED) as z:
    for f in sorted(base.iterdir()):
        z.write(f, arcname=f.name)

print(f"तैयार है: {zip_path}")
