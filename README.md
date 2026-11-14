8<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
  <meta name="description" content="PINOZ Store - katalog produk dan pemesanan produk pertanian melalui WhatsApp.">
  <meta name="theme-color" content="#0c4f31">
  <title>PINOZ Store | Belanja Produk Pertanian</title>
  <style>
    :root{--green:#167447;--dark:#0c4f31;--mint:#eaf7ef;--lime:#b9e769;--ink:#183329;--muted:#687b71;--line:#e3ece6;--bg:#f7faf7;--shadow:0 12px 32px rgba(18,65,42,.09)}
    *{box-sizing:border-box}
    html{scroll-behavior:smooth;scroll-padding-top:90px}
    body{margin:0;font-family:Inter,system-ui,-apple-system,"Segoe UI",sans-serif;color:var(--ink);background:var(--bg);line-height:1.5}
    button,input,textarea{font:inherit}button{cursor:pointer}
    .topbar{background:var(--dark);color:#e9fff1;text-align:center;padding:8px 12px;font-size:12px}
    header{position:sticky;top:0;z-index:20;background:rgba(255,255,255,.97);border-bottom:1px solid var(--line)}
    .nav{max-width:1160px;margin:auto;padding:12px 20px;display:flex;align-items:center;justify-content:space-between;gap:14px}
    .brand{display:flex;align-items:center;gap:9px;color:var(--dark);text-decoration:none;font-weight:900;font-size:21px;letter-spacing:.5px}
    .brand-mark{width:36px;height:36px;border-radius:12px;display:grid;place-items:center;background:var(--lime)}
    .nav-links{display:flex;gap:22px;align-items:center}
    .nav-links a{color:var(--ink);text-decoration:none;font-size:13px;font-weight:700}
    .cart-button,.add-btn,.submit{border:0;background:var(--green);color:#fff;font-weight:800}
    .cart-button{border-radius:999px;padding:10px 15px;white-space:nowrap}
    .hero{background:radial-gradient(circle at 85% 20%,rgba(185,231,105,.3),transparent 28%),linear-gradient(120deg,#0c4f31,#167447 65%,#2b8c5a);color:#fff}
    .hero-inner{max-width:1160px;margin:auto;padding:56px 22px;display:grid;grid-template-columns:1.15fr .85fr;align-items:center;gap:32px}
    .eyebrow{display:inline-block;padding:6px 11px;border-radius:99px;background:#ffffff20;color:#e9ffd2;font-size:11px;font-weight:850;letter-spacing:1px}
    h1{font-size:clamp(34px,5vw,58px);line-height:1.08;letter-spacing:-1.5px;margin:15px 0}
    .hero p{max-width:580px;color:#e1f3e8;font-size:15px;line-height:1.75}
    .hero-actions{display:flex;gap:10px;flex-wrap:wrap;margin-top:22px}
    .btn{display:inline-flex;justify-content:center;align-items:center;padding:12px 17px;border-radius:11px;text-decoration:none;font-weight:850;font-size:13px}
    .btn-primary{background:var(--lime);color:var(--dark)}.btn-light{background:#fff;color:var(--dark)}
    .hero-art{min-height:220px;border:1px solid #ffffff45;border-radius:24px;background:#ffffff16;display:grid;place-items:center;text-align:center;padding:24px}
    .hero-art .leaf{font-size:76px}.hero-art strong{display:block;font-size:21px;margin:5px 0}.hero-art span{font-size:12px;color:#d9f1df}
    .section{max-width:1160px;margin:auto;padding:52px 20px}
    .section-head{display:flex;justify-content:space-between;align-items:end;gap:18px;margin-bottom:22px}
    .section-kicker{color:var(--green);font-size:11px;font-weight:900;letter-spacing:1.4px;text-transform:uppercase}
    h2{font-size:clamp(25px,3vw,34px);letter-spacing:-.7px;margin:5px 0 0}
    .section-head p{margin:0;color:var(--muted);font-size:13px}
    .products{display:grid;grid-template-columns:repeat(3,minmax(0,1fr));gap:18px}
    .product{min-width:0;background:#fff;border:1px solid var(--line);border-radius:18px;overflow:hidden;box-shadow:0 5px 20px #14462d0a;display:flex;flex-direction:column}
    .product-image{height:210px;display:grid;place-items:center;position:relative;background:linear-gradient(145deg,#eaf7ef,#f8fbea);overflow:hidden}
    .product-image img{width:100%;height:100%;object-fit:contain;padding:12px;display:block}
    .placeholder{text-align:center;padding:16px;color:var(--green)}
    .placeholder b{display:block;font-size:55px;line-height:1.2}
    .placeholder span{font-size:10px;font-weight:900;letter-spacing:1px}
    .product-body{padding:17px;display:flex;flex-direction:column;flex:1}
    .product-tag{align-self:flex-start;color:var(--green);background:var(--mint);border-radius:99px;padding:4px 8px;font-size:10px;font-weight:900;text-transform:uppercase}
    .product h3{font-size:18px;line-height:1.3;margin:10px 0 6px}
    .product-desc{color:var(--muted);font-size:13px;line-height:1.65;min-height:62px}
    .product-bottom{display:flex;justify-content:space-between;align-items:center;gap:10px;margin-top:14px;flex-wrap:wrap}
    .price{font-size:17px;font-weight:950;color:var(--dark)}
    .product-actions{display:flex;gap:8px;flex-wrap:wrap}
    .add-btn{border-radius:9px;padding:10px 12px;font-size:12px}
    .detail-btn{border:1px solid #cfe2d5;background:#fff;color:var(--dark);border-radius:9px;padding:9px 11px;font-size:12px;font-weight:800}
    .how{background:var(--mint)}
    .how-inner{max-width:1160px;margin:auto;padding:40px 20px;display:grid;grid-template-columns:repeat(3,minmax(0,1fr));gap:15px}
    .step{background:#fff;border-radius:16px;padding:20px}
    .step b{display:grid;place-items:center;width:34px;height:34px;border-radius:10px;background:var(--lime);color:var(--dark)}
    .step h3{margin:12px 0 5px;font-size:16px}.step p{margin:0;color:var(--muted);font-size:13px;line-height:1.6}
    .checkout-layout{display:grid;grid-template-columns:.9fr 1.1fr;gap:18px;align-items:start}
    .panel{background:#fff;border:1px solid var(--line);border-radius:18px;padding:21px;box-shadow:0 5px 20px #14462d0a;min-width:0}
    .panel h3{margin:0 0 14px;font-size:18px}
    .empty{color:var(--muted);font-size:13px;padding:12px 0}
    .cart-row{display:grid;grid-template-columns:minmax(0,1fr) auto;gap:10px;padding:12px 0;border-bottom:1px solid var(--line)}
    .cart-row strong{display:block;font-size:13px}.cart-row small{color:var(--muted);font-size:11px}
    .qty{display:flex;align-items:center;gap:7px}.qty button{width:29px;height:29px;border:1px solid var(--line);border-radius:8px;background:#fff;color:var(--green);font-weight:900}
    .remove{border:0;background:transparent;color:#b34b4b;font-size:11px;padding:5px 0}
    .total{display:flex;justify-content:space-between;gap:10px;padding-top:16px;margin-top:7px;font-weight:950;font-size:16px}
    .discount-box{margin-top:16px;padding:14px;border:1px solid #dcebe0;border-radius:12px;background:#f8fcf9}
    .discount-box label{display:block;margin-bottom:8px}
    .discount-select{width:100%;border:1px solid #cfe2d5;border-radius:9px;padding:11px 12px;background:#fff;color:var(--ink);font-weight:750}
    .discount-row,.payable-row{display:flex;justify-content:space-between;gap:10px;padding-top:10px;font-size:13px}
    .discount-row{color:#b34b4b}
    .payable-row{margin-top:10px;padding-top:13px;border-top:1px dashed #cbded0;font-size:17px;font-weight:950;color:var(--dark)}
    .discount-hint{margin-top:6px;color:var(--muted);font-size:11px}
    .form-grid{display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:12px}
    .field{display:flex;flex-direction:column;gap:6px;min-width:0}.field.full{grid-column:1/-1}
    label{font-size:12px;font-weight:800;color:#385548}
    input,textarea{width:100%;min-width:0;border:1px solid #dce8df;border-radius:10px;padding:11px 12px;color:var(--ink);background:#fcfefc}
    input:focus,textarea:focus{outline:2px solid #16744730;border-color:var(--green)}
    textarea{resize:vertical;min-height:76px}
    .submit{width:100%;border-radius:11px;padding:14px;margin-top:16px}
    .hint{color:var(--muted);font-size:11px;line-height:1.55;margin-top:9px}
    footer{background:#0b3824;color:#d7eee0;padding:28px 18px;text-align:center;font-size:12px}
    footer strong{color:#fff;font-size:17px;letter-spacing:1px}
    .toast{position:fixed;left:50%;bottom:20px;transform:translate(-50%,120px);background:#173f2b;color:#fff;padding:12px 17px;border-radius:99px;font-size:13px;z-index:60;transition:transform .25s;box-shadow:var(--shadow);max-width:90vw;text-align:center}
    .toast.show{transform:translate(-50%,0)}
    .modal-backdrop{position:fixed;inset:0;background:#071d13a8;display:none;align-items:center;justify-content:center;padding:18px;z-index:80}
    .modal-backdrop.open{display:flex}
    .modal{background:#fff;border-radius:18px;max-width:520px;width:100%;max-height:85vh;overflow:auto;padding:22px;box-shadow:var(--shadow)}
    .modal-head{display:flex;justify-content:space-between;align-items:start;gap:12px}
    .modal h3{margin:0;font-size:21px}.modal-close{border:0;background:var(--mint);color:var(--dark);border-radius:9px;width:35px;height:35px;font-size:20px}
    .modal p{color:var(--muted);font-size:14px;line-height:1.7}
    .modal-note{padding:12px;border-radius:10px;background:var(--mint);font-size:12px;color:var(--dark)}

    .zoom-backdrop{position:fixed;inset:0;background:rgba(4,18,11,.94);display:none;align-items:center;justify-content:center;padding:18px;z-index:100}
    .zoom-backdrop.open{display:flex}
    .zoom-content{position:relative;width:min(96vw,900px);height:min(90vh,900px);display:flex;align-items:center;justify-content:center}
    .zoom-content img{display:block;max-width:100%;max-height:100%;width:auto;height:auto;object-fit:contain;border-radius:10px;background:#fff}
    .zoom-close{position:absolute;top:-10px;right:-5px;width:42px;height:42px;border:0;border-radius:50%;background:#fff;color:#123b28;font-size:28px;line-height:1;z-index:2;box-shadow:0 3px 16px #0005}
    .zoom-caption{position:absolute;bottom:-30px;left:0;right:0;text-align:center;color:#fff;font-size:13px;font-weight:700}
    [hidden]{display:none!important}
    /* Breakpoint dibuat lebih longgar agar browser HP yang memakai lebar layout desktop tetap nyaman. */
    @media(max-width:1100px){.products{grid-template-columns:repeat(2,minmax(0,1fr))}.nav-links{display:none}}
    @media(max-width:700px){
      .hero-inner{grid-template-columns:1fr;padding:38px 16px;gap:22px}
      .hero-art{min-height:165px}.hero-art .leaf{font-size:58px}
      .section{padding:38px 15px}.section-head{align-items:flex-start;flex-direction:column;gap:7px}
      .products{grid-template-columns:1fr;gap:14px}
      .product{display:grid;grid-template-columns: minmax(105px,34%) minmax(0,1fr);align-items:stretch}
      .product-image{height:100%;min-height:190px}
      .product-body{padding:13px}
      .product h3{font-size:16px}
      .product-desc{font-size:12px;min-height:0}
      .product-bottom{align-items:flex-start;flex-direction:column;margin-top:10px}
      .price{font-size:16px}
      .how-inner{grid-template-columns:1fr;padding:28px 15px}
      .checkout-layout{grid-template-columns:1fr}
      .panel{padding:16px}
      .nav{padding:10px 14px}.brand{font-size:19px}
      .cart-button{padding:9px 11px;font-size:12px}
    }
    /* Katalog 3 produk per baris, termasuk layar HP. Gambar utuh tanpa crop. */
    .products{grid-template-columns:repeat(3,minmax(0,1fr))}
    .product{display:flex;flex-direction:column;min-width:0}
    .product-image{height:190px;min-height:190px;width:100%;padding:8px}
    .product-image img{width:100%;height:100%;object-fit:contain;object-position:center;padding:4px}
    .product-body{padding:14px}
    .product-desc{min-height:0}
    @media(max-width:700px){
      .products{grid-template-columns:repeat(3,minmax(0,1fr));gap:9px}
      .product{display:flex;flex-direction:column}
      .product-image{height:115px;min-height:115px;padding:5px}
      .product-image img{object-fit:contain;padding:2px}
      .product-body{padding:9px}
      .product h3{font-size:12px;line-height:1.3;margin:7px 0 4px}
      .product-tag{font-size:8px;padding:3px 5px}
      .product-desc{font-size:10px;line-height:1.4;min-height:0}
      .product-bottom{display:flex;flex-direction:column;align-items:stretch;gap:7px;margin-top:9px}
      .price{font-size:11px}
      .product-actions{display:flex;flex-direction:column;gap:5px}
      .add-btn,.detail-btn{width:100%;padding:7px 4px;font-size:10px}
      .section{padding-left:10px;padding-right:10px}
      .section-head p{font-size:11px}
    }
    @media(max-width:390px){
      .products{grid-template-columns:repeat(3,minmax(0,1fr));gap:7px}
      .product-image{height:100px;min-height:100px}
      .product-body{padding:7px}
      .product h3{font-size:11px}
      .product-desc{font-size:9px}
      .price{font-size:10px}
      .form-grid{grid-template-columns:1fr}.field.full{grid-column:auto}
    }
  </style>
</head>
<body>
  <div class="topbar">Selamat datang di PINOZ Store • Pemesanan mudah melalui WhatsApp</div>
  <header>
    <nav class="nav">
      <a class="brand" href="#"><span class="brand-mark">✳</span> PINOZ</a>
      <div class="nav-links"><a href="#produk">Produk</a><a href="#cara-pesan">Cara Pemesanan</a><a href="#checkout">Checkout</a></div>
      <button class="cart-button" type="button" id="go-cart">🛒 Keranjang (<span id="cart-count">0</span>)</button>
    </nav>
  </header>

  <main>
    <section class="hero">
      <div class="hero-inner">
        <div>
          <span class="eyebrow">PINOZ • Solusi kebutuhan pertanian</span>
          <h1>Dukung pertanian<br>lebih produktif.</h1>
          <p>Temukan produk Pinoz untuk membantu memenuhi kebutuhan pertanian Anda. Pilih produk, lihat detailnya, masukkan ke keranjang, lalu kirim pesanan langsung melalui WhatsApp.</p>
          <div class="hero-actions"><a class="btn btn-primary" href="#produk">Lihat Produk</a><a class="btn btn-light" href="#cara-pesan">Cara Pemesanan</a></div>
        </div>
        <div class="hero-art"><div><div class="leaf">🌱</div><strong>Tumbuh • Rawat • Panen</strong><span>Mulai pemesanan produk Pinoz di sini</span></div></div>
      </div>
    </section>

    <section class="section" id="produk">
      <div class="section-head">
        <div><div class="section-kicker">Katalog pilihan</div><h2>Produk Pinoz</h2></div>
        <p>7 produk katalog • Tekan “Detail” untuk membaca keterangan produk.</p>
      </div>
      <div class="products" id="product-list" aria-live="polite"></div>
    </section>

    <section class="how" id="cara-pesan">
      <div class="how-inner">
        <div class="step"><b>01</b><h3>Pilih Produk</h3><p>Jelajahi katalog, baca detail produk, lalu tambahkan produk yang dibutuhkan ke keranjang.</p></div>
        <div class="step"><b>02</b><h3>Isi Data Customer</h3><p>Lengkapi nama, alamat, dan detail pesanan agar admin dapat memprosesnya.</p></div>
        <div class="step"><b>03</b><h3>Kirim via WhatsApp</h3><p>Periksa jumlah dan total pesanan, kemudian kirim ringkasan pesanan ke WhatsApp admin.</p></div>
      </div>
    </section>

    <section class="section" id="checkout">
      <div class="section-head"><div><div class="section-kicker">Selesaikan pesanan</div><h2>Keranjang & Data Customer</h2></div><p>Periksa pesanan sebelum dikirim.</p></div>
      <div class="checkout-layout">
        <div class="panel">
          <h3>🛒 Keranjang Belanja</h3>
          <div id="cart-items"><div class="empty">Keranjang masih kosong. Silakan pilih produk terlebih dahulu.</div></div>
          <div class="total"><span>Total Pesanan</span><span id="cart-total">Rp0</span></div>
          <div class="discount-box">
            <label for="discount-select">🎁 Pilih Diskon</label>
            <select class="discount-select" id="discount-select">
              <option value="0">Tanpa diskon (0%)</option>
              <option value="5">Diskon 5%</option>
              <option value="7">Diskon 7%</option>
              <option value="10">Diskon 10%</option>
            </select>
            <div class="discount-hint">Diskon dihitung otomatis dari total pesanan.</div>
            <div class="discount-row"><span>Potongan diskon</span><strong id="discount-amount">−Rp0</strong></div>
            <div class="payable-row"><span>Total Bayar</span><strong id="payable-total">Rp0</strong></div>
          </div>
        </div>
        <div class="panel">
          <h3>Data Customer</h3>
          <form id="order-form">
            <div class="form-grid">
              <div class="field full"><label for="customer-name">Nama lengkap *</label><input id="customer-name" name="name" required placeholder="Nama penerima"></div>
              <div class="field full"><label for="street">Nama jalan & nomor rumah *</label><input id="street" required placeholder="Contoh: Jl. Merdeka No. 10"></div>
              <div class="field"><label for="rt">RT *</label><input id="rt" required placeholder="001"></div>
              <div class="field"><label for="rw">RW *</label><input id="rw" required placeholder="002"></div>
              <div class="field"><label for="kelurahan">Kelurahan / Desa *</label><input id="kelurahan" required></div>
              <div class="field"><label for="kecamatan">Kecamatan *</label><input id="kecamatan" required></div>
              <div class="field"><label for="kota">Kabupaten / Kota *</label><input id="kota" required></div>
              <div class="field"><label for="kodepos">Kode Pos *</label><input id="kodepos" inputmode="numeric" required placeholder="5 digit"></div>
              <div class="field full"><label for="notes">Catatan pemesanan (opsional)</label><textarea id="notes" placeholder="Jumlah tambahan, patokan alamat, atau catatan lainnya"></textarea></div>
            </div>
            <button class="submit" type="submit">Kirim Pesanan via WhatsApp →</button>
            <div class="hint">WhatsApp akan terbuka dengan ringkasan pesanan. Pesanan diproses setelah dikonfirmasi admin.</div>
          </form>
        </div>
      </div>
    </section>
  </main>
  <footer><strong>PINOZ STORE</strong><p>Solusi kebutuhan pertanian Anda.</p><span>© <span id="year"></span> PINOZ Store. All rights reserved.</span></footer>
  <div class="toast" id="toast" role="status" aria-live="polite"></div>

  <div class="modal-backdrop" id="detail-modal" role="dialog" aria-modal="true" aria-labelledby="modal-title">
    <div class="modal">
      <div class="modal-head"><div><span class="section-kicker">Informasi produk</span><h3 id="modal-title">Detail Produk</h3></div><button class="modal-close" type="button" id="close-modal" aria-label="Tutup">×</button></div>
      <p id="modal-description"></p>
      <div class="modal-note">Catatan: manfaat, dosis, komposisi, dan cara penggunaan harus mengikuti label resmi produk. Lengkapi keterangan ini dengan informasi produk yang sebenarnya sebelum dipublikasikan.</div>
      <button class="add-btn" type="button" id="modal-add" style="margin-top:15px">+ Tambahkan ke Keranjang</button>
    </div>
  </div>


  <div class="zoom-backdrop" id="product-zoom" role="dialog" aria-modal="true" aria-label="Gambar produk ukuran penuh">
    <div class="zoom-content">
      <button class="zoom-close" type="button" id="zoom-close" aria-label="Tutup gambar">×</button>
      <img id="zoom-image" src="" alt="Gambar produk diperbesar">
      <div class="zoom-caption" id="zoom-caption">Ketuk di luar gambar atau tombol × untuk menutup</div>
    </div>
  </div>

  <script>
    "use strict";
    // Ganti nomor ini dengan nomor WhatsApp admin (format 62xxxxxxxxxx).
    const ADMIN_WA = "62881025173774";

    // Isi deskripsi berdasarkan label resmi produk. Jangan mencantumkan klaim/dosis yang belum diverifikasi.
    const PRODUCTS = [
      {id:1,name:"PINOZ Nutrisi Kompleks",category:"Nutrisi tanaman",price:120000,description:"Produk nutrisi kompleks untuk kebutuhan perawatan tanaman. Lengkapi keterangan komposisi, manfaat, dosis, dan cara aplikasi berdasarkan label resmi.",image:"https://cdn.phototourl.com/anon/2026-11-14-1e0f454f-147f-4998-8c73-488dc507ffa0.png",icon:"🌿"},
      {id:2,name:"PINOZ Booster Buah",category:"Perawatan tanaman",price:100000,description:"Produk dengan nama dagang Booster Buah. Tambahkan informasi fungsi, jenis tanaman sasaran, dosis, dan waktu aplikasi sesuai petunjuk resmi produk.",image:"",icon:"🌱"},
      {id:3,name:"PINOZ ZPT (Bio Hormon)",category:"ZPT",price:85000,description:"Produk kategori zat pengatur tumbuh sesuai penamaan produk. Lengkapi kandungan bahan aktif, sasaran penggunaan, dosis, dan cara aplikasi dari label resmi.",image:"",icon:"🌾"},
      {id:4,name:"PINOZ Super Serum",category:"Perawatan tanaman",price:100000,description:"Produk PINOZ Super Serum. Masukkan uraian manfaat, kandungan, tanaman sasaran, dan petunjuk penggunaan yang tercantum pada kemasan resmi.",image:"",icon:"🍃"},
      {id:5,name:"PINOZ Anti Virus",category:"Perlindungan tanaman",price:100000,description:"Produk dengan nama dagang Anti Virus. Pastikan keterangan fungsi, organisme sasaran, status/perizinan, dan cara penggunaan ditulis sesuai label resmi.",image:"",icon:"🪴"},
      {id:6,name:"PINOZ Suplemen Makro",category:"Nutrisi tanaman",price:150000,description:"Produk suplemen makro. Lengkapi daftar unsur/kandungan, manfaat, tanaman sasaran, dosis, dan cara aplikasi berdasarkan informasi resmi pada kemasan.",image:"",icon:"🌻"},
      {id:7,name:"PINOZ Booster Tanah",category:"Perawatan tanah",price:110000,description:"Produk dengan nama dagang Booster Tanah. Tambahkan informasi komposisi, fungsi, dosis, dan metode aplikasi sesuai label resmi produk.",image:"",icon:"🌻"}
    ];

    let cart = [];
    let selectedProductId = null;
    let toastTimer = null;
    const $ = id => document.getElementById(id);
    const rupiah = value => new Intl.NumberFormat("id-ID",{style:"currency",currency:"IDR",maximumFractionDigits:0}).format(value);

    function renderProducts(){
      const list = $("product-list");
      list.innerHTML = PRODUCTS.map(p => `
        <article class="product">
          <div class="product-image">
            ${p.image ? `<img src="${p.image}" alt="${escapeHTML(p.name)}" loading="lazy" decoding="async" tabindex="0" role="button" aria-label="Perbesar gambar ${escapeHTML(p.name)}" onclick="openProductZoom(${p.id})" onkeydown="if(event.key==='Enter'||event.key===' '){event.preventDefault();openProductZoom(${p.id})}" onerror="this.hidden=true;this.parentElement.querySelector('.placeholder').hidden=false">` : ""}
            <div class="placeholder" ${p.image ? "hidden" : ""}><b>${p.icon}</b><span>PINOZ • ${escapeHTML(p.category.toUpperCase())}</span></div>
          </div>
          <div class="product-body">
            <span class="product-tag">${escapeHTML(p.category)}</span>
            <h3>${escapeHTML(p.name)}</h3>
            <div class="product-desc">${escapeHTML(shortDescription(p.description))}</div>
            <div class="product-bottom">
              <span class="price">${p.price > 0 ? rupiah(p.price) : "Hubungi admin"}</span>
              <div class="product-actions">
                <button class="detail-btn" type="button" data-detail="${p.id}">Detail</button>
                <button class="add-btn" type="button" data-add="${p.id}">+ Keranjang</button>
              </div>
            </div>
          </div>
        </article>`).join("");
    }

    function openProductZoom(id){
      const product=PRODUCTS.find(p=>p.id===Number(id));
      if(!product || !product.image){showToast("Gambar produk belum tersedia");return;}
      $("zoom-image").src=product.image;
      $("zoom-image").alt=product.name;
      $("zoom-caption").textContent=product.name;
      $("product-zoom").classList.add("open");
      $("zoom-close").focus();
    }
    function closeProductZoom(){
      $("product-zoom").classList.remove("open");
      $("zoom-image").src="";
    }
    function shortDescription(text){return text.length > 115 ? text.slice(0,112).trim()+"…" : text;}
    function escapeHTML(value){return String(value).replace(/[&<>"']/g,ch=>({"&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#39;"}[ch]));}
    function showToast(message){
      $("toast").textContent=message;$("toast").classList.add("show");
      clearTimeout(toastTimer);toastTimer=setTimeout(()=>$("toast").classList.remove("show"),2200);
    }
    function addToCart(id){
      const product=PRODUCTS.find(p=>p.id===Number(id));if(!product)return;
      const existing=cart.find(item=>item.id===product.id);
      if(existing)existing.qty+=1;else cart.push({...product,qty:1});
      renderCart();showToast(product.name+" ditambahkan ke keranjang");
    }
    function changeQty(id,delta){
      const item=cart.find(p=>p.id===Number(id));if(!item)return;
      item.qty+=delta;if(item.qty<=0)cart=cart.filter(p=>p.id!==Number(id));
      renderCart();
    }
    function removeItem(id){cart=cart.filter(p=>p.id!==Number(id));renderCart();showToast("Produk dihapus dari keranjang");}
    function renderCart(){
      const container=$("cart-items");
      const count=cart.reduce((sum,item)=>sum+item.qty,0);
      const total=cart.reduce((sum,item)=>sum+item.price*item.qty,0);
      const discountRate=Number($("discount-select").value||0);
      const discountAmount=Math.round(total*discountRate/100);
      const payableTotal=total-discountAmount;
      $("cart-count").textContent=count;
      $("cart-total").textContent=rupiah(total);
      $("discount-amount").textContent="−"+rupiah(discountAmount);
      $("payable-total").textContent=rupiah(payableTotal);
      if(!cart.length){container.innerHTML='<div class="empty">Keranjang masih kosong. Silakan pilih produk terlebih dahulu.</div>';return;}
      container.innerHTML=cart.map(item=>`
        <div class="cart-row">
          <div><strong>${escapeHTML(item.name)}</strong><small>${rupiah(item.price)} / produk</small><br><button class="remove" type="button" data-remove="${item.id}">Hapus produk</button></div>
          <div class="qty"><button type="button" aria-label="Kurangi jumlah" data-qty="${item.id}" data-delta="-1">−</button><b>${item.qty}</b><button type="button" aria-label="Tambah jumlah" data-qty="${item.id}" data-delta="1">+</button></div>
        </div>`).join("");
    }
    function openDetails(id){
      const product=PRODUCTS.find(p=>p.id===Number(id));if(!product)return;
      selectedProductId=product.id;$("modal-title").textContent=product.name;
      $("modal-description").textContent=product.description+" Harga: "+rupiah(product.price)+".";
      $("detail-modal").classList.add("open");$("close-modal").focus();
    }
    function closeDetails(){$("detail-modal").classList.remove("open");selectedProductId=null;}
    $("product-list").addEventListener("click",event=>{
      const add=event.target.closest("[data-add]");const detail=event.target.closest("[data-detail]");
      if(add)addToCart(add.dataset.add);if(detail)openDetails(detail.dataset.detail);
    });
    $("cart-items").addEventListener("click",event=>{
      const qty=event.target.closest("[data-qty]");const remove=event.target.closest("[data-remove]");
      if(qty)changeQty(qty.dataset.qty,Number(qty.dataset.delta));if(remove)removeItem(remove.dataset.remove);
    });
    $("discount-select").addEventListener("change",renderCart);
    $("go-cart").addEventListener("click",()=>$("checkout").scrollIntoView({behavior:"smooth"}));

    $("zoom-close").addEventListener("click",closeProductZoom);
    $("product-zoom").addEventListener("click",event=>{if(event.target===$("product-zoom"))closeProductZoom();});
    $("close-modal").addEventListener("click",closeDetails);
    $("modal-add").addEventListener("click",()=>{if(selectedProductId!==null)addToCart(selectedProductId);closeDetails();});
    $("detail-modal").addEventListener("click",event=>{if(event.target===$("detail-modal"))closeDetails();});
    document.addEventListener("keydown",event=>{if(event.key==="Escape"){closeDetails();closeProductZoom();}});

    $("order-form").addEventListener("submit",event=>{
      event.preventDefault();
      if(!cart.length){alert("Keranjang masih kosong. Silakan pilih produk terlebih dahulu.");$("produk").scrollIntoView({behavior:"smooth"});return;}
      if(!/^[0-9]{9,15}$/.test(ADMIN_WA)){alert("Nomor WhatsApp admin belum benar. Periksa variabel ADMIN_WA.");return;}
      const value=id=>$(id).value.trim();
      const total=cart.reduce((sum,item)=>sum+item.price*item.qty,0);
      const discountRate=Number($("discount-select").value||0);
      const discountAmount=Math.round(total*discountRate/100);
      const payableTotal=total-discountAmount;
      const orderLines=cart.map(item=>`- ${item.name} x ${item.qty} | ${rupiah(item.price*item.qty)}`).join("\n");
      const message=[
        "*PESANAN BARU - PINOZ STORE*","",
        "*DATA CUSTOMER*",
        `Nama      : ${value("customer-name")}`,
        `Alamat       : ${value("street")}`,
        `RT/RW       : ${value("rt")}/${value("rw")}`,
        `Kelurahan/Desa: ${value("kelurahan")}`,
        `Kecamatan     : ${value("kecamatan")}`,
        `Kabupaten/Kota: ${value("kota")}`,
        `Kode Pos       : ${value("kodepos")}`,"",
        "*DETAIL PESANAN*",orderLines,"",
        `*TOTAL PESANAN: ${rupiah(total)}*`,
        `Diskon: ${discountRate}%`,
        `Potongan Diskon: -${rupiah(discountAmount)}`,
        `*TOTAL BAYAR: ${rupiah(payableTotal)}*`,
        `Catatan: ${value("notes")||"-"}`,"",
        "Mohon konfirmasi ketersediaan produk dan ongkos kirim. Terima kasih."
      ].join("\n");
      const url="https://wa.me/"+ADMIN_WA+"?text="+encodeURIComponent(message);
      window.open(url,"_blank","noopener,noreferrer");
    });
    $("year").textContent=new Date().getFullYear();
    renderProducts();renderCart();
  </script>
</body>
</html>
