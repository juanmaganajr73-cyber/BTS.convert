from PIL import Image
import qrcode

html = """
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>BTS Concert Surprise</title>
<style>
body {
  background: radial-gradient(circle at top, #7b2ff7, #000);
  color: white;
  font-family: Arial, sans-serif;
  text-align: center;
  padding-top: 15vh;
}
h1 { font-size: 3em; }
h2 { font-size: 1.9em; margin-top: 18px; }
p { font-size: 1.5em; margin-top: 10px; }
.time { font-size: 1.6em; font-weight: bold; margin-top: 10px; }
</style>
</head>
<body>
<h1>🎆 YOU'RE GOING TO A BTS CONCERT 🎆</h1>
<h2>May 23, 2026</h2>
<div class="time">⏰ 8:00 PM</div>
<p>📍 Allegiant Stadium</p>
<p>Las Vegas, NV</p>
<p>💜 Surprise! 💜</p>
</body>
</html>
"""

data_url = "data:text/html;charset=utf-8," + html.replace("\n", "")

qr = qrcode.QRCode(
    version=None,
    error_correction=qrcode.constants.ERROR_CORRECT_Q,
    box_size=10,
    border=4,
)
qr.add_data(data_url)
qr.make(fit=True)

img = qr.make_image(fill_color="black", back_color="white")
path = "/mnt/data/BTS_Concert_Surprise_QR_May23_2026_8PM.png"
img.save(path)

path# BTS.convert
