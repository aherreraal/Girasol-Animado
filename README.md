<!DOCTYPE html>
<html>
<body>
  <canvas id="girasol" width="500" height="600"></canvas>
  <script>
    const canvas = document.getElementById("girasol");
    const ctx = canvas.getContext("2d");
    let angle = 0;

    function draw() {
      // Fondo celeste
      ctx.fillStyle = "#87CEEB";
      ctx.fillRect(0, 0, canvas.width, canvas.height);
      
      // Centro del girasol (marrón)
      ctx.fillStyle = "#8B4513";
      ctx.beginPath();
      ctx.arc(250, 300, 50, 0, Math.PI * 2);
      ctx.fill();
      
      // Pétalos (amarillos)
      ctx.fillStyle = "#FFD700";
      for (let i = 0; i < 12; i++) {
        ctx.save();
        ctx.translate(250, 300);
        ctx.rotate(angle + (i * Math.PI / 6));
        ctx.beginPath();
        ctx.ellipse(60, 0, 40, 15, 0, 0, Math.PI * 2);
        ctx.fill();
        ctx.restore();
      }
      angle += 0.01;
      requestAnimationFrame(draw);
    }
    draw();
  </script>
</body>
</html>
