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
    // 1. यहाँ अपनी असली गूगल शीट की ID डालें
    const sheetId = 'अपनी_GOOGLE_SHEET_ID_यहाँ_डालें'; 
    const base = `https://docs.google.com/spreadsheets/d/${sheetId}/gviz/tq?tqx=out:json`;

    // किताब को खोलने/बंद करने के लिए
    function toggleLawBook() {
        var book = document.getElementById("lawBook");
        book.style.display = (book.style.display === "none" || book.style.display === "") ? "block" : "none";
    }

    // गूगल शीट से न्यूज़ लोड करने का फंक्शन
    document.addEventListener("DOMContentLoaded", function() {
        fetch(base)
            .then(res => res.text())
            .then(data => {
                // गूगल के एक्स्ट्रा टेक्स्ट को हटाकर शुद्ध JSON निकालना
                const jsonData = JSON.parse(data.substring(47, data.length - 2));
                const rows = jsonData.table.rows;
                let html = "";

                // पहली लाइन को छोड़कर बाकी सभी न्यूज़ लाइन्स को पढ़ना
                for (let i = 0; i < rows.length; i++) {
                    const title = rows[i].c[0] ? rows[i].c[0].v : "बिना टाइटल की न्यूज़";
                    const newsText = rows[i].c[1] ? rows[i].c[1].v : "कोई विवरण नहीं है।";

                    html += `
                        <div class="news-item">
                            <div class="news-title" onclick="toggleNewsContent(this)">
                                <span>📘 ${title}</span>
                                <span class="arrow">▼</span>
                            </div>
                            <div class="news-content">
                                <p>${newsText}</p>
                            </div>
                        </div>
                    `;
                }
                document.getElementById("newsContainer").innerHTML = html;
            })
            .catch(error => {
                console.error(error);
                document.getElementById("newsContainer").innerHTML = "<p style='color:red; text-align:center;'>न्यूज़ लोड करने में समस्या आई। कृपया शीट की एक्सेस सेटिंग चेक करें।</p>";
            });
    });

    // खबर को विस्तार में खोलने के लिए
    function toggleNewsContent(element) {
        var item = element.parentElement;
        var content = element.nextElementSibling;
        
        if (content.style.display === "block") {
            content.style.display = "none";
            item.classList.remove("active");
        } else {
            content.style.display = "block";
            item.classList.add("active");
        }
    }
</script>
<!-- लॉ न्यूज़ सेक्शन की समाप्ति -->
