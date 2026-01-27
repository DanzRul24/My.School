<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Portal Informasi Sekolah</title>
  <style>
    html { scroll-behavior: smooth; }
    body {
      margin: 0;
      font-family: 'Poppins', sans-serif;
      background-color: #f0f2f5;
      color: #333;
      transition: background 0.3s, color 0.3s;
    }
    header {
      background-color: #2c3e50;
      color: white;
      padding: 1rem 2rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    nav a {
      color: white;
      margin: 0 1rem;
      text-decoration: none;
      font-weight: 500;
    }
    .user-area {
      display: flex;
      align-items: center;
      gap: 10px;
      font-weight: 500;
    }
    #darkToggle {
      background: #2c3e50;
      color: white;
      border: none;
      padding: 6px 10px;
      border-radius: 6px;
      cursor: pointer;
      transition: background 0.3s;
    }
    #darkToggle:hover { background: #1a252f; }
    .welcome {
      background-color: #34495e;
      color: white;
      padding: 2rem;
      text-align: center;
    }
    .stats {
      display: flex;
      justify-content: space-around;
      background-color: white;
      margin: 1rem;
      padding: 1rem;
      border-radius: 8px;
      box-shadow: 0 2px 4px rgba(0,0,0,0.1);
    }
    .stat { text-align: center; }
    .section {
      background-color: white;
      margin: 1rem;
      padding: 1.5rem;
      border-radius: 8px;
      box-shadow: 0 2px 4px rgba(0,0,0,0.05);
      transition: transform 0.2s;
    }
    .section:hover { transform: scale(1.02); }
    .section h2 { margin-bottom: 1rem; color: #2c3e50; }
    .item {
      display: flex;
      align-items: flex-start;
      gap: 15px;
      margin-bottom: 1rem;
      padding-bottom: 0.5rem;
      border-bottom: 1px solid #eee;
    }
    .item img {
      width: 100px;
      height: 70px;
      object-fit: cover;
      border-radius: 6px;
    }
    .item-content {
      flex: 1;
    }
    footer {
      background-color: #2c3e50;
      color: white;
      padding: 2rem;
      text-align: center;
    }
    .social-icons img { width: 24px; margin: 0 0.5rem; }
    /* Mode Gelap */
    body.dark {
      background-color: #1e1e1e;
      color: #ddd;
    }
    body.dark .section, body.dark .stats {
      background-color: #2c2c2c;
      color: #ddd;
    }
    body.dark .item img { opacity: 0.8; }
    /* Scroll-to-top button */
    #topBtn {
      position: fixed;
      bottom: 20px;
      right: 20px;
      background: #2c3e50;
      color: white;
      border: none;
      padding: 10px 15px;
      border-radius: 50%;
      cursor: pointer;
      display: none;
    }
  </style>
</head>
<body>

  <header>
    <div><strong>Portal Sekolah</strong></div>
    <nav>
      <a href="#beranda">Beranda</a>
      <a href="#pengumuman">Pengumuman</a>
      <a href="#agenda">Agenda</a>
      <a href="#berita">Berita</a>
    </nav>
    <div class="user-area">
      <span>Halo, labib!</span>
      <button id="darkToggle" onclick="toggleDark()">🌙</button>
    </div>
  </header>

  <section class="welcome" id="beranda">
    <h1>Selamat Datang di Portal Informasi Sekolah</h1>
    <p>Temukan informasi terbaru seputar sekolah, pengumuman, agenda, dan berita</p>
  </section>

  <section class="stats">
    <div class="stat"><h3>500</h3><p>Siswa</p></div>
    <div class="stat"><h3>50</h3><p>Guru</p></div>
    <div class="stat"><h3>5</h3><p>Pengumuman</p></div>
    <div class="stat"><h3>30</h3><p>Kelas</p></div>
  </section>

  <section class="section" id="pengumuman">
    <h2>Pengumuman Terbaru</h2>
    <div class="item">
      <img src="ppdb.jpg" alt="PPDB">
      <div class="item-content"><strong>Penerimaan Siswa Baru 2026/2027</strong><br/>Info PPDB<br/><em>1 Januari 2026</em></div>
    </div>
    <div class="item">
      <img src="idulfitri.jpg" alt="Idul Fitri">
      <div class="item-content"><strong>Libur Hari Raya Idul Fitri</strong><br/>15 Feb - 15 Mar<br/><em>15 Februari 2026</em></div>
    </div>
    <div class="item">
      <img src="iduladha.jpg" alt="Idul Adha">
      <div class="item-content"><strong>Libur Hari Raya Idul Adha</strong><br/>10 Apr - 30 Apr<br/><em>10 April 2026</em></div>
    </div>
  </section>

  <section class="section" id="agenda">
    <h2>Agenda Sekolah</h2>
    <div class="item">
      <img src="rapat.jpg" alt="Rapat">
      <div class="item-content">20 Juni: Rapat Wali Kelas (09:00)</div>
    </div>
    <div class="item">
      <img src="upacara.jpg" alt="Upacara">
      <div class="item-content">25 Mei: Upacara Hari Senin (07:00)</div>
    </div>
    <div class="item">
      <img src="ujian.jpg" alt="Ujian">
      <div class="item-content">12 Juli: Ujian Akhir Semester Genap (07:00)</div>
    </div>
  </section>

  <section class="section" id="berita">
    <h2>Berita Terbaru</h2>
    <select id="filter" onchange="filterNews()">
      <option value="all">Semua</option>
      <option value="akademik">Akademik</option>
      <option value="event">Event</option>
      <option value="ekstra">Ekstrakurikuler</option>
    </select>
    <div class="item" data-cat="ekstra">
      <img src="ekstra.jpg" alt="Ekstra">
      <div class="item-content">Ekstra Kulikuler, Membuat Siswa Berkembang (22 Apr 2026)</div>
    </div>
    <div class="item" data-cat="akademik">
      <img src="belajar.jpg" alt="Belajar">
      <div class="item-content">Tips Efektif Belajar Menghadapi Ujian (24 Juni 2026)</div>
    </div>
    <div class="item" data-cat="akademik">
      <img src="online.jpg" alt="Online">
      <div class="item-content">Siswa Belajar Online (30 Juni 2026)</div>
    </div>
    <div class="item" data-cat="event">
      <img src="perlombaan.jpg" alt="Perlombaan">
      <div class="item-content">Event Sekolah: Perlombaan Siswa (10 Desember 2026)</div>
    </div>
    <div class="item" data-cat="event">
      <img src="kemerdekaan.jpg" alt="Kemerdekaan">
      <div class="item-content">Upacara Kemerdekaan 17 Agustus (16 Agustus 2026)</div>
    </div>

  </section>

  <footer>
    <h3>Alamat Sekolah</h3>
    <p>Prambatan Lor No.679, Kaliwungu Kudus<br/>(0291) 434330 | info@sekolah.ac.id</p>
    <div class="social-icons">
      <img src="instagram.png" alt="Instagram" />
      <img src="twitter.png" alt="Twitter" />
      <img src="email.png" alt="Email" />
    </div>
  </footer>

  <button id="topBtn" onclick="scrollTopFunc()">↑</button>

  <script>
    // Mode Gelap/Terang dengan ikon dinamis
    function toggleDark() {
      document.body.classList.toggle("dark");
      const btn = document.getElementById("darkToggle");
      if (document.body.classList.contains("dark")) {
        btn.textContent = "☀️";
      } else {
        btn.textContent = "🌙";
      }
    }
    // Scroll-to-top
    window.onscroll = function() {
      document.getElementById("topBtn").style.display =
        document.documentElement.scrollTop > 200 ? "block" : "none";
    };
    function scrollTopFunc() {
      document.documentElement.scrollTop = 0;
    }
    // Filter Berita
    function filterNews() {
      let val = document.getElementById("filter").value;
      document.querySelectorAll("#berita .item").forEach(item => {
        item.style.display = (val === "all" || item.dataset.cat === val) ? "block" : "none";
      });
    }
  </script>

</body>
</html>
