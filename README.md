<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dashboard Statistik Deskriptif</title>

    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, sans-serif;
        }

        body {
            background: #f1f5f9;
            color: #1e293b;
        }

        .sidebar {
            width: 240px;
            height: 100vh;
            position: fixed;
            background: #172554;
            color: white;
            padding: 25px 18px;
        }

        .sidebar h2 {
            margin-bottom: 35px;
            font-size: 22px;
        }

        .sidebar a {
            display: block;
            color: #dbeafe;
            text-decoration: none;
            padding: 14px 12px;
            margin-bottom: 8px;
            border-radius: 8px;
        }

        .sidebar a:hover {
            background: #2563eb;
            color: white;
        }

        .main {
            margin-left: 240px;
            padding: 30px;
        }

        .header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 15px;
            margin-bottom: 25px;
        }

        .header h1 {
            font-size: 28px;
            margin-bottom: 8px;
        }

        .header p {
            color: #64748b;
        }

        .badge {
            background: #dcfce7;
            color: #166534;
            padding: 10px 15px;
            border-radius: 20px;
            font-size: 13px;
        }

        .cards {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 18px;
            margin-bottom: 30px;
        }

        .card {
            background: white;
            padding: 22px;
            border-radius: 12px;
            box-shadow: 0 3px 12px #00000008;
        }

        .card p {
            color: #64748b;
            font-size: 13px;
        }

        .card h2 {
            font-size: 28px;
            margin: 14px 0 8px;
            color: #2563eb;
        }

        .section {
            margin-bottom: 30px;
            scroll-margin-top: 20px;
        }

        .section h2 {
            font-size: 21px;
            margin-bottom: 18px;
        }

        .panel {
            background: white;
            padding: 22px;
            border-radius: 12px;
            box-shadow: 0 3px 12px #00000008;
        }

        .table-container {
            overflow-x: auto;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            min-width: 650px;
        }

        th, td {
            padding: 13px;
            border-bottom: 1px solid #e2e8f0;
            text-align: center;
        }

        th {
            background: #eff6ff;
            color: #1e40af;
        }

        tr:hover {
            background: #f8fafc;
        }

        .charts {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
        }

        .chart-box {
            min-width: 0;
            height: 330px;
        }

        .chart-box h3 {
            margin-bottom: 20px;
            font-size: 16px;
        }

        .analysis {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
        }

        .analysis-item {
            background: white;
            padding: 20px;
            border-radius: 12px;
            border-left: 5px solid #2563eb;
            line-height: 1.7;
        }

        .analysis-item h3 {
            margin-bottom: 10px;
            font-size: 16px;
        }

        .analysis-item p {
            font-size: 14px;
            color: #475569;
        }

        .upload {
            margin-bottom: 25px;
        }

        input, button {
            padding: 10px;
            margin-top: 10px;
        }

        button {
            border: none;
            border-radius: 6px;
            background: #2563eb;
            color: white;
            cursor: pointer;
        }

        button:hover {
            background: #1d4ed8;
        }

        .note {
            margin-top: 15px;
            color: #64748b;
            font-size: 13px;
            line-height: 1.7;
        }

        footer {
            text-align: center;
            padding: 25px;
            color: #64748b;
            font-size: 13px;
        }

        @media (max-width: 1000px) {
            .cards {
                grid-template-columns: repeat(2, 1fr);
            }

            .charts {
                grid-template-columns: 1fr;
            }
        }

        @media (max-width: 650px) {
            .sidebar {
                width: 100%;
                height: auto;
                position: relative;
            }

            .sidebar h2 {
                margin-bottom: 15px;
            }

            .main {
                margin-left: 0;
                padding: 18px;
            }

            .cards, .analysis {
                grid-template-columns: 1fr;
            }

            .header h1 {
                font-size: 23px;
            }
        }
    </style>
</head>

<body>

    <aside class="sidebar">
        <h2>📊 Statistik</h2>

        <a href="#ringkasan">Dashboard</a>
        <a href="#data">Data Pengamatan</a>
        <a href="#statistik">Statistik Deskriptif</a>
        <a href="#grafik">Grafik Statistik</a>
        <a href="#analisis">Analisis Keputusan</a>
    </aside>

    <main class="main">

        <header class="header">
            <div>
                <h1>Dashboard Statistik Deskriptif</h1>
                <p>Analisis Data Pengunjung dan Penjualan</p>
            </div>

            <span class="badge">● Dashboard Aktif</span>
        </header>

        <!-- RINGKASAN -->
        <section id="ringkasan" class="cards">

            <div class="card">
                <p>Jumlah Pengamatan</p>
                <h2 id="jumlah">10</h2>
                <p>Hari pengamatan</p>
            </div>

            <div class="card">
                <p>Rata-rata Pengunjung</p>
                <h2 id="avgPengunjung">7.70</h2>
                <p>Pengunjung per hari</p>
            </div>

            <div class="card">
                <p>Rata-rata Penjualan</p>
                <h2 id="avgPenjualan">7.40</h2>
                <p>Penjualan per hari</p>
            </div>

            <div class="card">
                <p>Korelasi X dan Y</p>
                <h2 id="korelasi">0.691</h2>
                <p>Pengunjung dan penjualan</p>
            </div>

        </section>

        <!-- UPLOAD DATA -->
        <section class="section panel upload">
            <h2>Unggah Dataset CSV</h2>

            <p>
                Pilih file CSV dengan kolom Hari, Pengunjung, dan Penjualan.
            </p>

            <input type="file" id="fileInput" accept=".csv">

            <button onclick="unggahData()">
                Baca dan Analisis Data
            </button>

            <p class="note">
                Untuk versi HTML ini, unggah data menggunakan CSV.
                File Excel XLSX memerlukan pemrosesan tambahan.
            </p>
        </section>

        <!-- TABEL DATA -->
        <section id="data" class="section">
            <h2>Data Pengamatan</h2>

            <div class="panel table-container">
                <table>
                    <thead>
                        <tr>
                            <th>Hari</th>
                            <th>Pengunjung (X)</th>
                            <th>Penjualan (Y)</th>
                        </tr>
                    </thead>

                    <tbody id="tabelData"></tbody>
                </table>
            </div>
        </section>

        <!-- STATISTIK -->
        <section id="statistik" class="section">
            <h2>Statistik Deskriptif</h2>

            <div class="panel table-container">
                <table>
                    <thead>
                        <tr>
                            <th>Variabel</th>
                            <th>Jumlah</th>
                            <th>Mean</th>
                            <th>Median</th>
                            <th>Modus</th>
                            <th>Minimum</th>
                            <th>Maksimum</th>
                            <th>Standar Deviasi</th>
                        </tr>
                    </thead>

                    <tbody id="tabelStatistik"></tbody>
                </table>
            </div>
        </section>

        <!-- GRAFIK -->
        <section id="grafik" class="section">
            <h2>Visualisasi Data</h2>

            <div class="charts">

                <div class="panel chart-box">
                    <h3>Pengunjung dan Penjualan per Hari</h3>
                    <canvas id="grafikTren"></canvas>
                </div>

                <div class="panel chart-box">
                    <h3>Perbandingan Mean dan Median</h3>
                    <canvas id="grafikStatistik"></canvas>
                </div>

            </div>
        </section>

        <!-- ANALISIS -->
        <section id="analisis" class="section">
            <h2>Analisis dan Keputusan</h2>

            <div class="analysis">

                <div class="analysis-item">
                    <h3>1. Hubungan Pengunjung dan Penjualan</h3>
                    <p id="analisisKorelasi"></p>
                </div>

                <div class="analysis-item">
                    <h3>2. Strategi Penjualan</h3>
                    <p id="analisisPenjualan"></p>
                </div>

                <div class="analysis-item">
                    <h3>3. Evaluasi Hari Terbaik</h3>
                    <p id="analisisTerbaik"></p>
                </div>

                <div class="analysis-item">
                    <h3>4. Rekomendasi Keputusan</h3>
                    <p id="rekomendasi"></p>
                </div>

            </div>

            <p class="note">
                Catatan: korelasi menunjukkan hubungan statistik, bukan
                bukti sebab-akibat. Keputusan akhir perlu mempertimbangkan
                faktor lain seperti promosi, stok, dan hari libur.
            </p>
        </section>

        <footer>
            Dashboard Statistik Deskriptif &copy; 2026
        </footer>

    </main>

    <script>
        let data = [
            {hari: 1, pengunjung: 5, penjualan: 4},
            {hari: 2, pengunjung: 6, penjualan: 5},
            {hari: 3, pengunjung: 7, penjualan: 6},
            {hari: 4, pengunjung: 8, penjualan: 7},
            {hari: 5, pengunjung: 9, penjualan: 8},
            {hari: 6, pengunjung: 10, penjualan: 9},
            {hari: 7, pengunjung: 8, penjualan: 8},
            {hari: 8, pengunjung: 7, penjualan: 7},
            {hari: 9, pengunjung: 9, penjualan: 9},
            {hari: 10, pengunjung: 8, penjualan: 11}
        ];

        let grafikTren;
        let grafikStatistik;

        function rataRata(arr) {
            return arr.reduce((a, b) => a + b, 0) / arr.length;
        }

        function median(arr) {
            const a = [...arr].sort((x, y) => x - y);
            const m = Math.floor(a.length / 2);

            return a.length % 2
                ? a[m]
                : (a[m - 1] + a[m]) / 2;
        }

        function modus(arr) {
            const frekuensi = {};

            arr.forEach(n => {
                frekuensi[n] = (frekuensi[n] || 0) + 1;
            });

            const max = Math.max(...Object.values(frekuensi));

            if (max === 1) return "-";

            return Object.keys(frekuensi)
                .filter(k => frekuensi[k] === max)
                .join(", ");
        }

        function standarDeviasi(arr) {
            const mean = rataRata(arr);

            const varians = arr.reduce(
                (total, n) => total + Math.pow(n - mean, 2), 0
            ) / (arr.length - 1);

            return Math.sqrt(varians);
        }

        function korelasi(x, y) {
            const mx = rataRata(x);
            const my = rataRata(y);

            let atas = 0;
            let bawahX = 0;
            let bawahY = 0;

            for (let i = 0; i < x.length; i++) {
                atas += (x[i] - mx) * (y[i] - my);
                bawahX += Math.pow(x[i] - mx, 2);
                bawahY += Math.pow(y[i] - my, 2);
            }

            const penyebut = Math.sqrt(bawahX * bawahY);

            return penyebut === 0 ? 0 : atas / penyebut;
        }

        function tampilkanData() {
            const tbody = document.getElementById("tabelData");

            tbody.innerHTML = data.map(d => `
                <tr>
                    <td>${d.hari}</td>
                    <td>${d.pengunjung}</td>
                    <td>${d.penjualan}</td>
                </tr>
            `).join("");

            document.getElementById("jumlah").textContent = data.length;

            const x = data.map(d => d.pengunjung);
            const y = data.map(d => d.penjualan);

            const meanX = rataRata(x);
            const meanY = rataRata(y);
            const corr = korelasi(x, y);

            document.getElementById("avgPengunjung").textContent =
                meanX.toFixed(2);

            document.getElementById("avgPenjualan").textContent =
                meanY.toFixed(2);

            document.getElementById("korelasi").textContent =
                corr.toFixed(3);

            tampilkanStatistik(x, y);
            tampilkanGrafik(x, y);
            tampilkanAnalisis(x, y, corr, meanX, meanY);
        }

        function tampilkanStatistik(x, y) {
            const tbody = document.getElementById("tabelStatistik");

            const variabel = [
                {nama: "Pengunjung (X)", data: x},
                {nama: "Penjualan (Y)", data: y}
            ];

            tbody.innerHTML = variabel.map(v => {
                const a = v.data;

                return `
                    <tr>
                        <td>${v.nama}</td>
                        <td>${a.length}</td>
                        <td>${rataRata(a).toFixed(2)}</td>
                        <td>${median(a).toFixed(2)}</td>
                        <td>${modus(a)}</td>
                        <td>${Math.min(...a)}</td>
                        <td>${Math.max(...a)}</td>
                        <td>${standarDeviasi(a).toFixed(2)}</td>
                    </tr>
                `;
            }).join("");
        }

        function tampilkanGrafik(x, y) {
            const labels = data.map(d => "Hari " + d.hari);

            if (grafikTren) grafikTren.destroy();

            grafikTren = new Chart(
                document.getElementById("grafikTren"),
                {
                    type: "line",
                    data: {
                        labels: labels,
                        datasets: [
                            {
                                label: "Pengunjung (X)",
                                data: x,
                                borderColor: "#2563eb",
                                backgroundColor: "#2563eb",
                                tension: 0.3
                            },
                            {
                                label: "Penjualan (Y)",
                                data: y,
                                borderColor: "#10b981",
                                backgroundColor: "#10b981",
                                tension: 0.3
                            }
                        ]
                    },
                    options: {
                        responsive: true,
                        maintainAspectRatio: false
                    }
                }
            );

            if (grafikStatistik) grafikStatistik.destroy();

            grafikStatistik = new Chart(
                document.getElementById("grafikStatistik"),
                {
                    type: "bar",
                    data: {
                        labels: ["Pengunjung", "Penjualan"],
                        datasets: [
                            {
                                label: "Mean",
                                data: [rataRata(x), rataRata(y)],
                                backgroundColor: "#2563eb"
                            },
                            {
                                label: "Median",
                                data: [median(x), median(y)],
                                backgroundColor: "#10b981"
                            }
                        ]
                    },
                    options: {
                        responsive: true,
                        maintainAspectRatio: false
                    }
                }
            );
        }

        function tampilkanAnalisis(x, y, corr, meanX, meanY) {
            let kekuatan;

            if (Math.abs(corr) >= 0.7) {
                kekuatan = "kuat";
            } else if (Math.abs(corr) >= 0.4) {
                kekuatan = "sedang";
            } else if (Math.abs(corr) > 0) {
                kekuatan = "lemah";
            } else {
                kekuatan = "tidak terlihat";
            }

            const arah = corr > 0
                ? "positif"
                : corr < 0
                    ? "negatif"
                    : "tidak ada";

            document.getElementById("analisisKorelasi").textContent =
                `Nilai korelasi ${corr.toFixed(3)} menunjukkan hubungan ${arah} ${kekuatan} antara pengunjung dan penjualan. Korelasi tidak membuktikan sebab-akibat.`;

            document.getElementById("analisisPenjualan").textContent =
                `Rata-rata pengunjung adalah ${meanX.toFixed(2)} dan rata-rata penjualan ${meanY.toFixed(2)}. Gunakan nilai rata-rata sebagai salah satu acuan perencanaan stok dan target penjualan.`;

            const terbaik = data.reduce((a, b) =>
                b.penjualan > a.penjualan ? b : a
            );

            document.getElementById("analisisTerbaik").textContent =
                `Penjualan tertinggi terjadi pada hari ${terbaik.hari}, sebanyak ${terbaik.penjualan}. Periksa kondisi pada hari tersebut untuk menemukan strategi yang dapat dipertahankan.`;

            document.getElementById("rekomendasi").textContent =
                "Evaluasi hari dengan penjualan rendah, periksa ketersediaan stok, dan pertimbangkan promosi. Bandingkan data dari lebih banyak hari sebelum mengambil keputusan jangka panjang.";
        }

        function unggahData() {
            const file = document.getElementById("fileInput").files[0];

            if (!file) {
                alert("Silakan pilih file CSV terlebih dahulu.");
                return;
            }

            const reader = new FileReader();

            reader.onload = function(e) {
                try {
                    const lines = e.target.result.trim().split(/\r?\n/);

                    const parsed = lines.map(line =>
                        line.split(/[;,]/).map(value => value.trim())
                    );

                    const header = parsed[0].map(h => h.toLowerCase());

                    const idxHari = header.findIndex(h => h.includes("hari"));
                    const idxX = header.findIndex(h => h.includes("pengunjung"));
                    const idxY = header.findIndex(h => h.includes("penjualan"));

                    if (idxHari < 0 || idxX < 0 || idxY < 0) {
                        throw new Error(
                            "Header CSV harus memiliki kolom Hari, Pengunjung, dan Penjualan."
                        );
                    }

                    const hasil = parsed.slice(1)
                        .filter(row => row.length >= header.length)
                        .map(row => ({
                            hari: Number(row[idxHari]),
                            pengunjung: Number(row[idxX]),
                            penjualan: Number(row[idxY])
                        }))
                        .filter(row =>
                            Number.isFinite(row.hari) &&
                            Number.isFinite(row.pengunjung) &&
                            Number.isFinite(row.penjualan)
                        );

                    if (hasil.length === 0) {
                        throw new Error("Tidak ada baris data numerik yang valid.");
                    }

                    data = hasil;
                    tampilkanData();

                    alert("Dataset berhasil dianalisis.");

                } catch (error) {
                    alert("Gagal membaca CSV: " + error.message);
                }
            };

            reader.readAsText(file);
        }

        tampilkanData();
    </script>

</body>
</html>
