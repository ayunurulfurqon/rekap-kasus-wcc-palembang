
<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Rekap Kasus WCC Palembang</title>
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<style>
* { box-sizing: border-box; }
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: #f7f3f5;
  color: #352b32;
}
header {
  background: #702d50;
  color: white;
  padding: 30px 20px;
  text-align: center;
}
header h1 { margin: 0 0 8px; }
header p { margin: 0; opacity: .9; }
main {
  max-width: 1050px;
  margin: auto;
  padding: 25px 18px;
}
.total {
  background: white;
  padding: 25px;
  border-radius: 15px;
  text-align: center;
  box-shadow: 0 3px 12px #00000010;
  margin-bottom: 20px;
}
.total h2 { color: #702d50; font-size: 42px; margin: 5px; }
.cards {
  display: grid;
  grid-template-columns: repeat(auto-fit,minmax(150px,1fr));
  gap: 14px;
}
.card {
  background: white;
  border-radius: 12px;
  padding: 20px;
  border-left: 5px solid #a64d79;
  box-shadow: 0 3px 10px #0000000b;
}
.card h3 { font-size: 15px; margin: 0 0 12px; }
.card strong { font-size: 30px; color: #702d50; }
.chart {
  background: white;
  margin-top: 22px;
  padding: 22px;
  border-radius: 15px;
  box-shadow: 0 3px 12px #00000010;
}
.chart h2 { font-size: 19px; }
footer {
  text-align: center;
  padding: 25px;
  color: #76636e;
  font-size: 13px;
}
</style>
</head>
<body>
<header>
<h1>WCC PALEMBANG</h1>
<p>Dashboard Rekapitulasi Kasus Kekerasan</p>
</header>
<main>
<section class="total">
<p>TOTAL KESELURUHAN KASUS</p>
<h2>104</h2>
<p>Jumlah kasus berdasarkan data rekapitulasi</p>
</section>

<section class="cards">
<div class="card"><h3>KDRT</h3><strong>45</strong></div>
<div class="card"><h3>Perkosaan</h3><strong>10</strong></div>
<div class="card"><h3>Pelecehan Seksual</h3><strong>7</strong></div>
<div class="card"><h3>KDP</h3><strong>18</strong></div>
<div class="card"><h3>Trafficking</h3><strong>13</strong></div>
<div class="card"><h3>Kategori Lainnya / Belum Dirinci</h3><strong>11</strong></div>
</section>

<section class="chart">
<h2>Grafik Rekapitulasi Kasus</h2>
<canvas id="grafik"></canvas>
</section>
</main>
<footer>
WCC Palembang | Rekapitulasi Data Kasus
</footer>
<script>
new Chart(document.getElementById('grafik'), {
  type: 'bar',
  data: {
    labels: ['KDRT','Perkosaan','Pelecehan Seksual','KDP','Trafficking','Lainnya / Belum Dirinci'],
    datasets: [{
      label: 'Jumlah Kasus',
      data: [45,10,7,18,13,11],
      backgroundColor: ['#702d50','#a64d79','#d18aab','#8e5575','#bd7896','#d8b2c3'],
      borderRadius: 6
    }]
  },
  options: {
    responsive: true,
    plugins: { legend: { display: false } },
    scales: { y: { beginAtZero: true, ticks: { stepSize: 5 } } }
  }
});
</script>
</body>
</html>
