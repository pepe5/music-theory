<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bloom with Chromatic Scale</title>
</head>
<body>
    <canvas id="bloomCanvas" width="600" height="600"></canvas>
    <script>
        const canvas = document.getElementById('bloomCanvas');
        const ctx = canvas.getContext('2d');
        const centerX = canvas.width / 2;
        const centerY = canvas.height / 2;
        const bigRadius = 100;
        const smallRadius = 70;
        const chromaticScale = ['C', 'C#', 'D', 'D#', 'E', 'F', 'F#', 'G', 'G#', 'A', 'A#', 'HB'];

        function drawPetal(x, y, radius, angle, color) {
            ctx.beginPath();
            ctx.moveTo(x, y);
            ctx.arc(x, y, radius, angle, angle + Math.PI / 6);
            ctx.lineTo(x, y);
            ctx.fillStyle = color;
            ctx.fill();
            ctx.closePath();
        }

        function drawBloom() {
            for (let i = 0; i < 6; i++) {
                let angle = i * (Math.PI / 3);
                let color = `hsl(${i * 60}, 100%, 70%)`;
                drawPetal(centerX, centerY, bigRadius, angle, color);
                color = `hsl(${i * 75}, 100%, 40%)`;
                drawPetal(centerX, centerY, smallRadius, angle + Math.PI / 6, color);
            }
        }

        function annotatePetals() {
            for (let i = 0; i < 12; i++) {
                let angle = i * (Math.PI / 6) + 0.27;
                let x = centerX + (bigRadius + 20) * Math.cos(angle);
                let y = centerY + (bigRadius + 20) * Math.sin(angle);
                ctx.fillStyle = 'green';
                ctx.font = '16px Arial';
                ctx.fillText(chromaticScale[i], x - 10, y + 5);
            }
        }

        drawBloom();
        annotatePetals();
    </script>
</body>
</html>
