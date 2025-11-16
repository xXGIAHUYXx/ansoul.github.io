<!doctype html>
<html lang="vi">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Thanh toán VietQR</title>

  <style>
    :root{
      --accent:#0b76ef;
      --bg:#f6f8fb;
      --card:#ffffff;
      --muted:#6b7280;
      --radius:12px;
      font-family: Inter, "Segoe UI", Roboto, "Helvetica Neue", Arial;
    }
    body{
      margin:0;
      background:var(--bg);
      display:flex;
      align-items:center;
      justify-content:center;
      min-height:100vh;
      padding:24px;
    }

    .container{
      width:100%;
      max-width:720px;
      background:var(--card);
      border-radius:var(--radius);
      box-shadow:0 10px 30px rgba(11,118,239,0.06);
      padding:20px;
    }

    h1{ margin:0 0 14px 0; font-size:20px; }
    p.lead{ margin:0 0 18px 0; color:var(--muted); }

    .grid{
      display:grid;
      grid-template-columns: repeat(2, 1fr);
      gap:12px;
    }
    .full{ grid-column: 1 / -1; }

    label{
      display:block;
      font-size:13px;
      color:#111827;
      margin-bottom:6px;
    }

    input, textarea {
      width:100%;
      padding:10px 12px;
      border-radius:8px;
      border:1px solid #e6e9ef;
      background:white;
      font-size:14px;
      box-sizing:border-box;
    }

    textarea{ resize:vertical; min-height:80px; }

    .actions{
      display:flex;
      gap:12px;
      margin-top:16px;
      justify-content:flex-end;
      align-items:center;
    }

    .btn{
      border:0;
      padding:10px 16px;
      border-radius:10px;
      font-weight:600;
      cursor:pointer;
      background:var(--accent);
      color:white;
      box-shadow: 0 6px 18px rgba(11,118,239,0.12);
    }
    .btn.secondary{
      background:transparent;
      color:var(--accent);
      border:1px solid #dbeafe;
    }

    /* Overlay / modal */
    .overlay{
      position:fixed;
      inset:0;
      display:none;
      align-items:center;
      justify-content:center;
      background:rgba(0,0,0,0.45);
      z-index:9999;
      padding:20px;
    }
    .overlay.open{ display:flex; }

    .modal{
      width:100%;
      max-width:520px;
      background:var(--card);
      border-radius:14px;
      padding:20px;
      box-shadow:0 18px 50px rgba(0,0,0,0.35);
    }

    .modal-header{
      display:flex;
      justify-content:space-between;
      align-items:center;
      margin-bottom:12px;
    }
    .modal-title{ font-size:18px; font-weight:700; }
    .close-btn{
      background:transparent;
      border:0;
      font-size:20px;
      cursor:pointer;
    }

    .qr-box{
      text-align:center;
      margin-top:12px;
    }
    .qr-box img{
      width:260px;
      border-radius:14px;
      box-shadow:0 8px 22px rgba(0,0,0,0.12);
    }

    .hint{ font-size:13px; color:var(--muted); margin-top:10px; }

    .shop-header {
      display: flex;
      align-items: center;
      gap: 10px;
      margin-bottom: 16px;
    }

    .shop-logo {
      width: 46px;
      height: 46px;
      border-radius: 10px;
      object-fit: cover;
    }

    .shop-name {
      font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
      font-style: italic;
      font-size: 30px;
      font-weight: 700;
      color: #503D6B;
    }
  </style>
</head>
<body>

  <div class="container">
    <div class="shop-header">
      <img src="https://res.cloudinary.com/dqw7hwgly/image/upload/AnSoul_logo_crop_za1fjf.png" class="shop-logo" />
      <span class="shop-name">AnSoul</span>
    </div>
    <h1>Thanh toán VietQR</h1>
    <p class="lead">Điền thông tin đơn hàng để tạo mã QR thanh toán.</p>

    <form id="orderForm" onsubmit="return false;">
      <div class="grid">

        <div>
          <label>Tên sản phẩm</label>
          <input id="product" type="text" value="Nến thơm hương hoa oải hương" readonly>
        </div>

        <div>
          <label>Số lượng</label>
          <input id="qty" type="number" min="1" value="1" required>
        </div>

        <div class="full">
          <label>Đơn giá (VND)</label>
          <input id="price" type="number" min="1" value="100000" required>
        </div>

        <div>
          <label>Họ và tên</label>
          <input id="name" type="text" placeholder="Họ và tên" required>
        </div>

        <div>
          <label>Số điện thoại</label>
          <input id="phone" type="text" placeholder="Số điện thoại" required>
        </div>

        <div class="full">
          <label>Địa chỉ</label>
          <textarea id="address" required></textarea>
        </div>

      </div>

      <div class="actions">
        <button type="button" class="btn secondary" id="clearBtn">Xóa</button>
        <button type="button" class="btn" id="payNow">Thanh toán</button>
      </div>
    </form>

  </div>

  <!-- Modal hiển thị QR -->
  <div class="overlay" id="overlay">
    <div class="modal">
      <div class="modal-header">
        <div class="modal-title">Quét VietQR để thanh toán</div>
        <button class="close-btn" id="closeModal">&times;</button>
      </div>

      <div class="qr-box">
        <img id="qrImage" src="" alt="QR VietQR">
        <div class="hint" id="qrInfo"></div>
      </div>
    </div>
  </div>


<script>
  const overlay = document.getElementById("overlay");
  const closeModal = document.getElementById("closeModal");
  const qrImage = document.getElementById("qrImage");
  const qrInfo = document.getElementById("qrInfo");

  function formatVND(n){
    return new Intl.NumberFormat('vi-VN').format(n) + ' ₫';
  }

  document.getElementById("payNow").addEventListener("click", () => {
    const product = document.getElementById("product").value.trim();
    const qty = Number(document.getElementById("qty").value);
    const price = Number(document.getElementById("price").value);

    if (!product || qty < 1 || price < 1){
      alert("Vui lòng nhập đầy đủ thông tin sản phẩm.");
      return;
    }

    const name = document.getElementById("name").value.trim();
    const addr = document.getElementById("address").value.trim();
    if (!name || !addr){
      alert("Vui lòng nhập đầy đủ thông tin khách hàng.");
      return;
    }

    // Tính số tiền
    const amount = qty * price;

    // encode tên sản phẩm
    const productEncoded = encodeURIComponent(product);

    // tạo URL QR VietQR
    const qrUrl =
      `https://img.vietqr.io/image/ACB-39527607-print.png?amount=${amount}&addInfo=${productEncoded}&accountName=vuong%20gia%20huy`;

    qrImage.src = qrUrl;
    qrInfo.textContent = `Sản phẩm: ${product} | SL: ${qty} | Thành tiền: ${formatVND(amount)}`;

    overlay.classList.add("open");
  });

  closeModal.addEventListener("click", () => {
    overlay.classList.remove("open");
  });

  overlay.addEventListener("click", (e) => {
    if (e.target === overlay) overlay.classList.remove("open");
  });

  document.getElementById("clearBtn").addEventListener("click", () => {
    document.getElementById("orderForm").reset();
  });
</script>

</body>
</html>
