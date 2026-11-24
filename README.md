<!DOCTYPE html>
<html lang="th">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MILD SOAP | ร้านสบู่สมุนไพร</title>
<style>
* { box-sizing: border-box; }
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: #f8f7ef;
  color: #354333;
}
header {
  background: #496b4b;
  color: white;
  padding: 25px;
  text-align: center;
}
header h1 { margin: 0; font-size: 32px; }
nav { margin-top: 15px; }
nav a { color: white; margin: 0 12px; text-decoration: none; }
.hero {
  text-align: center;
  padding: 55px 20px;
  background: #e7eddf;
}
.hero h2 { font-size: 30px; }
.products {
  max-width: 900px;
  margin: 35px auto;
  padding: 15px;
  display: grid;
  grid-template-columns: repeat(auto-fit,minmax(230px,1fr));
  gap: 25px;
}
.card {
  background: white;
  padding: 20px;
  border-radius: 15px;
  text-align: center;
  box-shadow: 0 3px 12px #0001;
}
.card img {
  width: 100%;
  height: 190px;
  object-fit: cover;
  border-radius: 10px;
  background: #e7eddf;
}
.price { color: #527b4e; font-size: 23px; font-weight: bold; }
button {
  background: #496b4b;
  color: white;
  border: 0;
  padding: 12px 22px;
  border-radius: 8px;
  cursor: pointer;
}
.order {
  max-width: 600px;
  margin: 30px auto;
  padding: 25px;
  background: white;
  border-radius: 15px;
}
input, select {
  width: 100%;
  padding: 12px;
  margin: 8px 0 15px;
  border: 1px solid #ccc;
  border-radius: 7px;
}
footer {
  text-align: center;
  background: #496b4b;
  color: white;
  padding: 20px;
}
</style>
</head>
<body>

<header>
<h1>MILD SOAP</h1>
<p>สบู่สมุนไพร เพื่อการดูแลผิว</p>
<nav>
<a href="#home">หน้าแรก</a>
<a href="#products">สินค้า</a>
<a href="#order">สั่งซื้อ</a>
</nav>
</header>

<section class="hero" id="home">
<h2>ดูแลผิวด้วยสบู่จากธรรมชาติ</h2>
<p>เลือกสบู่ที่เหมาะกับการดูแลผิวของคุณ</p>
<a href="#products"><button>เลือกซื้อสินค้า</button></a>
</section>

<section id="products">
<h2 style="text-align:center">สินค้าของเรา</h2>
<div class="products">

<div class="card">
<img src="images/herbal-soap.jpg" alt="สบู่สมุนไพร">
<h3>สบู่สมุนไพร</h3>
<p>SKU-001</p>
<p>สบู่สมุนไพรสำหรับทำความสะอาดผิว</p>
<p class="price">59 บาท</p>
<button onclick="choose('สบู่สมุนไพร',59)">เลือกสินค้า</button>
</div>

<div class="card">
<img src="images/aloe-vera-soap.jpg" alt="สบู่ว่านหางจระเข้">
<h3>สบู่ว่านหางจระเข้</h3>
<p>SKU-002</p>
<p>สบู่ว่านหางจระเข้สำหรับทำความสะอาดผิว</p>
<p class="price">69 บาท</p>
<button onclick="choose('สบู่ว่านหางจระเข้',69)">เลือกสินค้า</button>
</div>

</div>
</section>

<section class="order" id="order">
<h2>แบบฟอร์มสั่งซื้อสินค้า</h2>
<label>ชื่อผู้สั่งซื้อ</label>
<input id="name" placeholder="กรอกชื่อของคุณ">

<label>เลือกสินค้า</label>
<select id="product">
<option value="สบู่สมุนไพร">สบู่สมุนไพร - 59 บาท</option>
<option value="สบู่ว่านหางจระเข้">สบู่ว่านหางจระเข้ - 69 บาท</option>
</select>

<label>จำนวนสินค้า</label>
<input id="quantity" type="number" min="1" value="1">

<label>ที่อยู่จัดส่ง</label>
<input id="address" placeholder="กรอกที่อยู่จัดส่ง">

<button onclick="order()">ยืนยันคำสั่งซื้อ</button>
<p id="result"></p>
</section>

<footer>
<p>MILD SOAP | ร้านสบู่สมุนไพร</p>
<p>ขอบคุณที่เลือกซื้อสินค้ากับเรา</p>
</footer>

<script>
function choose(name,price) {
 document.getElementById('product').value=name;
 document.getElementById('order').scrollIntoView();
}
function order() {
 const name=document.getElementById('name').value;
 const product=document.getElementById('product').value;
 const quantity=Number(document.getElementById('quantity').value);
 const address=document.getElementById('address').value;
 const price=product==='สบู่สมุนไพร'?59:69;
 if(!name || !address || quantity<1 || !Number.isInteger(quantity)) {
  alert('กรุณากรอกข้อมูลให้ครบถ้วน');
  return;
 }
 document.getElementById('result').innerHTML=
 'รับคำสั่งซื้อทดลองแล้ว<br>สินค้า: '+product+
 '<br>จำนวน: '+quantity+' ชิ้น<br>ยอดรวม: '+(price*quantity)+' บาท';
}
</script>
</body>
</html>
