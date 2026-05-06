# endix.githup.io
ENDİX<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<title>Ali Yyasir Web Sitesi</title>
<style>
body {
    font-family: Arial;
    margin: 0;
    background: #f0f0f0;
}

header {
    background: #333;
    color: white;
    padding: 15px;
    text-align: center;
}

.container {
    display: flex;
}

.menu {
    width: 200px;
    background: #444;
    color: white;
    padding: 10px;
}

.menu div {
    margin: 10px 0;
    cursor: pointer;
}

.content {
    flex: 1;
    padding: 20px;
    background: white;
}

img {
    width: 200px;
    border-radius: 10px;
}

button {
    padding: 10px;
    margin: 5px;
    cursor: pointer;
}
</style>
</head>
<body>

<header>
    <h1>Ali Yyasir'in Sitesi</h1>
</header>

<div class="container">
    <div class="menu">
        <div onclick="showPage('about')">Hakkımda</div>
        <div onclick="showPage('games')">Oyunlar</div>
    </div>

    <div class="content" id="content">
    </div>
</div>

<script>
function showPage(page) {
    const content = document.getElementById("content");

    if(page === "about") {
        content.innerHTML = `
        <h2>Hakkımda</h2>
        <img src="foto.jpg"><br><br>
        <p>
        Merhaba, benim adım Ali Yyasir. Ortaokul 6. sınıfa gidiyorum ve okul hayatımı oldukça severek sürdürüyorum.
        En sevdiğim dersler matematik, İngilizce ve bilişim teknolojileridir. Özellikle matematikte problem çözmek
        bana çok eğlenceli geliyor ve kendimi geliştirmek için sürekli yeni sorular çözmeye çalışıyorum.
        
        İngilizcem de oldukça iyidir ve bu sayede hem yeni şeyler öğrenebiliyor hem de farklı içerikleri rahatlıkla
        anlayabiliyorum. Bilişim teknolojileri dersinde ise bilgisayarlar, yazılım ve kodlama ile ilgilenmek beni
        çok heyecanlandırıyor.
        
        Boş zamanlarımda futbol oynamayı severim. Çok sık oynamasam da futbol benim için hem eğlenceli hem de
        enerjimi atabileceğim güzel bir spordur. Aynı zamanda oyun oynamayı, yeni şeyler öğrenmeyi ve kendimi
        geliştirmeyi de çok seviyorum.
        
        Gelecekte teknolojiyle ilgili alanlarda kendimi daha da geliştirmek ve başarılı olmak istiyorum.
        </p>
        `;
    }

    if(page === "games") {
        content.innerHTML = `
        <h2>Oyunlar</h2>
        <button onclick="startQuiz('Matematik')">Matematik</button>
        <button onclick="startQuiz('Türkçe')">Türkçe</button>
        <button onclick="startQuiz('Fen')">Fen</button>
        <button onclick="startQuiz('İngilizce')">İngilizce</button>
        <div id="quiz"></div>
        `;
    }
}

function startQuiz(ders) {
    const quizDiv = document.getElementById("quiz");
    let soruNo = 1;

    quizDiv.innerHTML = `<h3>${ders} Testi</h3><div id="soru"></div>`;

    function yeniSoru() {
        if(soruNo > 20) {
            document.getElementById("soru").innerHTML = "<h3>Test Bitti!</h3>";
            return;
        }

        document.getElementById("soru").innerHTML = `
        <p>${soruNo}. soru (${ders})</p>
        <button onclick="cevap()">A</button>
        <button onclick="cevap()">B</button>
        <button onclick="cevap()">C</button>
        <button onclick="cevap()">D</button>
        `;
    }

    window.cevap = function() {
        soruNo++;
        yeniSoru();
    }

    yeniSoru();
}

// Başlangıçta hakkımda açılsın
showPage('about');
</script>

</body>
</html>
