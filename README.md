<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Aarohi Photo Gallery</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1>Aarohi's Photo Gallery</h1>

  <div class="gallery">
    <div class="photo" data-caption="Photo 1">
      <img src="images/photo1.jpg" alt="Photo 1" onclick="openLightbox(0)">
      <a href="images/photo1.jpg" download>Download</a>
    </div>
    <div class="photo" data-caption="Photo 2">
      <img src="images/photo2.jpg" alt="Photo 2" onclick="openLightbox(1)">
      <a href="images/photo2.jpg" download>Download</a>
    </div>
    <div class="photo" data-caption="Photo 3">
      <img src="images/photo3.jpg" alt="Photo 3" onclick="openLightbox(2)">
      <a href="images/photo3.jpg" download>Download</a>
    </div>
    <!-- Add more photos here -->
  </div>

  <h2>Scan QR Code to Access</h2>
  <div class="qr">
    <img src="https://chart.googleapis.com/chart?cht=qr&chs=200x200&chl=https://tumhariwebsite.com" alt="QR Code">
  </div>

  <!-- Lightbox -->
  <div id="lightbox">
    <span class="close" onclick="closeLightbox()">&times;</span>
    <img id="lightbox-img" src="">
    <div id="caption"></div>
    <a class="prev" onclick="changeSlide(-1)">&#10094;</a>
    <a class="next" onclick="changeSlide(1)">&#10095;</a>
  </div>

  <script src="script.js"></script>
</body>
</html> 
AarohiGallery/
│
├─ index.html
├─ style.css
├─ script.js
└─ images/
      photo1.jpg
      photo2.jpg
      photo3.jpg
      ... (add more)
      body {
  font-family: Arial, sans-serif;
  text-align: center;
  background-color: #f0f0f5;
  color: #333;
  padding: 20px;
}

h1, h2 {
  margin-bottom: 20px;
}

.gallery {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 20px;
  margin-bottom: 40px;
}

.photo {
  border: 2px solid #ddd;
  padding: 10px;
  background: #fff;
  border-radius: 10px;
  transition: transform 0.3s;
}

.photo img {
  max-width: 100%;
  border-radius: 10px;
  cursor: pointer;
}

.photo:hover {
  transform: scale(1.05);
}

.photo a {
  display: block;
  margin-top: 10px;
  text-decoration: none;
  background-color: #ff4081;
  color: #fff;
  padding: 8px 12px;
  border-radius: 5px;
}

.qr img {
  margin-top: 20px;
  border: 2px solid #333;
  border-radius: 10px;
}

/* Lightbox */
#lightbox {
  display: none;
  position: fixed;
  z-index: 999;
  left: 0; top: 0;
  width: 100%; height: 100%;
  background-color: rgba(0,0,0,0.9);
  justify-content: center;
  align-items: center;
  overflow: hidden;
}

#lightbox img {
  max-width: 90%;
  max-height: 80%;
  border-radius: 10px;
  transition: 0.5s;
}

#caption {
  color: #fff;
  margin-top: 10px;
  font-size: 18px;
}

.close {
  position: absolute;
  top: 20px;
  right: 30px;
  color: #fff;
  font-size: 40px;
  font-weight: bold;
  cursor: pointer;
}

.prev, .next {
  cursor: pointer;
  position: absolute;
  top: 50%;
  width: auto;
  padding: 16px;
  color: #fff;
  font-weight: bold;
  font-size: 40px;
  user-select: none;
  transition: 0.3s;
}

.prev { left: 10px; }
.next { right: 10px; }

.prev:hover, .next:hover { color: #ff4081; }
let photos = document.querySelectorAll('.gallery .photo img');
let captions = Array.from(document.querySelectorAll('.gallery .photo')).map(p => p.dataset.caption);
let currentIndex = 0;

function openLightbox(index) {
  currentIndex = index;
  document.getElementById('lightbox').style.display = 'flex';
  updateLightbox();
}

function closeLightbox() {
  document.getElementById('lightbox').style.display = 'none';
}

function changeSlide(n) {
  currentIndex += n;
  if(currentIndex < 0) currentIndex = photos.length - 1;
  if(currentIndex >= photos.length) currentIndex = 0;
  updateLightbox();
}

function updateLightbox() {
  document.getElementById('lightbox-img').src = photos[currentIndex].src;
  document.getElementById('caption').innerText = captions[currentIndex];
}

console.log("Aarohi's Full Photo Gallery Website Ready!");
