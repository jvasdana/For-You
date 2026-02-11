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
            background: #ffc0cb url('pinkt.jpg') no-repeat center center / cover; /* Gabungan: solid pink + gambar pinkt.jpg */
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
            position: relative; /* Agar di atas animasi background */
            z-index: 1; /* Pastikan container di depan */
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
        /* Tombol Imut Berbeda-Beda */
        .btn-start {
            font-size: 1.2em;
            padding: 15px 30px;
            background-color: #ff69b4;
            color: white;
            border: none;
            border-radius: 50px; /* Bulat */
            cursor: pointer;
            box-shadow: 0 4px 8px rgba(255, 105, 180, 0.3);
            transition: all 0.3s ease;
        }
        .btn-start:hover {
            background-color: #ff1493;
            transform: scale(1.1);
        }
        .btn-answer {
            font-size: 1.2em;
            padding: 10px 20px;
            background-color: #32cd32;
            color: white;
            border: none;
            border-radius: 20px; /* Oval */
            cursor: pointer;
            box-shadow: 0 4px 8px rgba(50, 205, 50, 0.3);
            transition: all 0.3s ease;
        }
        .btn-answer:hover {
            background-color: #228b22;
            transform: scale(1.05);
        }
        .btn-oh-yaa {
            font-size: 1.2em;
            padding: 12px 25px;
            background-color: #ffd700;
            color: #333;
            border: none;
            border-radius: 30px; /* Bulat panjang */
            cursor: pointer;
            box-shadow: 0 4px 8px rgba(255, 215, 0, 0.3);
            transition: all 0.3s ease;
        }
        .btn-oh-yaa:hover {
            background-color: #ffed4e;
            transform: scale(1.1);
        }
        .btn-mau {
            font-size: 1.2em;
            padding: 10px 20px;
            background-color: #ff4500;
            color: white;
            border: none;
            border-radius: 15px; /* Sudut bulat */
            cursor: pointer;
            box-shadow: 0 4px 8px rgba(255, 69, 0, 0.3);
            transition: all 0.3s ease;
        }
        .btn-mau:hover {
            background-color: #dc143c;
            transform: scale(1.05);
        }
        .btn-tidak {
            font-size: 1.2em;
            padding: 10px 20px;
            background-color: #1e90ff;
            color: white;
            border: none;
            border-radius: 25px; /* Oval panjang */
            cursor: pointer;
            box-shadow: 0 4px 8px rgba(30, 144, 255, 0.3);
            transition: all 0.3s ease;
        }
        .btn-tidak:hover {
            background-color: #0066cc;
            transform: scale(1.05);
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
            z-index: 2; /* Di atas animasi background */
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
        .gift-question {
            font-family: 'Fredoka One', cursive; /* Font imut untuk pertanyaan hadiah */
            font-size: 2em;
            color: #ff69b4;
            margin: 20px 0;
        }
        .gift-message {
            font-family: 'Fredoka One', cursive; /* Font imut untuk pesan hadiah */
            font-size: 1.8em;
            color: #333;
            margin: 20px 0;
        }
        
        /* Animasi: Garis vertikal */
        .line {
            position: absolute;
            width: 2px;
            height: 100vh;
            background: linear-gradient(
                to bottom,
                rgba(255, 105, 180, 0),
                rgba(255, 105, 180, 0.4),
                rgba(255, 105, 180, 0)
            );
            animation: moveLine linear infinite;
            z-index: 0; /* Di belakang container */
        }
        @keyframes moveLine {
            from { transform: translateY(-100vh); }
            to { transform: translateY(100vh); }
        }
        
        /* Animasi: Bunga jatuh */
        .flower {
            position: absolute;
            color: #ff4d88;
            font-size: 24px;
            animation: fall linear infinite;
            opacity: 0.8;
            z-index: 0; /* Di belakang container */
        }
        @keyframes fall {
            0% {
                transform: translateY(-10vh);
                opacity: 1;
            }
            100% {
                transform: translateY(110vh);
                opacity: 0;
            }
        }
        
        /* Animasi: Kucing jatuh */
        .cat {
            position: absolute;
            font-size: 30px;
            animation: fall linear infinite;
            opacity: 0.9;
            z-index: 0; /* Di belakang container */
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Bagian Awal: Judul, Gambar, Tombol Ayo Main!! -->
        <div id="intro">
            <h1>Selamat Ulang Tahun, Shafa Amanah!!!</h1>
            <img src="2.gif" alt="Gambar Ulang Tahun" style="max-width: 300px; border-radius: 10px; margin: 20px 0;">
            <button class="btn-start" onclick="startQuiz()">Ayo Main!!</button>
        </div>
        
        <!-- Pertanyaan 1 -->
        <div id="q1" class="hidden">
            <p class="question">1 + 1 = ?</p>
            <input type="number" id="ans1">
            <button class="btn-answer" onclick="checkAnswer(1, 2)">Jawab</button>
        </div>
        
        <!-- Pertanyaan 2 -->
        <div id="q2" class="hidden">
            <p class="question">2 x 2 = ?</p>
            <input type="number" id="ans2">
            <button class="btn-answer" onclick="checkAnswer(2, 4)">Jawab</button>
        </div>
        
        <!-- Pertanyaan 3 -->
        <div id="q3" class="hidden">
            <p class="question">4 x 4 = ?</p>
            <input type="number" id="ans3">
            <button class="btn-answer" onclick="checkAnswer(3, 16)">Jawab</button>
        </div>
        
        <!-- Pesan Imut Setelah 16 -->
        <div id="wow" class="hidden">
            <p class="wow-message sparkle">WOW SUDAH 16 TAHUN YAA</p>
        </div>
        
        <!-- Efek Ledakan dan Pesan Akhir -->
        <div id="celebration" class="hidden">
            <p class="celebration">Selamat Ulang Tahun!!!</p>
            <p>Semoga hari ini penuh kebahagiaan dan tahun depan lebih baik lagi. Terima kasih atas segalanya!</p>
            <p class="from-message">Dari: [Orang Gila]</p>
            <button class="btn-oh-yaa" onclick="showGiftQuestion()">Oh yaa!!</button>
        </div>
        
        <!-- Pertanyaan Hadiah -->
        <div id="gift-question" class="hidden">
            <p class="gift-question">Mau hadiah gak??</p>
            <button class="btn-mau" onclick="showGiftMessage(true)">Mau</button>
            <button class="btn-tidak" onclick="showGiftMessage(false)">Tidak</button>
        </div>
        
        <!-- Pesan Hadiah Akhir -->
        <div id="gift-message" class="hidden">
            <p class="gift-message" id="final-message"></p>
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
        
        function showGiftQuestion() {
            document.getElementById('celebration').classList.add('hidden');
            document.getElementById('gift-question').classList.remove('hidden');
        }
        
        function showGiftMessage(wantsGift) {
            document.getElementById('gift-question').classList.add('hidden');
            const messageElement = document.getElementById('final-message');
            if (wantsGift) {
                messageElement.innerHTML = "oke!!:) DM gua pake emot 🎁";
            } else {
                messageElement.innerHTML = "Ouu oke semangat belajarnya ya! Jangan lupa istirahat dan jaga kesehatan. Kamu pasti bisa!";
            }
            document.getElementById('gift-message').classList.remove('hidden');
        }
        
        // Script: Garis vertikal
        function createLine() {
            const line = document.createElement("div");
            line.className = "line";
            line.style.left = Math.random() * 100 + "vw";
            line.style.animationDuration = (4 + Math.random() * 6) + "s";
            document.body.appendChild(line);
            
            setTimeout(() => {
                line.remove();
            }, 10000);
        }
        
        // Script: Bunga jatuh
        function createFlower() {
            const flower = document.createElement("div");
            flower.className = "flower";
            flower.innerHTML = "🌸"; // Emoji bunga
            flower.style.left = Math.random() * 100 + "vw";
            flower.style.animationDuration = (1 + Math.random() * 2) + "s"; // Durasi cepat: 1-6 detik
            flower.style.fontSize = (16 + Math.random() * 30) + "px";
            document.body.appendChild(flower);
            
            setTimeout(() => {
                flower.remove();
            }, 3000); // Hilang cepat: 3 detik
        }
        
        // Script: Kucing jatuh
        function createCat() {
            const cat = document.createElement("div");
            cat.className = "cat";
            cat.innerHTML = "🐱"; // Emoji kucing
            cat.style.left = Math.random() * 100 + "vw"; // Posisi horizontal acak
            cat.style.animationDuration = (1 + Math.random() * 2) + "s"; // Durasi cepat: 1-6 detik
            cat.style.fontSize = (20 + Math.random() * 20) + "px"; // Ukuran acak
            document.body.appendChild(cat);
            
            setTimeout(() => {
                cat.remove();
            }, 3000); // Hilang cepat: 3 detik
        }
        
        setInterval(createLine, 400);
        setInterval(createFlower, 100); // Bunga jatuh cepat dan sering
        setInterval(createCat, 100); // Kucing jatuh cepat dan sering
    </script>
</body>
</html>
