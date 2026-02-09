<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Selamat Ulang Tahun!!!</title>
    <!-- Import Google Font untuk font lucu -->
    <link href="https://fonts.googleapis.com/css2?family=Fredoka+One&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: Arial, sans-serif;
            background-image: url('hati.html'); /* Background gambar hati.html */
            background-size: cover; /* Memenuhi layar */
            background-position: center; /* Posisi tengah */
            background-repeat: no-repeat; /* Tidak diulang */
            text-align: center;
            margin: 0;
            padding: 0;
            overflow: hidden;
        }
        .container {
            padding: 50px;
            background-color: rgba(255, 255, 255, 0.8); /* Overlay semi-transparan agar teks terbaca */
            border-radius: 10px;
            margin: 20px auto;
            max-width: 600px;
        }
        h1 {
            color: #ff69b4;
            font-size: 3em;
        }
        .question {
            font-family: 'Fredoka One', cursive; /* Font lucu untuk pertanyaan */
            font-size: 2em;
            margin: 20px 0;
            animation: slideIn 0.5s ease-out; /* Animasi slide in */
        }
        @keyframes slideIn {
            from { transform: translateX(-100%); opacity: 0; }
            to { transform: translateX(0); opacity: 1; }
        }
        input {
            font-size: 1.5em;
            padding: 10px;
            width: 100px;
            text-align: center;
        }
        button {
            font-size: 1.2em;
            padding: 10px 20px;
            background-color: #ff69b4;
            color: white;
            border: none;
            cursor: pointer;
            margin-top: 10px;
        }
        button:hover {
            background-color: #ff1493;
        }
        .hidden {
            display: none;
        }
        .firework {
            position: absolute;
            width: 10px;
            height: 10px;
            background-color: red;
            border-radius: 50%;
            animation: explode 2s ease-out forwards;
        }
        @keyframes explode {
            0% { transform: scale(1); opacity: 1; }
            100% { transform: scale(10); opacity: 0; }
        }
        .celebration {
            font-family: 'Fredoka One', cursive; /* Font lucu untuk pesan akhir */
            font-size: 2em;
            color: #ff69b4;
            animation: bounce 1s infinite;
        }
        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% { transform: translateY(0); }
            40% { transform: translateY(-10px); }
            60% { transform: translateY(-5px); }
        }
        .wow-message {
            font-family: 'Fredoka One', cursive; /* Font lucu untuk pesan imut */
            font-size: 2.5em;
            color: #ff69b4;
            animation: bounce 1s infinite, sparkle 1s infinite; /* Bounce dan sparkle */
            position: relative;
        }
        @keyframes sparkle {
            0%, 100% { text-shadow: 0 0 5px #ff69b4; }
            50% { text-shadow: 0 0 20px #ff69b4, 0 0 30px #ff69b4; }
        }
        .sparkle::before {
            content: '✨';
            position: absolute;
            top: -10px;
            left: -10px;
            animation: twinkle 1s infinite;
        }
        .sparkle::after {
            content: '✨';
            position: absolute;
            top: -10px;
            right: -10px;
            animation: twinkle 1s infinite 0.5s;
        }
        @keyframes twinkle {
            0%, 100% { opacity: 0; }
            50% { opacity: 1; }
        }
        .from-message {
            font-family: 'Fredoka One', cursive; /* Font lucu untuk bagian Dari */
            font-size: 1.5em;
            color: #333;
            margin-top: 10px;
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Bagian Awal: Judul, Gambar, Tombol Ayo Main!! -->
        <div id="intro">
            <h1>Selamat Ulang Tahun,   Shafa Amanah!</h1>
            <img src="2.gif" alt="Gambar Ulang Tahun" style="max-width: 300px; border-radius: 10px; margin: 20px 0;">
            <button onclick="startQuiz()">Ayo Main!!</button>
        </div>
        
        <!-- Pertanyaan 1 -->
        <div id="q1" class="hidden">
            <p class="question">1 + 1 = ?</p>
            <input type="number" id="ans1">
            <button onclick="checkAnswer(1, 2)">Jawab</button>
        </div>
        
        <!-- Pertanyaan 2 -->
        <div id="q2" class="hidden">
            <p class="question">2 x 2 = ?</p>
            <input type="number" id="ans2">
            <button onclick="checkAnswer(2, 4)">Jawab</button>
        </div>
        
        <!-- Pertanyaan 3 -->
        <div id="q3" class="hidden">
            <p class="question">4 x 4 = ?</p>
            <input type="number" id="ans3">
            <button onclick="checkAnswer(3, 16)">Jawab</button>
        </div>
        
        <!-- Pesan Imut Setelah 16 -->
        <div id="wow" class="hidden">
            <p class="wow-message sparkle">WOW SUDAH 16 TAHUN YAA</p>
        </div>
        
        <!-- Efek Ledakan dan Pesan Akhir -->
        <div id="celebration" class="hidden">
            <p class="celebration">Selamat Ulang Tahun!!!!</p>
            <p>Semoga hari ini penuh kebahagiaan dan tahun depan lebih baik lagi. Terima kasih atas segalanya!. Cieee yang setahun lagi sweet seventeen :)</p>
            <p class="from-message">From: [Orang Gila]</p>
        </div>
    </div>
    
    <script>
        let currentQuestion = 1;
        
        function startQuiz() {
            document.getElementById('intro').classList.add('hidden');
            document.getElementById('q1').classList.remove('hidden');
        }
        
        function checkAnswer(questionNum, correctAnswer) {
            const input = document.getElementById('ans' + questionNum);
            if (parseInt(input.value) === correctAnswer) {
                document.getElementById('q' + questionNum).classList.add('hidden');
                currentQuestion++;
                if (currentQuestion <= 3) {
                    document.getElementById('q' + currentQuestion).classList.remove('hidden');
                } else {
                    // Tampilkan pesan imut WOW
                    document.getElementById('wow').classList.remove('hidden');
                    // Tunggu 3 detik, lalu lanjut ke ledakan
                    setTimeout(() => {
                        document.getElementById('wow').classList.add('hidden');
                        // Efek ledakan
                        explodeFireworks();
                        // Suara petasan
                        const fireworkSound = new Audio('petasan.mp3');
                        fireworkSound.play();
                        // Tunggu sedikit lalu mainkan lagu
                        setTimeout(() => {
                            const birthdaySong = new Audio('hbdeee.mp3');
                            birthdaySong.play();
                        }, 2000); // 2 detik setelah ledakan
                        // Tampilkan pesan akhir
                        document.getElementById('celebration').classList.remove('hidden');
                    }, 3000); // 3 detik untuk pesan WOW
                }
            } else {
                alert('Jawaban salah! Coba lagi.');
            }
        }
        
        function explodeFireworks() {
            for (let i = 0; i < 20; i++) {
                const firework = document.createElement('div');
                firework.classList.add('firework');
                firework.style.left = Math.random() * 100 + 'vw';
                firework.style.top = Math.random() * 100 + 'vh';
                firework.style.backgroundColor = ['red', 'blue', 'yellow', 'green'][Math.floor(Math.random() * 4)];
                document.body.appendChild(firework);
                setTimeout(() => firework.remove(), 2000);
            }
        }
    </script>
</body>
</html>
