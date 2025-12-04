
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
