<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Amora Joyería</title>

<!-- Fuentes elegantes -->
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@500;700&family=Raleway:wght@300;400;600&display=swap" rel="stylesheet">

<style>
:root {
  --gold: #c5a14e;
  --dark: #0d0d0d;
  --light: #faf7f2;
  --gray: #9a9a9a;
}

/* Fondo animado y difuminado */
body {
  font-family: "Raleway", sans-serif;
  margin: 0;
  padding: 0;
  color: var(--light);
  background: linear-gradient(-45deg, #0d0d0d, #1a1a1a, #c5a14e, #2b2b2b);
  background-size: 400% 400%;
  animation: gradientBG 20s ease infinite;
}

/* Animación del fondo */
@keyframes gradientBG {
  0% {background-position: 0% 50%;}
  50% {background-position: 100% 50%;}
  100% {background-position: 0% 50%;}
}

header {
  text-align: center;
  padding: 60px 20px;
  background: rgba(0, 0, 0, 0.6);
}

header h1 {
  font-family: "Playfair Display", serif;
  font-size: 3.5rem;
  letter-spacing: 4px;
  color: var(--gold);
  margin: 0;
  text-shadow: 0px 2px 6px rgba(0,0,0,0.6);
}

header p {
  font-size: 1.2rem;
  color: var(--gray);
  margin-top: 10px;
}

/* Contenedor del slider */
.flyer-container {
  position: relative;
  width: 90%;
  max-width: 1000px;
  margin: 50px auto;
  overflow: hidden;
  border-radius: 20px;
  box-shadow: 0 6px 20px rgba(0,0,0,0.6);
}

.flyer {
  display: flex;
  transition: transform 1s ease-in-out;
  width: 300%;
}

.flyer img {
  width: 100%;
  flex: 1;
  object-fit: cover;
}

/* Miniaturas */
.thumbnails {
  display: flex;
  justify-content: center;
  gap: 15px;
  margin-top: 20px;
}

.thumbnails img {
  width: 100px;
  height: 70px;
  object-fit: cover;
  border: 2px solid transparent;
  border-radius: 8px;
  cursor: pointer;
  transition: transform 0.3s, border 0.3s;
}

.thumbnails img:hover {
  transform: scale(1.1);
  border: 2px solid var(--gold);
}

/* Botones de control */
.controls {
  position: absolute;
  top: 50%;
  width: 100%;
  display: flex;
  justify-content: space-between;
  transform: translateY(-50%);
  padding: 0 20px;
}

.controls button {
  background: rgba(0,0,0,0.5);
  border: 2px solid var(--gold);
  color: var(--gold);
  font-size: 2rem;
  padding: 10px 20px;
  cursor: pointer;
  border-radius: 50%;
  transition: background 0.3s, transform 0.2s;
}

.controls button:hover {
  background: var(--gold);
  color: var(--dark);
  transform: scale(1.1);
}

footer {
  text-align: center;
  padding: 30px 10px;
  color: var(--gray);
  font-size: 0.9rem;
  margin-top: 60px;
}

footer span {
  color: var(--gold);
}

/* Botón flotante WhatsApp */
.whatsapp-float {
  position: fixed;
  bottom: 20px;
  right: 20px;
  background: #25d366;
  color: white;
  border-radius: 50%;
  width: 60px;
  height: 60px;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 2rem;
  box-shadow: 0px 4px 8px rgba(0,0,0,0.4);
  transition: transform 0.3s;
  text-decoration: none;
  z-index: 1000;
}

.whatsapp-float:hover {
  transform: scale(1.1);
  background: #20b954;
}
</style>
</head>
<body>

<header>
  <h1>Amora Joyería</h1>
  <p>Elegancia que perdura en el tiempo</p>
</header>

<!-- SLIDER -->
<div class="flyer-container">
  <div class="flyer" id="flyer">
    <img src="https://i.ibb.co/ry8ddZW/joya1.jpg" alt="Joya 1">
    <img src="https://i.ibb.co/SJxnrYp/joya2.jpg" alt="Joya 2">
    <img src="https://i.ibb.co/gFcWr9D/joya3.jpg" alt="Joya 3">
  </div>
  <div class="controls">
    <button onclick="moveSlide(-1)">❮</button>
    <button onclick="moveSlide(1)">❯</button>
  </div>
</div>

<!-- Miniaturas -->
<div class="thumbnails">
  <img src="https://i.ibb.co/ry8ddZW/joya1.jpg" onclick="goToSlide(0)">
  <img src="https://i.ibb.co/SJxnrYp/joya2.jpg" onclick="goToSlide(1)">
  <img src="https://i.ibb.co/gFcWr9D/joya3.jpg" onclick="goToSlide(2)">
</div>

<footer>
  © 2025 <span>Amora Joyería</span> · Todos los derechos reservados
</footer>

<!-- Botón WhatsApp -->
<a href="https://wa.me/50212345678?text=Hola%20quiero%20más%20información%20sobre%20Amora%20Joyería" 
   class="whatsapp-float" target="_blank">
   💬
</a>

<script>
let index = 0;
const flyer = document.getElementById('flyer');

function moveSlide(step) {
  index += step;
  if (index < 0) index = 2;
  if (index > 2) index = 0;
  flyer.style.transform = `translateX(-${index * 100}%)`;
}

function goToSlide(n) {
  index = n;
  flyer.style.transform = `translateX(-${index * 100}%)`;
}

// Cambio automático cada 5 segundos
setInterval(() => moveSlide(1), 5000);
</script>
</body>
</html
