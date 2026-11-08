<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="PINOZ Store - katalog produk dan pemesanan produk pertanian secara mudah melalui WhatsApp.">
  <title>PINOZ Store | Belanja Produk Pertanian</title>
  <style>
    :root {
      --green: #167447; --green-dark: #0c4f31; --mint: #eaf7ef;
      --lime: #b9e769; --ink: #183329; --muted: #687b71;
      --line: #e3ece6; --white: #fff; --bg: #f7faf7;
      --shadow: 0 14px 38px rgba(18, 65, 42, .09);
    }
    * { box-sizing: border-box; }
    html { scroll-behavior: smooth; }
    body { margin: 0; font-family: Inter, ui-sans-serif, system-ui, -apple-system, Segoe UI, sans-serif; color: var(--ink); background: var(--bg); }
    button, input, textarea { font: inherit; }
    button { cursor: pointer; }
    .topbar { background: var(--green-dark); color: #e9fff1; text-align: center; padding: 9px 16px; font-size: 12px; letter-spacing: .3px; }
    header { position: sticky; top: 0; z-index: 20; background: rgba(255,255,255,.94); backdrop-filter: blur(12px); border-bottom: 1px solid var(--line); }
    .nav { max-width: 1160px; margin: auto; padding: 15px 22px; display: flex; align-items: center; justify-content: space-between; gap: 16px; }
    .brand { display: flex; align-items: center; gap: 10px; font-weight: 900; font-size: 23px; letter-spacing: 1px; color: var(--green-dark); text-decoration: none; }
    .brand-mark { width: 38px; height: 38px; border-radius: 13px; display: grid; place-items: center; color: var(--green-dark); background: var(--lime); font-size: 20px; }
    .nav-links { display: flex; gap: 25px; align-items: center; }
    .nav-links a { color: var(--ink); text-decoration: none; font-size: 14px; font-weight: 650; }
    .cart-button { border: 0; border-radius: 999px; background: var(--green); color: white; padding: 11px 17px; font-weight: 750; }
    .hero { overflow: hidden; background: radial-gradient(circle at 85% 20%, rgba(185,231,105,.32), transparent 28%), linear-gradient(120deg, #0c4f31, #167447 62%, #2b8c5a); color: white; }
    .hero-inner { max-width: 1160px; margin: auto; padding: 76px 22px 82px; display: grid; grid-template-columns: 1.15fr .85fr; align-items: center; gap: 40px; }
    .eyebrow { display: inline-flex; padding: 7px 12px; border-radius: 999px; background: rgba(255,255,255,.13); color: #e9ffd2; font-size: 12px; font-weight: 800; letter-spacing: 1px; text-transform: uppercase; }
    h1 { margin: 18px 0 14px; font-size: clamp(38px, 5vw, 61px); line-height: 1.05; letter-spacing: -2px; }
    .hero p { max-width: 560px; color: #e1f3e8; line-height: 1.75; font-size: 16px; }
    .hero-actions { display: flex; gap: 12px; flex-wrap: wrap; margin-top: 27px; }
    .btn-primary, .btn-light { display: inline-flex; align-items: center; justify-content: center; border: 0; border-radius: 12px; padding: 14px 20px; font-weight: 800; text-decoration: none; }
    .btn-primary { background: var(--lime); color: var(--green-dark); }
    .btn-light { background: white; color: var(--green-dark); }
    .hero-art { min-height: 280px; border: 1px solid rgba(255,255,255,.25); border-radius: 28px; background: rgba(255,255,255,.10); display: grid; place-items: center; padding: 28px; text-align: center; }
    .hero-art .leaf { font-size: 100px; filter: drop-shadow(0 15px 18px rgba(0,0,0,.15)); }
    .hero-art strong { display: block; font-size: 23px; margin-top: 8px; }
    .hero-art span { color: #d9f1df; font-size: 13px; }
    .section { max-width: 1160px; margin: auto; padding: 65px 22px; }
    .section-head { display: flex; align-items: end; justify-content: space-between; gap: 20px; margin-bottom: 25px; }
    .section-kicker { color: var(--green); font-size: 12px; font-weight: 850; letter-spacing: 1.4px; text-transform: uppercase; }
    h2 { font-size: clamp(27px, 3vw, 36px); letter-spacing: -1px; margin: 8px 0 0; }
    .section-head p { color: var(--muted); margin: 0; font-size: 14px; }
    .products { display: grid; grid-template-columns: repeat(3, 1fr); gap: 20px; }
    .product { background: white; border: 1px solid var(--line); border-radius: 20px; overflow: hidden; box-shadow: 0 5px 20px rgba(20,70,45,.04); transition: transform .2s, box-shadow .2s; }
    .product:hover { transform: translateY(-4px); box-shadow: var(--shadow); }
    .product-image { height: 205px; display: grid; place-items: center; background: linear-gradient(145deg, #eaf7ef, #f8fbea); color: var(--green); position: relative; }
    .product-image img { width: 100%; height: 100%; object-fit: cover; }
    .product-image .placeholder { text-align: center; padding: 18px; }
    .product-image .placeholder b { display: block; font-size: 54px; }
    .product-image .placeholder span { font-size: 12px; font-weight: 800; letter-spacing: 1px; }
    .product-body { padding: 19px; }
    .product-tag { color: var(--green); background: var(--mint); display: inline-block; border-radius: 99px; padding: 5px 9px; font-size: 10px; font-weight: 850; text-transform: uppercase; letter-spacing: .6px; }
    .product h3 { margin: 12px 0 7px; font-size: 19px; }
    .product-desc { color: var(--muted); font-size: 13px; line-height: 1.6; min-height: 42px; }
    .product-bottom { display: flex; justify-content: space-between; align-items: center; gap: 12px; margin-top: 17px; }
    .price { font-weight: 900; color: var(--green-dark); font-size: 18px; }
    .add-btn { border: 0; border-radius: 10px; background: var(--green); color: white; padding: 11px 14px; font-size: 12px; font-weight: 800; }
    .how { background: var(--mint); }
    .how-inner { max-width: 1160px; margin: auto; padding: 48px 22px; display: grid; grid-template-columns: repeat(3,1fr); gap: 18px; }
    .step { background: white; border-radius: 17px; padding: 23px; }
    .step b { display: grid; place-items: center; width: 35px; height: 35px; border-radius: 11px; background: var(--lime); color: var(--green-dark); }
    .step h3 { margin: 14px 0 6px; font-size: 16px; }
    .step p { margin: 0; color: var(--muted); font-size: 13px; line-height: 1.6; }
    .checkout-layout { display: grid; grid-template-columns: .9fr 1.1fr; gap: 22px; align-items: start; }
    .panel { background: white; border: 1px solid var(--line); border-radius: 20px; padding: 24px; box-shadow: 0 5px 20px rgba(20,70,45,.04); }
    .panel h3 { margin: 0 0 17px; font-size: 19px; }
    .empty { color: var(--muted); font-size: 14px; padding: 15px 0; }
    .cart-row { display: grid; grid-template-columns: 1fr auto; gap: 12px; padding: 14px 0; border-bottom: 1px solid var(--line); }
    .cart-row strong { display: block; font-size: 14px; }
    .cart-row small { color: var(--muted); }
    .qty { display: flex; align-items: center; gap: 9px; }
    .qty button { width: 27px; height: 27px; border: 1px solid var(--line); border-radius: 8px; background: white; color: var(--green); font-weight: 900; }
    .remove { border: 0; background: transparent; color: #b34b4b; font-size: 11px; padding: 5px 0; }
    .total { display: flex; justify-content: space-between; padding-top: 18px; margin-top: 8px; font-weight: 900; font-size: 17px; }
    .form-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 13px; }
    .field { display: flex; flex-direction: column; gap: 7px; }
    .field.full { grid-column: 1 / -1; }
    label { font-size: 12px; font-weight: 800; color: #385548; }
    input, textarea { width: 100%; border: 1px solid #dce8df; border-radius: 10px; padding: 12px 13px; outline: none; color: var(--ink); background: #fcfefc; }
    input:focus, textarea:focus { border-color: var(--green); box-shadow: 0 0 0 3px rgba(22,116,71,.09); }
    textarea { resize: vertical; min-height: 75px; }
    .submit { width: 100%; border: 0; border-radius: 12px; background: #20a45a; color: white; padding: 15px; margin-top: 18px; font-weight: 900; }
    .hint { color: var(--muted); font-size: 11px; line-height: 1.55; margin-top: 10px; }
    footer { background: #0b3824; color: #d7eee0; padding: 30px 22px; text-align: center; font-size: 12px; }
    footer strong { color: white; font-size: 17px; letter-spacing: 1px; }
    .toast { position: fixed; bottom: 20px; left: 50%; transform: translateX(-50%) translateY(100px); background: #173f2b; color: white; padding: 12px 18px; border-radius: 99px; font-size: 13px; z-index: 50; transition: .25s; box-shadow: var(--shadow); }
    .toast.show { transform: translateX(-50%) translateY(0); }
    @media (max-width: 800px) {
      .hero-inner { grid-template-columns: 1fr; padding-top: 55px; }
      .hero-art { min-height: 210px; }
      .products { grid-template-columns: repeat(2,1fr); }
      .checkout-layout { grid-template-columns: 1fr; }
      .nav-links { display: none; }
    }
    @media (max-width: 540px) {
      .products, .how-inner { grid-template-columns: 1fr; }
      .section { padding: 48px 16px; }
      .hero-inner { padding: 48px 17px; }
      .section-head { align-items: start; flex-direction: column; }
      .form-grid { grid-template-columns: 1fr; }
      .field.full { grid-column: auto; }
      .nav { padding: 12px 16px; }
    }
  </style>
</head>
<body>
  <div class="topbar">Selamat datang di PINOZ Store • Pemesanan mudah melalui WhatsApp</div>
  <header>
    <nav class="nav">
      <a class="brand" href="#"><span class="brand-mark">✳</span> PINOZ</a>
      <div class="nav-links">
        <a href="#produk">Produk</a><a href="#cara-pesan">Cara Pemesanan</a><a href="#checkout">Checkout</a>
      </div>
      <button class="cart-button" onclick="document.querySelector('#checkout').scrollIntoView({behavior:'smooth'})">🛒 Keranjang (<span id="cart-count">0</span>)</button>
    </nav>
  </header>

  <main>
    <section class="hero">
      <div class="hero-inner">
        <div>
          <span class="eyebrow">PINOZ • Solusi kebutuhan pertanian</span>
          <h1>Dukung pertanian<br>lebih produktif.</h1>
          <p>Temukan produk Pinoz untuk membantu memenuhi kebutuhan pertanian Anda. Pilih produk, masukkan ke keranjang, lalu kirim pesanan langsung melalui WhatsApp.</p>
          <div class="hero-actions">
            <a class="btn-primary" href="#produk">Lihat Produk</a>
            <a class="btn-light" href="#cara-pesan">Cara Pemesanan</a>
          </div>
        </div>
        <div class="hero-art">
          <div><div class="leaf">🌱</div><strong>Tumbuh • Rawat • Panen</strong><span>Mulai pemesanan produk Pinoz di sini</span></div>
        </div>
      </div>
    </section>

    <section class="section" id="produk">
      <div class="section-head">
        <div><div class="section-kicker">Katalog pilihan</div><h2>Produk Pinoz</h2></div>
        <p>6 contoh produk sudah tersedia. Nama, foto, dan harga masih contoh.</p>
      </div>
      <div class="products" id="product-list"></div>
    </section>

    <section class="how" id="cara-pesan">
      <div class="how-inner">
        <div class="step"><b>01</b><h3>Pilih Produk</h3><p>Jelajahi katalog dan tambahkan produk yang dibutuhkan ke keranjang.</p></div>
        <div class="step"><b>02</b><h3>Isi Data Customer</h3><p>Lengkapi nama, alamat, dan detail pesanan agar admin dapat memprosesnya.</p></div>
        <div class="step"><b>03</b><h3>Kirim via WhatsApp</h3><p>Tekan tombol pesan. Rincian pesanan akan disiapkan otomatis di WhatsApp.</p></div>
      </div>
    </section>

    <section class="section" id="checkout">
      <div class="section-head">
        <div><div class="section-kicker">Selesaikan pesanan</div><h2>Keranjang & Data Customer</h2></div>
        <p>Periksa pesanan sebelum dikirim.</p>
      </div>
      <div class="checkout-layout">
        <div class="panel">
          <h3>🛒 Keranjang Belanja</h3>
          <div id="cart-items"><div class="empty">Keranjang masih kosong. Silakan pilih produk terlebih dahulu.</div></div>
          <div class="total"><span>Total Pesanan</span><span id="cart-total">Rp0</span></div>
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
            <div class="hint">Dengan menekan tombol ini, website akan membuka WhatsApp dengan ringkasan pesanan. Pesanan baru diproses setelah dikonfirmasi oleh admin.</div>
          </form>
        </div>
      </div>
    </section>
  </main>

  <footer><strong>PINOZ STORE</strong><p>Solusi kebutuhan pertanian Anda.</p><span>© <span id="year"></span> PINOZ Store. All rights reserved.</span></footer>
  <div class="toast" id="toast">Produk ditambahkan ke keranjang</div>

  <script>
    /*
      PENGATURAN TOKO:
      1. Ganti nomor WhatsApp di bawah dengan nomor admin.
         Format: kode negara + nomor, tanpa +, spasi, atau tanda hubung.
         Contoh Indonesia: 6281234567890
      2. Edit daftar produk di PRODUCTS: nama, harga, deskripsi, kategori, dan gambar.
      3. Harga harus berupa angka tanpa titik/koma. Contoh Rp25.000 ditulis 25000.
    */
    const ADMIN_WA = "62881025173774"; // WAJIB GANTI DENGAN NOMOR WHATSAPP ADMIN

    const PRODUCTS = [
      { id: 1, name: "PINOZ Nutrisi Daun", category: "Contoh katalog", price: 25000,
        description: "Contoh tampilan produk. Ganti deskripsi sesuai informasi pada label resmi.", image: "", icon: "🌿" },
      { id: 2, name: "PINOZ Perangsang Akar", category: "Contoh katalog", price: 30000,
        description: "Contoh item katalog untuk kebutuhan perawatan tanaman. Detail produk perlu disesuaikan.", image: "", icon: "🌱" },
      { id: 3, name: "PINOZ Booster Tanaman", category: "Contoh katalog", price: 35000,
        description: "Contoh tampilan produk. Cantumkan manfaat dan petunjuk sesuai kemasan resmi.", image: "", icon: "🌾" },
      { id: 4, name: "PINOZ Nutrisi Buah", category: "Contoh katalog", price: 40000,
        description: "Contoh item katalog. Silakan ubah nama, keterangan, dan harga sesuai produk asli.", image: "", icon: "🍃" },
      { id: 5, name: "PINOZ Perawatan Tanaman", category: "Contoh katalog", price: 45000,
        description: "Contoh tampilan katalog untuk produk Pinoz lainnya. Informasi masih berupa contoh.", image: "", icon: "🪴" },
      { id: 6, name: "PINOZ Paket Pertanian", category: "Contoh katalog", price: 55000,
        description: "Contoh paket produk. Sesuaikan isi paket, harga, dan deskripsi sebelum dipublikasikan.", image: "", icon: "🌻" }
    ];

    let cart = [];
    const rupiah = value => new Intl.NumberFormat("id-ID", {
      style: "currency", currency: "IDR", maximumFractionDigits: 0
    }).format(value);

    function renderProducts() {
      const list = document.getElementById("product-list");
      list.innerHTML = PRODUCTS.map(p => `
        <article class="product">
          <div class="product-image">
            ${p.image
              ? `<img src="${p.image}" alt="${p.name}" onerror="this.style.display='none';this.nextElementSibling.style.display='block'">`
              : ""}
            <div class="placeholder" ${p.image ? 'style="display:none"' : ""}><b>${p.icon || "🌿"}</b><span>PINOZ • CONTOH KATALOG</span></div>
          </div>
          <div class="product-body">
            <span class="product-tag">${p.category}</span>
            <h3>${p.name}</h3>
            <div class="product-desc">${p.description}</div>
            <div class="product-bottom">
              <span class="price">${p.price > 0 ? rupiah(p.price) : "Hubungi admin"}</span>
              <button class="add-btn" onclick="addToCart(${p.id})">+ Keranjang</button>
            </div>
          </div>
        </article>`).join("");
    }

    function addToCart(id) {
      const product = PRODUCTS.find(p => p.id === id);
      const found = cart.find(item => item.id === id);
      if (found) found.qty++;
      else cart.push({ ...product, qty: 1 });
      renderCart();
      showToast(product.name + " ditambahkan");
    }

    function changeQty(id, amount) {
      const item = cart.find(p => p.id === id);
      if (!item) return;
      item.qty += amount;
      if (item.qty <= 0) cart = cart.filter(p => p.id !== id);
      renderCart();
    }

    function removeItem(id) {
      cart = cart.filter(p => p.id !== id);
      renderCart();
    }

    function renderCart() {
      const container = document.getElementById("cart-items");
      const count = cart.reduce((sum, item) => sum + item.qty, 0);
      const total = cart.reduce((sum, item) => sum + item.price * item.qty, 0);
      document.getElementById("cart-count").textContent = count;
      document.getElementById("cart-total").textContent = rupiah(total);

      if (!cart.length) {
        container.innerHTML = '<div class="empty">Keranjang masih kosong. Silakan pilih produk terlebih dahulu.</div>';
        return;
      }
      container.innerHTML = cart.map(item => `
        <div class="cart-row">
          <div><strong>${item.name}</strong><small>${item.price > 0 ? rupiah(item.price) : "Harga dikonfirmasi admin"} / produk</small><br>
            <button class="remove" onclick="removeItem(${item.id})">Hapus produk</button></div>
          <div class="qty"><button type="button" onclick="changeQty(${item.id},-1)">−</button><b>${item.qty}</b><button type="button" onclick="changeQty(${item.id},1)">+</button></div>
        </div>`).join("");
    }

    function showToast(message) {
      const toast = document.getElementById("toast");
      toast.textContent = message;
      toast.classList.add("show");
      clearTimeout(window.toastTimer);
      window.toastTimer = setTimeout(() => toast.classList.remove("show"), 2100);
    }

    document.getElementById("order-form").addEventListener("submit", function(event) {
      event.preventDefault();
      if (!cart.length) {
        alert("Keranjang masih kosong. Silakan pilih produk terlebih dahulu.");
        document.getElementById("produk").scrollIntoView({ behavior: "smooth" });
        return;
      }
      if (ADMIN_WA === "6281234567890" || !/^[0-9]{9,15}$/.test(ADMIN_WA)) {
        alert("Admin perlu mengatur nomor WhatsApp toko terlebih dahulu pada variabel ADMIN_WA di dalam file index.html.");
        return;
      }

      const value = id => document.getElementById(id).value.trim();
      const total = cart.reduce((sum, item) => sum + item.price * item.qty, 0);
      const orderLines = cart.map(item =>
        `- ${item.name} x ${item.qty} | ${item.price > 0 ? rupiah(item.price * item.qty) : "Harga konfirmasi admin"}`
      ).join("\n");

      const message = [
        "*PESANAN BARU - PINOZ STORE*",
        "",
        "*DATA CUSTOMER*",
        `Nama: ${value("customer-name")}`,
        `Alamat: ${value("street")}`,
        `RT/RW: ${value("rt")}/${value("rw")}`,
        `Kelurahan/Desa: ${value("kelurahan")}`,
        `Kecamatan: ${value("kecamatan")}`,
        `Kabupaten/Kota: ${value("kota")}`,
        `Kode Pos: ${value("kodepos")}`,
        "",
        "*DETAIL PEMESANAN*",
        orderLines,
        "",
        `*TOTAL: ${total > 0 ? rupiah(total) : "Menunggu konfirmasi harga admin"}*`,
        `Catatan: ${value("notes") || "-"}`,
        "",
        "Mohon konfirmasi ketersediaan produk dan ongkos kirim. Terima kasih."
      ].join("\n");

      const url = `https://wa.me/${ADMIN_WA}?text=${encodeURIComponent(message)}`;
      window.open(url, "_blank", "noopener,noreferrer");
    });

    document.getElementById("year").textContent = new Date().getFullYear();
    renderProducts();
    renderCart();
  </script>
</body>
</html>
