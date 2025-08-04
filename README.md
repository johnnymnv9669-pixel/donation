<html>
  <head>
    <meta charset="UTF-8" />
    <title></title>
    <style>
      body {
        background-color: #304674;
        color: white;
        font-family: Arial, sans-serif;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        height: 100vh;
        margin: 0;
      }
      .label {
        font-size: 22px;
        margin-bottom: 4px;
      }
      .money {
        font-size: 28px;
        font-weight: bold;
        color: #00ff88;
        margin-bottom: 16px;
      }
    </style>
  </head>
  <body>
    <div id="output">Loading...</div>

    <script>
      fetch("https://script.google.com/macros/s/AKfycbzzV5I2dIEwy5zNOSjUYQcSjEXqLM-JdtrQSpTGxy7hlyerTBiCetYj5QEUySIqfVA/exec")
        .then(response => response.json())
        .then(data => {
          document.getElementById("output").innerHTML = `
            <div class="label">Amount LAK:</div>
            <div class="money">${data.LAK}</div>
            <div class="label">Amount USD:</div>
            <div class="money">${data.USD}</div>
            <div class="label">Amount THB:</div>
            <div class="money">${data.THB}</div>
          `;
        })
        .catch(error => {
          document.getElementById("output").innerHTML = "❌ Error loading data.";
          console.error("Error:", error);
        });
    </script>
  </body>
</html>
