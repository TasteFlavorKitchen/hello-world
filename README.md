<!DOCTYPE html>
<html>
<head>
    <title>簡易 POS</title>
    <style>
        body { font-family: Arial, sans-serif; }
        .button { padding: 10px 20px; margin: 5px; cursor: pointer; background: lightblue; border: none; }
    </style>
</head>
<body>
    <h2>POS 系統</h2>
    <button class="button" onclick="addItem('美式咖啡', 5)">美式咖啡 - $5</button>
    <button class="button" onclick="addItem('拿鐵', 6)">拿鐵 - $6</button>
    <h3>訂單：</h3>
    <ul id="orderList"></ul>
    <h3>總價: $<span id="totalPrice">0</span></h3>
    <button onclick="printReceipt()">列印收據</button>

    <script>
        let total = 0;
        function addItem(name, price) {
            const list = document.getElementById("orderList");
            const item = document.createElement("li");
            item.textContent = `${name} - $${price}`;
            list.appendChild(item);
            total += price;
            document.getElementById("totalPrice").textContent = total;
        }

        function printReceipt() {
            window.print();
        }
    </script>
</body>
</html>
