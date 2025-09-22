<!DOCTYPE html>
<html lang="th">
<head>
  <meta charset="UTF-8">
  <title>โปรแกรมนับคาร์บ (Carb Counting)</title>
  <style>
    body {
      font-family: "Prompt", sans-serif;
      background: linear-gradient(135deg, #f6d365, #fda085);
      text-align: center;
      padding: 40px;
    }
    h1 {
      color: #2d3436;
    }
    input, button {
      font-size: 16px;
      padding: 8px;
      margin: 5px;
      border-radius: 5px;
      border: 1px solid #d63031;
    }
    button {
      background-color: #e17055;
      color: white;
      cursor: pointer;
    }
    button:hover {
      background-color: #d63031;
    }
    table {
      margin: 20px auto;
      border-collapse: collapse;
      width: 80%;
    }
    th, td {
      border: 1px solid #b2bec3;
      padding: 10px;
      text-align: center;
    }
    th {
      background-color: #ffeaa7;
    }
    #total {
      font-size: 20px;
      margin-top: 20px;
      font-weight: bold;
      color: #2d3436;
    }
  </style>
</head>
<body>
  <h1>🍚 โปรแกรมนับคาร์โบไฮเดรต</h1>
  <p>
    อาหาร: <input type="text" id="food" placeholder="เช่น ข้าวสวย">
    คาร์บ (กรัม): <input type="number" id="carb" placeholder="เช่น 45">
    <button onclick="addFood()">➕ เพิ่ม</button>
  </p>

  <table id="foodTable">
    <tr>
      <th>อาหาร</th>
      <th>คาร์บ (กรัม)</th>
    </tr>
  </table>

  <div id="total">รวมคาร์บทั้งหมด: 0 กรัม</div>

  <script>
    let totalCarb = 0;

    function addFood() {
      const food = document.getElementById("food").value;
      const carb = parseFloat(document.getElementById("carb").value);

      if (food && carb > 0) {
        const table = document.getElementById("foodTable");
        const row = table.insertRow();
        const cell1 = row.insertCell(0);
        const cell2 = row.insertCell(1);

        cell1.innerHTML = food;
        cell2.innerHTML = carb + " กรัม";

        totalCarb += carb;
        document.getElementById("total").innerHTML = 
          `รวมคาร์บทั้งหมด: ${totalCarb} กรัม 🍞`;
        
        document.getElementById("food").value = "";
        document.getElementById("carb").value = "";
      } else {
        alert("กรุณากรอกชื่ออาหารและปริมาณคาร์บให้ถูกต้อง");
      }
    }
  </script>
</body>
</html>
