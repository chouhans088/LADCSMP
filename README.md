<!DOCTYPE html>
<html lang="hi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Legal News — विधिक समाचार</title>
<link href="https://fonts.googleapis.com/css2?family=Noto+Sans+Devanagari:wght@300;400;600;700;900&family=Noto+Serif+Devanagari:wght@400;600;700&family=Playfair+Display:ital,wght@0,700;1,400&display=swap" rel="stylesheet">
<style>
* { box-sizing: border-box; margin: 0; padding: 0; }

body {
  min-height: 100vh;
  background: #2c1810;
  background-image:
    radial-gradient(ellipse at 20% 20%, #3d2010 0%, transparent 60%),
    radial-gradient(ellipse at 80% 80%, #1a0f08 0%, transparent 60%);
  padding: 20px 12px 40px;
  font-family: 'Noto Sans Devanagari', sans-serif;
}

/* Newspaper container */
.newspaper {
  max-width: 680px;
  margin: 0 auto;
  background: #f5ead5;
  background-image:
    url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='400' height='400'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3CfeColorMatrix type='saturate' values='0'/%3E%3C/filter%3E%3Crect width='400' height='400' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
  border: 1px solid #c8a878;
  box-shadow:
    0 0 0 4px #b89060,
    0 0 0 8px #f5ead5,
    0 0 0 10px #b89060,
    8px 12px 40px rgba(0,0,0,0.6);
  position: relative;
}

/* Paper texture lines */
.newspaper::before {
  content: '';
  position: absolute;
  inset: 0;
  background-image: repeating-linear-gradient(
    0deg, transparent, transparent 27px,
    rgba(180,140,80,0.06) 27px, rgba(180,140,80,0.06) 28px
  );
  pointer-events: none;
}

/* Masthead */
.masthead {
  border-bottom: 3px double #5c3a1a;
  padding: 20px 24px 16px;
  text-align: center;
  background: linear-gradient(180deg, #ede0c0 0%, #f5ead5 100%);
}

.masthead-top {
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 10px;
  color: #7a5a30;
  margin-bottom: 10px;
  font-family: 'Noto Serif Devanagari', serif;
}

.masthead h1 {
  font-family: 'Playfair Display', serif;
  font-size: clamp(28px, 8vw, 48px);
  color: #2c1810;
  letter-spacing: 2px;
  line-height: 1;
  margin-bottom: 6px;
  text-shadow: 1px 1px 0 rgba(0,0,0,0.1);
}

.masthead-tagline {
  font-family: 'Noto Serif Devanagari', serif;
  font-size: 12px;
  color: #5c3a1a;
  letter-spacing: 1px;
  font-style: italic;
  margin-bottom: 8px;
}

.masthead-divider {
  height: 1px;
  background: linear-gradient(90deg, transparent, #5c3a1a, transparent);
  margin: 8px 0;
}

.masthead-info {
  display: flex;
  justify-content: space-between;
  font-size: 10px;
  color: #7a5a30;
}

/* Breaking banner */
.breaking-banner {
  background: #2c1810;
  color: #f5ead5;
  padding: 6px 16px;
  font-size: 11px;
  font-weight: 700;
  letter-spacing: 2px;
  text-align: center;
  text-transform: uppercase;
}

/* Content area */
.content {
  padding: 20px 24px;
}

/* Article */
.article {
  margin-bottom: 24px;
  padding-bottom: 20px;
  border-bottom: 1px solid #c8a878;
}

.article:last-child {
  border-bottom: none;
  margin-bottom: 0;
}

/* Category badge */
.cat-badge {
  display: inline-block;
  background: #2c1810;
  color: #f5ead5;
  font-size: 9px;
  letter-spacing: 2px;
  padding: 3px 10px;
  margin-bottom: 8px;
  text-transform: uppercase;
}

/* Headline */
.article-headline {
  font-family: 'Noto Serif Devanagari', serif;
  font-size: clamp(18px, 4vw, 24px);
  font-weight: 700;
  color: #1a0f08;
  line-height: 1.3;
  margin-bottom: 8px;
  border-bottom: 2px solid #5c3a1a;
  padding-bottom: 8px;
}

/* Dateline */
.dateline {
  font-size: 11px;
  color: #7a5a30;
  font-style: italic;
  margin-bottom: 12px;
  font-family: 'Noto Serif Devanagari', serif;
}

/* Body text */
.article-body {
  font-family: 'Noto Serif Devanagari', serif;
  font-size: 14px;
  color: #2a1a0a;
  line-height: 1.9;
  text-align: justify;
}

.article-body p {
  margin-bottom: 12px;
  text-indent: 16px;
}

.article-body p:first-child::first-letter {
  font-size: 3em;
  font-weight: 700;
  float: left;
  line-height: 0.8;
  margin: 4px 6px 0 0;
  color: #2c1810;
  font-family: 'Playfair Display', serif;
}

/* Section headers inside article */
.section-head {
  font-family: 'Noto Serif Devanagari', serif;
  font-size: 14px;
  font-weight: 700;
  color: #2c1810;
  margin: 14px 0 8px;
  padding: 6px 10px;
  background: rgba(92,58,26,0.08);
  border-left: 3px solid #5c3a1a;
}

/* Info boxes */
.info-box {
  background: rgba(92,58,26,0.06);
  border: 1px solid #c8a878;
  border-radius: 2px;
  padding: 12px 14px;
  margin: 12px 0;
  font-size: 13px;
  line-height: 1.8;
  color: #2a1a0a;
}

.info-box ul {
  list-style: none;
  padding: 0;
}

.info-box ul li::before {
  content: "· ";
  color: #5c3a1a;
  font-weight: 700;
}

/* Warning box */
.warning-box {
  background: #fff8e8;
  border: 1px solid #c8a878;
  border-left: 4px solid #c8692a;
  padding: 12px 14px;
  margin: 12px 0;
  font-size: 13px;
  color: #5c3a1a;
  line-height: 1.7;
}

/* Divider */
.ornament {
  text-align: center;
  color: #b89060;
  font-size: 18px;
  margin: 16px 0;
  letter-spacing: 8px;
}

/* Footer */
.paper-footer {
  background: #2c1810;
  color: #b89060;
  padding: 12px 20px;
  font-size: 10px;
  text-align: center;
  letter-spacing: 1px;
  line-height: 1.8;
}

/* Back button */
.back-btn {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background: rgba(245,234,213,0.1);
  border: 1px solid rgba(184,144,96,0.4);
  color: #b89060;
  padding: 8px 18px;
  border-radius: 4px;
  text-decoration: none;
  font-size: 12px;
  margin-bottom: 16px;
  font-family: inherit;
  cursor: pointer;
}

/* Page number */
.page-num {
  text-align: center;
  font-size: 11px;
  color: #7a5a30;
  padding: 8px;
  font-family: 'Noto Serif Devanagari', serif;
  border-top: 1px solid #c8a878;
  background: #ede0c0;
}
</style>
</head>
<body>

<div style="max-width:680px;margin:0 auto;">
  <a href="index.html" class="back-btn">← Legal Aid Directory पर वापस</a>
</div>

<div class="newspaper">

  <!-- Masthead -->
  <div class="masthead">
    <div class="masthead-top">
      <span>⚖ जिला विधिक सेवा प्राधिकरण, नीमच</span>
      <span>स्थापना — 2026</span>
    </div>
    <div class="masthead-divider"></div>
    <h1>Legal News</h1>
    <div class="masthead-tagline">विधिक समाचार एवं अपडेट</div>
    <div class="masthead-divider"></div>
    <div class="masthead-info">
      <span id="todayDate">—</span>
      <span>नीमच, मध्यप्रदेश</span>
      <span>निःशुल्क विधिक सहायता</span>
    </div>
  </div>

  <!-- Breaking banner -->
  <div class="breaking-banner">⚡ ताज़ा समाचार — Latest Legal Updates ⚡</div>

  <!-- Content -->
  <div class="content">

    <!-- Article 1 -->
    <div class="article">
      <div class="cat-badge">परीक्षा समाचार</div>
      <div class="article-headline">MPPSC ने जारी किया ADPO परीक्षा का नया पैटर्न! जानें क्या है सिलेबस</div>
      <div class="dateline">भोपाल, 16 जुलाई 2026</div>

      <div class="article-body">
        <p>मध्य प्रदेश लोक सेवा आयोग (MPPSC) ने सहायक जिला अभियोजन अधिकारी (ADPO) परीक्षा 2026 का सिलेबस जारी कर दिया है। इस बार विधि सेक्शन में पुरानी IPC-CrPC की जगह नए BNS-BNSS-BSA को शामिल किया गया है। परीक्षा 18 अक्टूबर 2026 को होने की संभावना है।</p>
      </div>

      <div class="section-head">🔴 बड़ा बदलाव: पहली बार सेक्शनवार क्वालीफाइंग</div>
      <div class="article-body">
        <p>MPPSC ने इस बार सख्त नियम लागू किया है — दोनों सेक्शनों में अलग-अलग 40% अंक लाना अनिवार्य होगा। यानी सामान्य ज्ञान और विधि, दोनों में क्वालीफाई करना जरूरी होगा। SC/ST/OBC को 10% की छूट दी गई है।</p>
      </div>

      <div class="section-head">📊 कुल 450 अंकों की होगी भिड़ंत</div>
      <div class="info-box">
        <ul>
          <li>कुल सवाल: 150 (सभी MCQ)</li>
          <li>सेक्शन A (सामान्य ज्ञान): 50 सवाल — 150 अंक</li>
          <li>सेक्शन B (विधि): 100 सवाल — 300 अंक</li>
          <li>समय: 3 घंटे</li>
          <li>नेगेटिव मार्किंग: हर गलत जवाब पर -1 अंक कटेगा</li>
        </ul>
      </div>

      <div class="section-head">🗂️ सिलेबस: क्या पढ़ना है?</div>

      <div class="section-head" style="background:rgba(26,74,26,0.08);border-left-color:#1a4a1a;">🟢 सामान्य ज्ञान — 50 सवाल</div>
      <div class="article-body">
        <p>पूरा फोकस मध्य प्रदेश पर रहेगा। इतिहास, भूगोल, राजनीति, अर्थव्यवस्था, जनजातियाँ, बोलियाँ और संस्कृति — सब MP सेंट्रिक होगा। साथ ही राष्ट्रीय-अंतरराष्ट्रीय करंट अफेयर्स और ई-गवर्नेंस, AI, साइबर सिक्योरिटी जैसे आधुनिक टॉपिक भी पूछे जाएंगे।</p>
      </div>

      <div class="section-head" style="background:rgba(139,26,26,0.08);border-left-color:#8c1a1a;">🔴 विधि — 100 सवाल (सबसे वेटेज)</div>
      <div class="info-box">
        <ul>
          <li>मुख्य विधि: संविधान, BNS, BNSS, BSA, भ्रष्टाचार निवारण अधिनियम</li>
          <li>MP स्पेशल: MP आबकारी, MP राज्य सुरक्षा, MP गोवध निषेध अधिनियम</li>
          <li>संरक्षण कानून: POCSO, घरेलू हिंसा, दहेज निषेध, किशोर न्याय, SC/ST एक्ट, NDPS</li>
          <li>अन्य: IT एक्ट, RTI, मोटर वाहन, शस्त्र, खाद्य सुरक्षा</li>
        </ul>
      </div>

      <div class="warning-box">
        ⚠️ <strong>विशेष सलाह:</strong> इस बार BNS, BNSS और BSA पर सबसे ज्यादा फोकस करना होगा क्योंकि पुरानी IPC, CrPC और Evidence Act हटा दी गई हैं। MP के स्थानीय कानूनों को भी गंभीरता से पढ़ना होगा।
      </div>

      <div class="section-head">🗓️ परीक्षा कब?</div>
      <div class="article-body">
        <p>अभी आधिकारिक नोटिफिकेशन जारी नहीं हुआ है, लेकिन मीडिया रिपोर्ट्स के अनुसार अक्टूबर 2026 में एग्जाम होने की उम्मीद है।</p>
      </div>
    </div>

    <div class="ornament">— ✦ —</div>

    <!-- Add more news placeholder -->
    <div style="text-align:center;padding:20px;color:#9a7a50;font-size:12px;font-style:italic;border:1px dashed #c8a878;border-radius:2px;">
      📰 और समाचार जल्द आएंगे...<br>
      <span style="font-size:10px;">नई news जोड़ने के लिए Google Sheet update करें</span>
    </div>

  </div>

  <div class="page-num">— पृष्ठ 1 — जिला विधिक सेवा प्राधिकरण, नीमच —</div>

  <div class="paper-footer">
    ⚖ Legal News — विधिक समाचार &nbsp;|&nbsp; जिला विधिक सेवा प्राधिकरण, नीमच (म.प्र.)<br>
    सचिव — शोभना मीणा &nbsp;|&nbsp; दूरभाष: 07423-299234 &nbsp;|&nbsp; Email: secdlsaneemuch@gmail.com
  </div>

</div>

<script>
// Today's date
const days = ['रविवार','सोमवार','मंगलवार','बुधवार','गुरुवार','शुक्रवार','शनिवार'];
const months = ['जनवरी','फरवरी','मार्च','अप्रैल','मई','जून','जुलाई','अगस्त','सितम्बर','अक्टूबर','नवम्बर','दिसम्बर'];
const now = new Date();
document.getElementById('todayDate').textContent =
  `${days[now.getDay()]}, ${now.getDate()} ${months[now.getMonth()]} ${now.getFullYear()}`;
</script>

</body>
</html>
# LADCSMP
All legal and defence policy chief legal aid defence counsel deputy legal aid defence counsel assistant legal aid defence counsel concept and all defence contact detail
<!-- लॉ न्यूज़ सेक्शन की शुरुआत -->
<div class="law-news-container">
    
    <!-- सुंदर और आकर्षक लॉ न्यूज़ बटन -->
    <button class="news-toggle-btn" onclick="toggleLawBook()">
        <span class="icon">⚖️</span> लॉ न्यूज़ (Law News) देखें
    </button>

    <!-- किताब जैसी दिखने वाली डिजाइन -->
    <div id="lawBook" class="law-book">
        <div class="book-cover">
            <h3>कानूनी समाचार पत्रिका (Live Law Journal)</h3>
            <p>गूगल शीट से सीधे अपडेटेड नवीनतम फैसले</p>
        </div>
        
        <!-- यहीं पर गूगल शीट से आकर न्यूज़ अपने आप जुड़ेगी -->
        <div class="book-pages" id="newsContainer">
            <p style="text-align:center; color:#888;">समाचार लोड हो रहे हैं...</p>
        </div>
    </div>
</div>

<!-- वेबसाइट को सुंदर बनाने के लिए डिज़ाइन (CSS) -->
<style>
    .law-news-container {
        font-family: 'Arial', sans-serif;
        margin: 20px auto;
        text-align: center;
        max-width: 600px;
        padding: 10px;
    }

    .news-toggle-btn {
        background: linear-gradient(135deg, #8B0000, #d32f2f);
        color: white;
        font-size: 18px;
        font-weight: bold;
        padding: 14px 28px;
        border: none;
        border-radius: 50px;
        cursor: pointer;
        box-shadow: 0 5px 15px rgba(0,0,0,0.3);
        transition: all 0.3s ease;
    }

    .news-toggle-btn:hover {
        transform: translateY(-3px);
        box-shadow: 0 8px 20px rgba(0,0,0,0.4);
    }

    .law-book {
        display: none;
        margin-top: 25px;
        background: #fdfaf2;
        border: 4px solid #8B0000;
        border-radius: 8px;
        box-shadow: 5px 5px 25px rgba(0,0,0,0.2);
        text-align: left;
        overflow: hidden;
        animation: openBook 0.5s ease-out;
    }

    @keyframes openBook {
        from { transform: scaleY(0); opacity: 0; }
        to { transform: scaleY(1); opacity: 1; }
    }

    .book-cover {
        background: #8B0000;
        color: #fff;
        padding: 15px;
        text-align: center;
        border-bottom: 2px solid #660000;
    }

    .book-cover h3 { margin: 0; font-size: 20px; }
    .book-cover p { margin: 5px 0 0 0; font-size: 13px; color: #ffcccc; }

    .book-pages { padding: 15px; }

    .news-item {
        border-bottom: 1px solid #e0dacc;
        margin-bottom: 5px;
    }

    .news-title {
        font-size: 16px;
        font-weight: bold;
        color: #333;
        padding: 12px;
        background: #f5efe0;
        cursor: pointer;
        display: flex;
        justify-content: space-between;
        align-items: center;
        border-radius: 4px;
    }

    .news-title:hover {
        background: #ebe2cc;
        color: #8B0000;
    }

    .news-content {
        display: none;
        padding: 15px;
        background: #fff;
        border-left: 3px solid #8B0000;
        color: #444;
        font-size: 14px;
        line-height: 1.6;
    }

    .arrow {
        font-size: 12px;
        transition: transform 0.3s;
    }
    
    .news-item.active .arrow {
        transform: rotate(180deg);
    }
</style>

<!-- गूगल शीट से डेटा खींचने का ऑटोमैटिक कोड (JavaScript) -->
<script>
    <script>
// ==========================================
// 🔴 आपकी असली गूगल शीट की ID यहाँ सेट है
// ==========================================
const sheetId = '1AMPH4jZfE843Ltv3o1W4CzqDdusv0vfe-l20iFaE36U'; 
const base = `https://docs.google.com/spreadsheets/d/${sheetId}/gviz/tq?tqx=out:json`;

// किताब को खोलने/बंद करने के लिए फंक्शन
function toggleLawBook() {
    var book = document.getElementById("lawBook");
    if (book.style.display === "none" || book.style.display === "") {
        book.style.display = "block";
    } else {
        book.style.display = "none";
    }
}

// गूगल शीट से लाइव समाचार खींचने का फंक्शन
document.addEventListener("DOMContentLoaded", function() {
    fetch(base)
        .then(res => res.text())
        .then(data => {
            const jsonData = JSON.parse(data.substring(47, data.length - 2));
            const rows = jsonData.table.rows;
            let html = "";

            if (!rows || rows.length === 0) {
                html = `<div style="text-align:center;padding:20px;color:#9a7a50;">📰 अभी कोई समाचार उपलब्ध नहीं है।</div>`;
            } else {
                for (let i = 0; i < rows.length; i++) {
                    const title = rows[i].c[0] ? rows[i].c[0].v : "मुख्य शीर्षक उपलब्ध नहीं है";
                    const newsText = rows[i].c[1] ? rows[i].c[1].v : "समाचार का विवरण अभी उपलब्ध नहीं है।";

                    html += `
                        <div class="news-item" style="margin-bottom: 15px; padding: 10px; border-bottom: 1px dashed #c8a878;">
                            <h4 style="color: #2c1810; margin-bottom: 5px; font-weight: bold;">📘 ${title}</h4>
                            <p style="color: #2a1a0a; font-size: 14px; line-height: 1.6; text-align: justify; white-space: pre-line;">${newsText}</p>
                        </div>
                    `;
                }
            }
            // पुराने डिब्बे (newsContainer) में लाइव न्यूज़ डालना
            const container = document.getElementById("newsContainer") || document.getElementById("lawBook");
            if(container) {
                container.innerHTML = html;
            }
        })
        .catch(error => {
            console.error(error);
            const container = document.getElementById("newsContainer") || document.getElementById("lawBook");
            if(container) {
                container.innerHTML = `
                    <div style="text-align:center; padding:10px; color:red; font-size:13px; font-weight:bold;">
                        ⚠️ न्यूज़ लोड करने में तकनीकी समस्या आई!
                    </div>`;
            }
        });
});
</script>
