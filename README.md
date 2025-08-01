<!DOCTYPE html>
<html lang="th">
<head>
  <meta charset="UTF-8" />
  <title>ยอดเงินบริจาค</title>
  <style>
    body {
      background-color: #304674;
      color: white;
      font-family: Arial, sans-serif;
      text-align: center;
      padding: 50px;
    }
    .label { font-size: 22px; margin-top: 10px; }
    .money { color: #00ff88; font-weight: bold; font-size: 28px; }
  </style>
</head>
<body>
  <h2>ยอดเงินบริจาคทั้งหมด</h2>
  <div class="label">LAK:</div>
  <div class="money" id="lak">Loading...</div>
  <div class="label">USD:</div>
  <div class="money" id="usd">Loading...</div>
  <div class="label">THB:</div>
  <div class="money" id="thb">Loading...</div>

  <script>
    const scriptURL =
      "https://script.google.com/macros/s/AKfycbyRRkVfsYFlgezwx5P8sjGjjQpw0B9kRK9KiUBee96yja0gddG6psPSuPdCRmd460M/exec";

    fetch(scriptURL)
      .then(res => res.json())
      .then(data => {
        document.getElementById("lak").textContent = data.LAK + " LAK";
        document.getElementById("usd").textContent = data.USD + " USD";
        document.getElementById("thb").textContent = data.THB + " THB";
      })
      .catch(err => {
        console.error("Error loading data:", err);
        document.getElementById("lak").textContent = "ไม่สามารถโหลดได้";
        document.getElementById("usd").textContent = "-";
        document.getElementById("thb").textContent = "-";
      });
  </script>
</body>
</html>
