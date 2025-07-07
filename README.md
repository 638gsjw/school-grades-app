# school-grades-app
<!DOCTYPE html>
<html lang="ar">
<head>
  <meta charset="UTF-8">
  <title>تطبيق مُفضل الشرعبي</title>
  <style>
    body { background: #E0F7FA; font-family: Arial, sans-serif; direction: rtl; text-align: center; padding: 20px; }
    input, button { padding: 10px; margin: 5px; font-size: 16px; border-radius: 8px; }
    .result { margin-top: 20px; font-weight: bold; color: #01579B; }
  </style>
</head>
<body>
  <h2>تطبيق مُفضل الشرعبي 📱</h2>
  <input type="text" id="name" placeholder="اسم الطالب"><br>
  <input type="number" id="quran" placeholder="درجة القرآن"><br>
  <input type="number" id="islamic" placeholder="التربية الإسلامية"><br>
  <input type="number" id="arabic" placeholder="اللغة العربية"><br>
  <input type="number" id="english" placeholder="الإنجليزية"><br>
  <input type="number" id="math" placeholder="الرياضيات"><br>
  <input type="number" id="physics" placeholder="الفيزياء"><br>
  <input type="number" id="chemistry" placeholder="الكيمياء"><br>
  <input type="number" id="bio" placeholder="الأحياء"><br>

  <button onclick="calculate()">احسب النتيجة</button>

  <div class="result" id="output"></div>

  <script>
    function calculate() {
      const values = [
        +document.getElementById("quran").value,
        +document.getElementById("islamic").value,
        +document.getElementById("arabic").value,
        +document.getElementById("english").value,
        +document.getElementById("math").value,
        +document.getElementById("physics").value,
        +document.getElementById("chemistry").value,
        +document.getElementById("bio").value
      ];
      const sum = values.reduce((a, b) => a + b, 0);
      const avg = sum / 8;
      let grade = "", stars = "";
      if (avg >= 90) { grade = "ممتاز"; stars = "⭐⭐⭐⭐⭐"; }
      else if (avg >= 80) { grade = "جيد جدًا"; stars = "⭐⭐⭐⭐"; }
      else if (avg >= 70) { grade = "جيد"; stars = "⭐⭐⭐"; }
      else if (avg >= 60) { grade = "مقبول"; stars = "⭐⭐"; }
      else { grade = "راسب"; stars = "⭐"; }

      const name = document.getElementById("name").value;
      document.getElementById("output").innerHTML =
        `📛 الاسم: ${name}<br>📊 المجموع: ${sum}<br>📈 المعدل: ${avg}<br>🏅 التقدير: ${grade}<br>${stars}<br>✨ تصميم مُفضل الشرعبي`;
    }
  </script>
</body>
</html>
