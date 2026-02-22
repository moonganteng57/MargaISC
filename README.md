# MargaISC
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Soal-soal Marga ISC - Galaksi Bimasakti</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial', sans-serif;
        }

        body {
            background: linear-gradient(135deg, #0b0d17 0%, #1a2a6c 50%, #2a0845 100%);
            color: #fff;
            min-height: 100vh;
            padding: 20px;
        }

        .container {
            max-width: 800px;
            margin: 0 auto;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 30px;
            backdrop-filter: blur(10px);
            box-shadow: 0 0 30px rgba(0, 255, 255, 0.2);
        }

        header {
            text-align: center;
            margin-bottom: 30px;
            border-bottom: 2px solid #00ffff;
            padding-bottom: 20px;
        }

        header h1 {
            color: #00ffff;
            font-size: 2.5rem;
            margin-bottom: 10px;
            text-shadow: 0 0 15px rgba(0, 255, 255, 0.8);
        }

        header p {
            font-size: 1.1rem;
            color: #cccccc;
        }

        .menu-utama {
            text-align: center;
            margin: 30px 0;
        }

        .btn {
            display: inline-block;
            padding: 15px 30px;
            margin: 10px;
            border: none;
            border-radius: 8px;
            font-size: 1.1rem;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            color: #fff;
        }

        .btn-primary {
            background-color: #00ffff;
            color: #0b0d17;
            font-weight: bold;
            box-shadow: 0 0 15px rgba(0, 255, 255, 0.5);
        }

        .btn-primary:hover {
            background-color: #00cccc;
            box-shadow: 0 0 20px rgba(0, 255, 255, 0.8);
            transform: translateY(-3px);
        }

        .btn-secondary {
            background-color: #ff6b6b;
            box-shadow: 0 0 15px rgba(255, 107, 107, 0.5);
        }

        .btn-secondary:hover {
            background-color: #ff4757;
            box-shadow: 0 0 20px rgba(255, 107, 107, 0.8);
            transform: translateY(-3px);
        }

        .soal-kontainer {
            margin: 20px 0;
            padding: 20px;
            background-color: rgba(0, 0, 0, 0.3);
            border-radius: 10px;
            border-left: 5px solid #00ffff;
        }

        .level-judul {
            color: #ffd700;
            font-size: 1.5rem;
            margin: 20px 0 10px 0;
            text-shadow: 0 0 10px rgba(255, 215, 0, 0.7);
        }

        .soal-nomor {
            font-weight: bold;
            color: #00ffff;
            margin-bottom: 10px;
        }

        .soal-teks {
            font-size: 1.1rem;
            margin-bottom: 10px;
        }

        .petunjuk {
            font-size: 0.9rem;
            color: #cccccc;
            margin-bottom: 15px;
            font-style: italic;
        }

        .jawaban-input {
            width: 100%;
            padding: 10px;
            border-radius: 5px;
            border: none;
            margin-bottom: 15px;
            font-size: 1rem;
            background-color: rgba(255, 255, 255, 0.2);
            color: #fff;
            border: 1px solid transparent;
        }

        .jawaban-input:focus {
            outline: none;
            border: 1px solid #00ffff;
            box-shadow: 0 0 10px rgba(0, 255, 255, 0.5);
        }

        .hasil-item {
            margin: 10px 0;
            padding: 10px;
            border-radius: 5px;
        }

        .benar {
            background-color: rgba(46, 204, 113, 0.3);
            border-left: 5px solid #2ecc71;
        }

        .salah {
            background-color: rgba(231, 76, 60, 0.3);
            border-left: 5px solid #e74c3c;
        }

        .hasil-akhir {
            margin-top: 30px;
            padding: 25px;
            background-color: rgba(255, 215, 0, 0.2);
            border-radius: 10px;
            text-align: center;
        }

        .hasil-akhir h3 {
            font-size: 1.8rem;
            margin-bottom: 15px;
            color: #ffd700;
        }

        .peringkat-tabel {
            width: 100%;
            margin-top: 20px;
            border-collapse: collapse;
        }

        .peringkat-tabel th, .peringkat-tabel td {
            padding: 12px;
            text-align: left;
            border-bottom: 1px solid rgba(255, 255, 255, 0.2);
        }

        .peringkat-tabel th {
            background-color: rgba(0, 255, 255, 0.2);
            color: #0b0d17;
            font-weight: bold;
        }

        .peringkat-tabel tr:hover {
            background-color: rgba(255, 255, 255, 0.1);
        }

        .hidden {
            display: none;
        }

        @media (max-width: 600px) {
            header h1 {
                font-size: 1.8rem;
            }

            .btn {
                display: block;
                width: 100%;
                margin: 10px 0;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Header -->
        <header>
            <h1>SOAL-SOAL MARGA ISC</h1>
            <p>Petualangan di Planet-planet Galaksi Bimasakti</p>
        </header>

        <!-- Menu Utama -->
        <div id="menu-utama" class="menu-utama">
            <input type="text" id="nama-pemain" placeholder="Masukkan nama kamu..." class="jawaban-input" style="max-width: 400px;">
            <br>
            <button class="btn btn-primary" onclick="mulaiTes()">Mulai Tes Astronomi</button>
            <button class="btn btn-secondary" onclick="lihatPeringkat()">Lihat Papan Peringkat</button>
        </div>

        <!-- Area Tes -->
        <div id="area-tes" class="hidden">
            <div id="soal-konten"></div>
            <button class="btn btn-primary" onclick="submitJawaban()" id="btn-submit" style="margin-top: 20px;">Kirim Semua Jawaban</button>
            <button class="btn btn-secondary" onclick="kembaliKeMenu()" style="margin-top: 20px;">Kembali ke Menu</button>
        </div>

        <!-- Area Hasil -->
        <div id="area-hasil" class="hidden">
            <div id="hasil-konten"></div>
            <button class="btn btn-primary" onclick="kembaliKeMenu()" style="margin-top: 20px;">Kembali ke Menu</button>
            <button class="btn btn-secondary" onclick="ulangiTes()" style="margin-top: 20px;">Ulangi Tes</button>
        </div>

        <!-- Area Peringkat -->
        <div id="area-peringkat" class="hidden">
            <h2 style="text-align: center; margin-bottom: 20px; color: #00ffff;">PAPAN PERINGKAT MARGA ISC</h2>
            <div id="peringkat-konten"></div>
            <button class="btn btn-secondary" onclick="kembaliKeMenu()" style="margin-top: 20px;">Kembali ke Menu</button>
        </div>
    </div>

    <script>
        // Data Soal
        const dataSoal = {
            "LEVEL MUDAH": [
                {
                    "soal": "Planet yang menjadi teman dekat Bumi dan sering terlihat bersinar di malam hari adalah...",
                    "petunjuk": "Ia dikenal sebagai 'Bintang Pagi' atau 'Bintang Malam'",
                    "jawaban": "Venus"
                },
                {
                    "soal": "Bintang pusat Galaksi Bimasakti yang menjadi sumber cahaya dan panas bagi semua planet di dalamnya adalah...",
                    "petunjuk": "Ia terletak di tengah tata surya kita",
                    "jawaban": "Matahari"
                },
                {
                    "soal": "Planet terbesar di Tata Surya yang memiliki cincin tampak tipis namun luas adalah...",
                    "petunjuk": "Ia memiliki banyak bulan, salah satunya adalah Io",
                    "jawaban": "Jupiter"
                },
                {
                    "soal": "Benda langit yang terbentuk dari es dan debu, dan memiliki 'ekor' saat mendekati Bintang Utama adalah...",
                    "petunjuk": "Contohnya adalah Komet Halley",
                    "jawaban": "Komet"
                },
                {
                    "soal": "Grup planet yang terdiri dari Merkurius, Venus, Bumi, dan Mars disebut sebagai...",
                    "petunjuk": "Mereka lebih kecil dan terbuat dari bahan padat",
                    "jawaban": "Planet Batuan"
                }
            ],
            "LEVEL MEDIUM": [
                {
                    "soal": "Planet yang memiliki cincin paling mencolok dan terlihat jelas dari Bumi adalah...",
                    "petunjuk": "Ia adalah planet keenam dari Bintang Utama",
                    "jawaban": "Saturnus"
                },
                {
                    "soal": "Galaksi Bimasakti termasuk ke dalam jenis galaksi yang bentuknya seperti piringan dengan lengkungan di tengah yaitu...",
                    "petunjuk": "Jenis galaksi yang sama dengan Galaksi Andromeda",
                    "jawaban": "Galaksi Spiral"
                },
                {
                    "soal": "Fenomena alam semesta di mana bintang besar mengalami ledakan hebat dan menghasilkan cahaya yang sangat terang adalah...",
                    "petunjuk": "Ia dapat menghasilkan lebih banyak cahaya daripada seluruh galaksi dalam waktu singkat",
                    "jawaban": "Supernova"
                },
                {
                    "soal": "Planet yang memiliki siklus musim sangat panjang karena kemiringan sumbu rotasinya yang ekstrem adalah...",
                    "petunjuk": "Ia adalah planet ketujuh dari Bintang Utama",
                    "jawaban": "Uranus"
                },
                {
                    "soal": "Bulan terbesar di Tata Surya yang termasuk bulan dari Jupiter dan bahkan lebih besar dari planet Merkurius adalah...",
                    "petunjuk": "Namanya diambil dari dewi bulan dalam mitologi Yunani",
                    "jawaban": "Ganimedes"
                }
            ],
            "LEVEL SUSAH": [
                {
                    "soal": "Wilayah di luar orbit Neptunus yang merupakan rumah bagi banyak benda langit kecil, termasuk Pluto, disebut sebagai...",
                    "petunjuk": "Ia berbeda dengan Sabuk Asteroid yang terletak antara Mars dan Jupiter",
                    "jawaban": "Belt Kuiper"
                },
                {
                    "soal": "Jenis bintang kompak yang memiliki massa sangat besar dan gravitasi luar biasa kuat sehingga bahkan cahaya tidak bisa melarikan diri adalah...",
                    "petunjuk": "Dapat terbentuk setelah supernova dari bintang yang sangat masif",
                    "jawaban": "Lubang Hitam"
                },
                {
                    "soal": "Planet yang ditemukan melalui perhitungan matematika sebelum diamati secara langsung dengan teleskop adalah...",
                    "petunjuk": "Ia adalah planet kedelapan dari Bintang Utama",
                    "jawaban": "Neptunus"
                },
                {
                    "soal": "Pusat Galaksi Bimasakti dipercaya mengandung sebuah lubang hitam supermasif yang diberi nama...",
                    "petunjuk": "Singkatan dari Sagittarius A-star",
                    "jawaban": "Sagittarius A*"
                },
                {
                    "soal": "Fenomena di mana cahaya dari bintang jauh ditekuk oleh gravitasi objek besar di antara bintang tersebut dan pengamat di Bumi disebut sebagai...",
                    "petunjuk": "Ini adalah bukti dari teori relativitas umum Einstein",
                    "jawaban": "Lensa Gravitasi"
                }
            ]
        };

        // Variabel Global
        let namaPemain = "";
        let totalSoal = 15;

        // Fungsi Tampilan
        function tampilkanArea(id) {
            document.getElementById("menu-utama").classList.add("hidden");
            document.getElementById("area-tes").classList.add("hidden");
            document.getElementById("area-hasil").classList.add("hidden");
            document.getElementById("area-peringkat").classList.add("hidden");
            document.getElementById(id).classList.remove("hidden");
        }

        // Fungsi Menu Utama
        function mulaiTes() {
            namaPemain = document.getElementById("nama-pemain").value.trim();
            if (namaPemain === "") {
                alert("Masukkan nama kamu terlebih dahulu!");
                return;
            }
            
            tampilkanArea("area-tes");
            renderSoal();
        }

        function lihatPeringkat() {
            tampilkanArea("area-peringkat");
            renderPeringkat();
        }

        function kembaliKeMenu() {
            tampilkanArea("menu-utama");
        }

        function ulangiTes() {
            document.getElementById("nama-pemain").value = namaPemain;
            mulaiTes();
        }

        // Fungsi Soal
        function renderSoal() {
            let konten = "";
            let nomorSoal = 1;

            for (const [level, daftarSoal] of Object.entries(dataSoal)) {
                konten += `<h3 class="level-judul">${level}</h3>`;
                
                daftarSoal.forEach((soal, index) => {
                    konten += `
                        <div class="soal-kontainer">
                            <div class="soal-nomor">SOAL ${nomorSoal}</div>
                            <div class="soal-teks">${soal.soal}</div>
                            <div class="petunjuk">Petunjuk: ${soal.petunjuk}</div>
                            <input type="text" id="jawaban-${level}-${index}" class="jawaban-input" placeholder="Tulis jawabanmu di sini...">
                        </div>
                    `;
                    nomorSoal++;
                });
            }

            document.getElementById("soal-konten").innerHTML = konten;
        }

        // Fungsi Submit dan Hasil
        function submitJawaban() {
            let konten = "";
            let totalBen
            
