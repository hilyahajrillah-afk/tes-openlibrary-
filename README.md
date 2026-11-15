<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Open Library Latihan</title>
  <style>
    body { font-family: Arial, sans-serif; margin: 0; background: #fffaf0; color: #333; }
    header { background: #f59e0b; color: #fff; padding: 24px 16px; text-align: center; }
    main { max-width: 900px; margin: 0 auto; padding: 16px; }
    .filter button { margin: 4px; padding: 8px 14px; border: 0; border-radius: 20px; background: #fde68a; cursor: pointer; }
    .filter button.aktif { background: #d97706; color: #fff; }
    .kartu-wadah { display: grid; grid-template-columns: repeat(auto-fit, minmax(240px, 1fr)); gap: 16px; margin-top: 16px; }
    .kartu { background: #fff; border-radius: 12px; padding: 16px; box-shadow: 0 2px 6px rgba(0,0,0,.1); }
    .kartu a { display: inline-block; margin-top: 8px; color: #b45309; font-weight: bold; }
    footer { text-align: center; padding: 16px; font-size: 14px; }
  </style>
</head>
<body>
  <header>
    <h1>Open Library Latihan</h1>
    <p>Katalog bacaan anak dan remaja. Tanpa akun, tanpa iklan.</p>
  </header>
  <main>
    <div class="filter">
      <button class="aktif" data-usia="semua">Semua usia</button>
      <button data-usia="3-8">3-8 tahun</button>
      <button data-usia="9-12">9-12 tahun</button>
      <button data-usia="13-17">13-17 tahun</button>
    </div>
    <div class="kartu-wadah">
      <div class="kartu" data-usia="3-8">
        <h3>Cerita Contoh 1</h3>
        <p>Dongeng · 3-8 tahun · Bahasa Indonesia</p>
        <p>Ringkasan singkat cerita contoh pertama.</p>
        <a href="https://www.google.com">Baca di Sumber Asli</a>
      </div>
      <div class="kartu" data-usia="9-12">
        <h3>Cerita Contoh 2</h3>
        <p>Cerita rakyat · 9-12 tahun · Bahasa Indonesia</p>
        <p>Ringkasan singkat cerita contoh kedua.</p>
        <a href="https://www.google.com">Baca di Sumber Asli</a>
      </div>
      <div class="kartu" data-usia="13-17">
        <h3>Cerita Contoh 3</h3>
        <p>Sains &amp; alam · 13-17 tahun · Bahasa Indonesia</p>
        <p>Ringkasan singkat cerita contoh ketiga.</p>
        <a href="https://www.google.com">Baca di Sumber Asli</a>
      </div>
    </div>
  </main>
  <footer>Halaman latihan Divisi Jaringan · 2026</footer>
  <script>
    var tombol = document.querySelectorAll('.filter button');
    var kartu = document.querySelectorAll('.kartu');
    tombol.forEach(function (t) {
      t.addEventListener('click', function () {
        tombol.forEach(function (x) { x.classList.remove('aktif'); });
        t.classList.add('aktif');
        var usia = t.getAttribute('data-usia');
        kartu.forEach(function (k) {
          k.style.display = (usia === 'semua' || k.getAttribute('data-usia') === usia) ? '' : 'none';
        });
      });
    });
  </script>
</body>
</html>
