<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>النظام الذكي لحساب الأضرار والخسائر والتعويضات</title>
  <!-- Font Awesome للأيقونات -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <!-- استخدام خط "Cairo" لإحساس ملكي وفخم -->
  <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;600;700&display=swap" rel="stylesheet">
  <!-- مكتبة jsPDF للتصدير إلى PDF -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
  <!-- Chart.js (إذا دعت الحاجة) -->
  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
  
<style>
    :root {
      --primary-color: #1B2631; /* لون أزرق داكن ملكي */
      --secondary-color: #212F3D; /* لون أغمق للفخامة */
      --accent-color: #F1C40F; /* ذهبي ملكي */
      --bg-color: #F5F0E1; /* خلفية بيج أنيقة */
      --section-bg: linear-gradient(135deg, #2E4053, #1B2631); /* مزيج ألوان فاخر */
      --section-border: var(--accent-color);
      --text-color: #ECF0F1;
      --input-bg: #2C3E50; /* لون المدخلات */
    }

    :root {
       /* بني ملكي */
       /* أسود داكن */
       /* ذهبي فخم */
       /* بيج فاتح */
       /* بيج ذهبي */
      
       /* بني راقٍ */
       /* بيج فاتح */
      --animation-speed: 0.8s;
    }

    body {
      background: var(--bg-color);
      color: var(--text-color);
      font-family: 'Cairo', sans-serif;
    }

    .container {
      background: var(--section-bg);
      border: 3px solid var(--accent-color);
      box-shadow: 0 15px 40px rgba(0,0,0,0.2);
    }

    .header {
      background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
      color: #fff;
      border-bottom: 5px solid var(--accent-color);
      box-shadow: 0 10px 40px rgba(0,0,0,0.5);
    }

    .header h1, .header h2 {
      color: var(--accent-color);
    }

    .section {
      background: var(--section-bg);
      border: 2px solid var(--accent-color);
      box-shadow: 0 8px 20px rgba(0,0,0,0.1);
    }

    .section-title {
      color: var(--accent-color);
      border-bottom: 3px solid var(--accent-color);
    }

    .input-group label {
      color: var(--primary-color);
    }

    input, select, textarea {
      background: var(--input-bg);
      border: 2px solid var(--primary-color);
      color: var(--primary-color);
    }

    .btn {
      background: var(--primary-color);
      border: 2px solid var(--accent-color);
      color: #fff;
    }

    .btn:hover {
      background: var(--secondary-color);
    }

    .footer {
      background: var(--primary-color);
      border-top: 5px solid var(--accent-color);
      color: #fff;
    }


    @media (max-width: 768px) {
      .container {
        width: 100%;
        padding: 10px;
      }
      .header h1 {
        font-size: 2rem;
      }
      .section-title {
        font-size: 1.4rem;
      }
      input, select, textarea {
        font-size: 1rem;
        padding: 8px;
      }
    }
</style>
<style>
    /* إعدادات الألوان والخطوط – ألوان داكنة فاخرة */
    :root {
      
      
      
      
      
      
      
      
      --animation-speed: 0.8s;
    }
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: 'Cairo', sans-serif;
    }
    body {
      background: var(--bg-color);
      color: var(--text-color);
      line-height: 1.8;
      position: relative;
      overflow-x: hidden;
      padding-bottom: 100px;
    }
    /* تأثير فقاعات متحركة في الخلفية */
    body::before {
      content: "";
      position: fixed;
      top: 0; left: 0;
      width: 100%;
      height: 100%;
      background: radial-gradient(circle, rgba(241,196,15,0.25) 1px, transparent 1px);
      background-size: 40px 40px;
      opacity: 0.3;
      z-index: -2;
      animation: moveBubbles 30s linear infinite;
    }
    @keyframes moveBubbles {
      from { transform: translateY(0); }
      to { transform: translateY(-300px); }
    }
    .container {
      width: 95%;
      max-width: 1400px;
      margin: 40px auto;
      padding: 30px;
      background: var(--section-bg);
      border-radius: 20px;
      box-shadow: 0 15px 40px rgba(0,0,0,0.35);
      position: relative;
      overflow: hidden;
    }
    /* الهيدر */
    .header {
      background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
      color: #fff;
      padding: 3rem 2rem;
      text-align: center;
      border-radius: 20px;
      margin-bottom: 20px;
      position: relative;
      overflow: hidden;
      box-shadow: 0 10px 40px rgba(0,0,0,0.5);
      animation: slideIn var(--animation-speed) ease-out;
    }
    .header::after {
      content: "";
      position: absolute;
      bottom: 0;
      left: 0;
      width: 100%;
      height: 10px;
      background: linear-gradient(90deg, transparent, var(--accent-color), transparent);
      animation: glow 3s infinite;
    }
    @keyframes slideIn {
      from { transform: translateY(20px); opacity: 0; }
      to { transform: translateY(0); opacity: 1; }
    }
    @keyframes glow {
      0%, 100% { opacity: 0.4; }
      50% { opacity: 1; }
    }
    .header h1 { font-size: 3.4rem; margin-bottom: 0.5rem; }
    .header h2 { font-size: 1.8rem; margin-bottom: 1rem; }
    .header a { color: #FFD700; text-decoration: none; font-weight: bold; }
    .reference-number {
      background: var(--accent-color);
      padding: 1rem 2rem;
      border-radius: 30px;
      margin-top: 1.5rem;
      display: inline-block;
      font-weight: 700;
      box-shadow: 0 4px 10px rgba(0,0,0,0.4);
    }
    /* شريط الأخبار المتحرك (Ticker) */
    .news-ticker {
      background: linear-gradient(135deg, #212F3D, #1B2631);
      border: 2px solid var(--accent-color);
      border-radius: 10px;
      overflow: hidden;
      white-space: nowrap;
      padding: 10px 20px;
      margin-bottom: 30px;
      box-shadow: 0 8px 30px rgba(0,0,0,0.5);
    }
    .news-ticker .ticker-content {
      display: inline-block;
      /* الدورة 3 دقائق = 180 ثانية */
      animation: tickerScroll 180s linear infinite;
    }
    @keyframes tickerScroll {
      from { transform: translateX(-100%); }
      to { transform: translateX(0); }
    }
    .news-ticker span {
      margin-right: 50px;
      font-size: 1rem;
      color: var(--accent-color);
    }
    .news-ticker .contact-info {
      font-size: 0.9rem;
      font-style: italic;
      margin-right: 50px;
      color: var(--accent-color);
    }
    /* الأقسام العامة */
    .section {
      background: linear-gradient(135deg, #2C3E50, #1B2631);
      border-radius: 15px;
      padding: 2.5rem;
      margin-bottom: 25px;
      border: 2px double var(--accent-color);
      position: relative;
      overflow: hidden;
      animation: fadeIn 0.8s ease-out;
    }
    @keyframes fadeIn {
      from { opacity: 0; transform: scale(0.95); }
      to { opacity: 1; transform: scale(1); }
    }
    .section-title {
      color: var(--accent-color);
      margin-bottom: 1rem;
      display: flex;
      align-items: center;
      gap: 15px;
      font-size: 1.8rem;
      position: relative;
      padding-bottom: 8px;
      border-bottom: 2px solid var(--accent-color);
    }
    .section-title i { font-size: 2rem; }
    .section-intro {
      background: linear-gradient(135deg, #34495E, #2C3E50);
      padding: 1.8rem;
      border-radius: 10px;
      margin-bottom: 2rem;
      border-left: 4px solid var(--accent-color);
      font-size: 1.1rem;
      line-height: 1.6;
      color: #ECF0F1;
    }
    .input-group { margin-bottom: 2rem; }
    label { margin-bottom: 0.8rem; font-weight: bold; color: var(--accent-color); }
    input, select, textarea {
      width: 100%;
      padding: 1rem;
      border: 2px solid #555;
      border-radius: 8px;
      font-size: 1.1rem;
      transition: all 0.3s ease;
      margin-bottom: 1rem;
      background: var(--input-bg);
      color: #ECF0F1;
    }
    input:focus, select:focus, textarea:focus { border-color: var(--accent-color); outline: none; }
    .dynamic-list { margin: 1.5rem 0; }
    .item-card {
      background: #212F3D;
      border: 2px solid #555;
      padding: 1.5rem;
      margin: 10px 0;
      border-radius: 10px;
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 1rem;
      align-items: center;
      position: relative;
      animation: fadeIn 0.8s ease-out;
    }
    .add-btn, .btn {
      background: var(--primary-color);
      color: #fff;
      border: 2px double var(--accent-color);
      padding: 1rem 2rem;
      border-radius: 10px;
      cursor: pointer;
      transition: all 0.3s ease;
      display: inline-flex;
      align-items: center;
      gap: 10px;
      margin: 0.5rem 0;
    }
    .add-btn:hover, .btn:hover { background: var(--secondary-color); transform: scale(1.02); }
    .remove-btn {
      background: var(--accent-color);
      color: #fff;
      border: none;
      padding: 0.6rem 1.2rem;
      border-radius: 6px;
      cursor: pointer;
      position: absolute;
      left: 15px;
      bottom: 15px;
      transition: transform 0.3s ease;
    }
    .remove-btn:hover { transform: scale(1.1); }
    .total-box {
      background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
      color: #fff;
      padding: 2rem;
      border-radius: 15px;
      text-align: center;
      margin-top: 2rem;
      animation: pulse 2s infinite;
    }
    @keyframes pulse {
      0% { transform: scale(1); }
      50% { transform: scale(1.03); }
      100% { transform: scale(1); }
    }
    .legal-references {
      background: linear-gradient(135deg, #2C3E50, #212F3D);
      padding: 2rem;
      border-radius: 12px;
      margin-top: 3rem;
      border: 2px dashed var(--accent-color);
      font-size: 1rem;
      line-height: 1.6;
      color: #ECF0F1;
    }
    /* تحسين الفوتر */
    .footer {
      background: linear-gradient(135deg, var(--secondary-color), var(--primary-color));
      color: #fff;
      padding: 2rem;
      text-align: center;
      border-radius: 15px;
      margin-top: 20px;
      position: relative;
      overflow: hidden;
      border: 2px solid var(--accent-color);
      box-shadow: 0 8px 30px rgba(0,0,0,0.45);
    }
    .footer .contact-box {
      display: inline-block;
      background: rgba(0,0,0,0.3);
      padding: 10px 20px;
      margin: 5px;
      border-radius: 25px;
      transition: transform 0.3s ease;
    }
    .footer .contact-box:hover {
      transform: scale(1.05);
    }
    .footer .contact-box i {
      margin-left: 8px;
      color: var(--accent-color);
      animation: iconPulse 2s infinite;
    }
    @keyframes iconPulse {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.1); }
    }
    .footer a {
      color: var(--accent-color);
      text-decoration: none;
      font-weight: bold;
    }
    .footer::before {
      content: "";
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: none;
    }
    /* قسم أزرار الإجراءات */
    .actions {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 10px;
      margin: 30px 0;
    }
    .actions button {
      background: var(--primary-color);
      color: #fff;
      border: 2px double var(--accent-color);
      padding: 1rem 2rem;
      border-radius: 10px;
      cursor: pointer;
      transition: all 0.3s ease;
      font-size: 1rem;
      display: inline-flex;
      align-items: center;
      gap: 10px;
    }
    .actions button:hover {
      background: var(--secondary-color);
      transform: scale(1.02);
    }
    /* أقسام إضافية: دليل المستخدم، إدارة ملفات المطالبات، الوثائق، FAQ */
    .extra-section {
      background: linear-gradient(135deg, #1B2631, #212F3D);
      border-radius: 15px;
      padding: 2.5rem;
      margin-bottom: 25px;
      border: 2px double var(--accent-color);
      position: relative;
      overflow: hidden;
      animation: fadeIn 0.8s ease-out;
      color: #ECF0F1;
    }
    .extra-section .section-title {
      color: var(--accent-color);
      border-bottom: 2px solid var(--accent-color);
    }
    .extra-section .section-intro {
      background: linear-gradient(135deg, #34495E, #2C3E50);
      padding: 1.8rem;
      border-radius: 10px;
      margin-bottom: 2rem;
      border-left: 4px solid var(--accent-color);
      font-size: 1.1rem;
      line-height: 1.6;
      color: #ECF0F1;
    }
    /* قسم دليل المستخدم */
    .user-guide {
      background: linear-gradient(135deg, #2C3E50, #1B2631);
      border-radius: 15px;
      padding: 2rem;
      margin-bottom: 25px;
      border: 2px solid var(--accent-color);
      box-shadow: 0 8px 30px rgba(0,0,0,0.45);
    }
    .user-guide h2 {
      color: var(--accent-color);
      margin-bottom: 1rem;
    }
    .user-guide p, .user-guide ul, .user-guide ol {
      font-size: 1rem;
      line-height: 1.6;
      margin: 10px 0;
      text-align: justify;
    }
    /* قسم الوثائق والمستندات والدلائل */
    .documents-section {
      background: linear-gradient(135deg, #2C3E50, #1B2631);
      border-radius: 15px;
      padding: 2rem;
      margin-bottom: 25px;
      border: 2px solid var(--accent-color);
      box-shadow: 0 8px 30px rgba(0,0,0,0.45);
    }
    .documents-section h2 {
      color: var(--accent-color);
      margin-bottom: 1rem;
    }
    .documents-section .section-intro {
      background: linear-gradient(135deg, #34495E, #2C3E50);
      padding: 1.5rem;
      border-radius: 10px;
      margin-bottom: 1rem;
      border-left: 4px solid var(--accent-color);
      font-size: 1rem;
      line-height: 1.6;
    }
    .documents-section .file-upload {
      margin: 15px 0;
    }
    .documents-section input[type="file"] {
      display: block;
      width: 100%;
      margin-bottom: 10px;
      background: var(--input-bg);
      color: #ECF0F1;
      border: 2px solid #555;
      padding: 1rem;
      border-radius: 8px;
    }
    .documents-section .approve-btn {
      background: var(--primary-color);
      color: #fff;
      border: 2px double var(--accent-color);
      padding: 1rem 2rem;
      border-radius: 10px;
      cursor: pointer;
      transition: all 0.3s ease;
      display: inline-flex;
      align-items: center;
      gap: 10px;
    }
    .documents-section .approve-btn:hover {
      background: var(--secondary-color);
      transform: scale(1.02);
    }
    /* قسم الأسئلة الشائعة (FAQ) */
    .faq-section {
      background: linear-gradient(135deg, #2C3E50, #1B2631);
      border-radius: 15px;
      padding: 2rem;
      margin-bottom: 25px;
      border: 2px solid var(--accent-color);
      box-shadow: 0 8px 30px rgba(0,0,0,0.45);
    }
    .faq-section h2 {
      color: var(--accent-color);
      margin-bottom: 1rem;
      text-align: center;
    }
    .faq-item {
      border-bottom: 1px solid var(--accent-color);
      padding: 10px 0;
      cursor: pointer;
    }
    .faq-item:last-child {
      border-bottom: none;
    }
    .faq-item h3 {
      font-size: 1.2rem;
      margin-bottom: 5px;
      position: relative;
    }
    .faq-item h3::after {
      content: "\f107";
      font-family: "Font Awesome 6 Free";
      font-weight: 900;
      position: absolute;
      left: 0;
      top: 0;
      transition: transform 0.3s ease;
    }
    .faq-item.active h3::after {
      transform: rotate(180deg);
    }
    .faq-answer {
      max-height: 0;
      overflow: hidden;
      transition: max-height 0.5s ease;
      font-size: 1rem;
      line-height: 1.6;
      margin-top: 5px;
    }
    
    /* ميديا كويري للأجهزة الصغيرة */
    @media (max-width: 768px) {
      .header h1 { font-size: 2.8rem; }
      .header h2 { font-size: 1.4rem; }
      .section-title { font-size: 1.6rem; }
    }
    
    @media print {
      body { font-size: 12pt; background: white !important; }
      button { display: none !important; }
    }
  
    @media (max-width: 768px) {
      .container {
        width: 100%;
        padding: 10px;
      }
      .header h1 {
        font-size: 2rem;
      }
      .section-title {
        font-size: 1.4rem;
      }
      input, select, textarea {
        font-size: 1rem;
        padding: 8px;
      }
    }
</style>
<style>
  #finalSummary table {
    width: 100%;
    border-collapse: collapse;
    margin-top: 15px;
    background-color: #2C3E50;
    color: #F1C40F;
    border-radius: 10px;
    overflow: hidden;
    box-shadow: 0 0 15px rgba(0,0,0,0.3);
  }
  #finalSummary th, #finalSummary td {
    border: 2px solid #F1C40F;
    padding: 12px;
    text-align: center;
    font-size: 1.1rem;
  }
  #finalSummary th {
    background-color: #F1C40F;
    color: #2C3E50;
    font-weight: bold;
  }
  #finalSummary tbody tr:nth-child(even) {
    background-color: #34495E;
  }
  #finalSummary tbody tr:nth-child(odd) {
    background-color: #2C3E50;
  }
  #finalSummary tr.total-row {
    font-weight: bold;
    background-color: #F1C40F;
    color: #2C3E50;
    font-size: 1.2rem;
  }
  .btn-calculate {
    background-color: #F1C40F;
    color: #2C3E50;
    font-weight: bold;
    padding: 10px 20px;
    border-radius: 8px;
    border: none;
    cursor: pointer;
    transition: 0.3s ease-in-out;
  }
  .btn-calculate:hover {
    background-color: #D4AC0D;
  }
  /* تنسيق الجدول في قسم الخلاصة النهائية */
        #finalSummary table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 15px;
            table-layout: fixed;
            /* لجعل الأعمدة متساوية */
        }

        #finalSummary th,
        #finalSummary td {
            border: 1px solid var(--accent-color);
            padding: 10px;
            text-align: center;
            font-size: 1.1rem;
            overflow: hidden;
            /* لإخفاء النص الزائد */
            white-space: nowrap;
            /* لمنع التفاف النص */
            text-overflow: ellipsis;
            /* لإضافة علامة (...) للنص الزائد */
        }

        #finalSummary th {
            background-color: var(--primary-color);
            color: var(--accent-color);
            font-weight: bold;
        }

        #finalSummary td {
            color: #FFD700;
            /* اللون الذهبي للنص */
        }

        #finalSummary tr.total-row {
            background-color: var(--accent-color);
            color: var(--primary-color);
            font-weight: bold;
        }

        /* تحديد عرض ثابت للأعمدة (اختياري) */
        #finalSummary .column-1 {
            width: 5%;
        }

        #finalSummary .column-2 {
            width: 55%;
        }

        #finalSummary .column-3,
        #finalSummary .column-4 {
            width: 20%;
        }
</style>
<script>
  function calculateFinalSummary() {
    let totalYER = 0, totalUSD = 0;
    const sectionIDs = [
      'fixedAssetsTotal', 'inventoryDamageTotal', 'humanTotalYER', 'financialDirectTotal',
      'operationalTotalYER', 'delayedTotalYER', 'institutionalTotalYER', 'legalClaimsTotalYER',
      'rehabTotalYER', 'productionDelayTotalYER', 'competitiveLossTotalYER', 'intangibleTotalYER',
      'techDamageTotalYER', 'reputationLossTotalYER', 'futurePlansTotalYER', 'otherTotalYER'
    ];
    const sectionUSDIDs = [
      'fixedAssetsTotalUSD', 'inventoryDamageTotalUSD', 'humanTotalUSD', 'financialDirectTotalUSD',
      'operationalTotalUSD', 'delayedTotalUSD', 'institutionalTotalUSD', 'legalClaimsTotalUSD',
      'rehabTotalUSD', 'productionDelayTotalUSD', 'competitiveLossTotalUSD', 'intangibleTotalUSD',
      'techDamageTotalUSD', 'reputationLossTotalUSD', 'futurePlansTotalUSD', 'otherTotalUSD'
    ];

    sectionIDs.forEach(id => {
      let value = parseFloat(document.getElementById(id).innerText.replace(/,/g, '')) || 0;
      totalYER += value;
    });
    sectionUSDIDs.forEach(id => {
      let value = parseFloat(document.getElementById(id).innerText.replace(/,/g, '')) || 0;
      totalUSD += value;
    });

    document.getElementById('totalSumYER').innerText = totalYER.toLocaleString();
    document.getElementById('totalSumUSD').innerText = totalUSD.toLocaleString();
  }
</script>

</head>
<body>

<script>
function addFuturePlansLoss() {
    let container = document.getElementById("futurePlansLoss");
    let newItem = document.createElement("div");
    newItem.classList.add("item-card");
    newItem.innerHTML = `
        <input type="text" placeholder="مثال: تأجيل مشروع استثماري">
        <input type="number" placeholder="المبلغ (ريال)" oninput="calculateSectionTotal('futurePlansLoss','futurePlansTotalYER','futurePlansTotalUSD')">
        <input type="number" placeholder="مدة التأثير (بالسنوات)" oninput="calculateSectionTotal('futurePlansLoss','futurePlansTotalYER','futurePlansTotalUSD')">
        <select class="currency">
            <option value="YER">ريال يمني</option>
            <option value="USD">دولار أمريكي</option>
        </select>
        <button class="remove-btn" onclick="this.parentElement.remove(); calculateSectionTotal('futurePlansLoss','futurePlansTotalYER','futurePlansTotalUSD')">
            <i class="fas fa-times"></i> حذف
        </button>
    `;
    container.appendChild(newItem);
}
</script>

  <div class="container">
    <!-- الهيدر -->
    <div class="header">
    <img src="https://guyc-ye.com/wp-content/uploads/2024/05/GUYC-Log33o-copy.png" alt="شعار الاتحاد العام للمقاولين اليمنيين" style="max-height:180px; background: transparent; margin-bottom:10px;">
    <h1>الإستمارة الذكية لتسجيل الأضرار والخسائر</h1>
    <h2>قطاع المقاولات اليمني - الاتحاد العام للمقاولين اليمنيين</h2>
    <!-- باقي محتويات الهيدر -->
    
      <div class="reference-number" id="fileNumber"></div>
      <div class="timestamp" id="currentDate"></div>
      <p>زوروا موقعنا: <a href="https://guyc-ye.com/" target="_blank">guyc-ye.com</a></p>
    </div>
    
    <!-- شريط الأخبار المتحرك (Ticker) -->
    <div class="news-ticker">
      <div class="ticker-content">
        <span><strong>مقدمة:</strong> يواجه قطاع المقاولات في اليمن تحديات كبيرة بسبب الحرب والصراع المستمر، مما يؤدي إلى خسائر مادية جسيمة.</span>
        <span><strong>هدف الدليل:</strong> تزويد المقاولين بخطة عمل واضحة للمطالبة بالتعويضات العادلة وفقًا للمعايير الدولية.</span>
        <span><strong>أهمية الدليل:</strong> توثيق الأضرار، حساب التعويضات، وتقديم المطالبات بشكل احترافي.</span>
        <span><strong>المراحل:</strong> التوثيق، الحساب، التقديم، والمتابعة القانونية.</span>
        <span class="contact-info"><strong>للتواصل:</strong> 01-450553 | info@guyc-ye.com | guyc-ye.com</span>
      </div>
    </div>
    
    <!-- قسم مقدمة تعريفية -->
    <div class="section">
      <div class="section-title" style="color: #F1C40F;">
        <i class="fas fa-info-circle"></i>
        <h2>مقدمة تعريفية</h2>
      </div>
      <div class="section-intro">
        <p>
          يُعد هذا النظام منصة شاملة لتوثيق وحساب كافة أنواع الأضرار والخسائر الناتجة عن الأزمات والحروب والنزاعات المسلحة وفقًا للمعايير الدولية وأفضل الممارسات العالمية. يساعد النظام المقاولين على إعداد ملف مطالبة متكامل ودقيق مدعومًا بالأدلة والمرجعيات القانونية.
        </p>
        <ul>
          <li><strong>الفئات المستهدفة:</strong> المقاولون، الشركات الإنشائية، الجهات الحكومية، منظمات المجتمع المدني.</li>
          <li><strong>أهمية النظام:</strong> توثيق شامل وحساب دقيق وإعداد ملف مطالبة متكامل.</li>
          <li><strong>تنويه:</strong> تُستخدم البيانات للتقييم الأولي وقد تخضع للمراجعة من الجهات المختصة.</li>
        </ul>
      </div>
    </div>
    
    <!-- قسم دليل المستخدم -->
    <div class="extra-section user-guide" id="userGuideSection">
      <h2>دليل المستخدم</h2>
      <p>
        يحتوي هذا القسم على تعليمات مفصلة حول كيفية استخدام النظام وإعداد ملف المطالبة:
      </p>
      <ol>
        <li>ادخل بيانات الشركة والمقاول في قسم "البيانات الأساسية".</li>
        <li>حدد سعر الصرف في قسم "إعدادات العملة".</li>
        <li>أدخل تفاصيل كل بند في أقسام الأضرار المختلفة مع تحديد القيمة، النسبة، والمدة.</li>
        <li>استخدم زر "إضافة بند" لإدراج المزيد من البنود عند الحاجة.</li>
        <li>اضغط على زر الحساب في كل قسم لمعاينة الإجمالي الفرعي لذلك القسم.</li>
        <li>راجع نتائج الخلاصة النهائية لتجميع كافة النتائج.</li>
      </ol>
      <p>
        <strong>ملاحظة:</strong> تأكد من مراجعة كافة البيانات والوثائق قبل تقديم ملف المطالبة.
      </p>
    </div>
    
    <!-- البيانات الأساسية -->
    <div class="section">
      <div class="section-title" style="color: #F1C40F;">
        <i class="fas fa-building"></i>
        <h2>البيانات الأساسية</h2>
      </div>
      <div class="input-group">
        <label style="color: #F1C40F;">اسم الشركة/المؤسسة:</label>
        <input type="text" id="companyName" placeholder="أدخل اسم الشركة" required>
      </div>
      <div class="input-group">
        <label style="color: #F1C40F;">اسم المقاول المسؤول:</label>
        <input type="text" id="contractorName" placeholder="أدخل اسم المقاول" required>
      </div>
      
    <div class="input-group">
      <label style="color: #F1C40F;">رقم السجل التجاري:</label>
      <input type="text" id="businessRegNumber" placeholder="أدخل رقم السجل التجاري">
    </div>
    <div class="input-group">
      <label style="color: #F1C40F;">نوع النشاط / التخصص:</label>
      <input type="text" id="businessType" placeholder="أدخل نوع النشاط أو التخصص">
    </div>
    <div class="input-group">
      <label style="color: #F1C40F;">تصنيف الشركة:</label>
      <input type="text" id="companyClassification" placeholder="أدخل تصنيف الشركة إن وجد">
    </div>
    <div class="input-group">
      <label style="color: #F1C40F;">حجم الشركة:</label>
      <select id="companySize">
        <option value="small">شركة صغيرة</option>
        <option value="medium">شركة متوسطة</option>
        <option value="large">شركة كبيرة</option>
      </select>
    </div>
<div class="input-group">
        <label style="color: #F1C40F;">رقم الهاتف:</label>
        <input type="tel" id="phoneNumber" placeholder="أدخل رقم الهاتف" required>
      </div>
    </div>
    
    <!-- إعدادات العملة -->
    <div class="section">
      <div class="section-title" style="color: #F1C40F;">
        <i class="fas fa-coins"></i>
        <h2>إعدادات العملة</h2>
      </div>
      <div class="input-group">
        <label style="color: #F1C40F;">سعر صرف الدولار (USD) مقابل الريال (YER):</label>
        <input type="number" id="exchangeRate" placeholder="أدخل سعر الصرف" required>
      </div>
    </div>
    
    <!-- قسم حساب الأضرار وأنواعها -->
    <div class="section" id="damageCalculators">
      <div class="section-title" style="color: #F1C40F;">
        <i class="fas fa-calculator"></i>
        <h2>قسم حساب الأضرار وأنواعها</h2>
      </div>
      <div class="section-intro">
        <p>
          يتم تقسيم الأضرار إلى ثلاث مجموعات: المباشرة، غير المباشرة، وأضرار أخرى. لكل نوع قسم خاص به يحتوي على شرح تعريفي، مثال، طريقة الاحتساب والمرجع القانوني، مع إمكانية إضافة وحذف البنود وحساب النتيجة بالريال والدولار.
        </p>
      </div>
      
      <!-- (أولاً: الأضرار المباشرة) -->
      <!-- 1. أضرار الأصول الثابتة -->
      <div class="section" id="fixedAssets">
        <div class="section-title" style="color: #F1C40F;">
          <i class="fas fa-building"></i>
          <h2>أضرار الأصول الثابتة</h2>
        </div>
        <div class="section-intro">
          <p>
            تُحسب أضرار الأصول الثابتة (مثل المباني، المعدات، الآلات، والأدوات) بناءً على تكلفة الاستبدال أو الإصلاح مع تطبيق نسب الإهلاك. <br>
            <strong>مثال:</strong> إذا دُمّرت منشأة بنسبة 80%، يُحسب التعويض بناءً على 80% من القيمة السوقية.<br>
            <strong>المرجع القانوني:</strong> معايير RICS وFIDIC.
          </p>
        </div>
        <div class="dynamic-list" id="fixedAssets">
          <div class="item-card">
            <input type="text" placeholder="مثال: مبنى رئيسي">
            <input type="number" placeholder="قيمة الضرر (ريال)" oninput="calculateSectionTotal('fixedAssets','fixedAssetsTotal','fixedAssetsTotalUSD')">
            <select class="severity" oninput="calculateSectionTotal('fixedAssets','fixedAssetsTotal','fixedAssetsTotalUSD')">
              <option value="1">100%</option>
              <option value="0.8">80%</option>
              <option value="0.5">50%</option>
            </select>
            <input type="number" placeholder="مدة الضرر (بالسنوات)" oninput="calculateSectionTotal('fixedAssets','fixedAssetsTotal','fixedAssetsTotalUSD')">
            <select class="currency">
              <option value="YER">ريال يمني</option>
              <option value="USD">دولار أمريكي</option>
            </select>
            <button class="remove-btn" onclick="this.parentElement.remove(); calculateSectionTotal('fixedAssets','fixedAssetsTotal','fixedAssetsTotalUSD')">
              <i class="fas fa-times"></i> حذف
            </button>
            <button class="add-btn" onclick="addDamage('fixedAssets')">
              <i class="fas fa-plus"></i> إضافة بند
            </button>
          </div>
        </div>
        <div class="actions">
          <button class="btn" onclick="calculateSectionTotal('fixedAssets','fixedAssetsTotal','fixedAssetsTotalUSD')">
            <i class="fas fa-calculator"></i> حساب أضرار الأصول الثابتة
          </button>
        </div>
        <div class="total-box">
          <p>النتيجة بالريال: <span id="fixedAssetsTotal">0</span></p>
          <p>النتيجة بالدولار: <span id="fixedAssetsTotalUSD">0</span></p>
        </div>
      </div>
      
      <!-- 2. أضرار المخزون والمواد -->
      <div class="section" id="inventoryDamage">
        <div class="section-title" style="color: #F1C40F;">
          <i class="fas fa-box"></i>
          <h2>أضرار المخزون والمواد</h2>
        </div>
        <div class="section-intro">
          <p>
            تُحسب أضرار المخزون والمواد (مثل المواد الخام) بناءً على القيمة السوقية أو الاستبدالية مع تطبيق نسبة الخسارة.<br>
            <strong>مثال:</strong> إذا تعرضت المواد لخسارة بنسبة 60%، يُحسب التعويض وفقًا لذلك.<br>
            <strong>المرجع القانوني:</strong> معايير IVSC.
          </p>
        </div>
        <div class="dynamic-list" id="inventoryDamage">
          <div class="item-card">
            <input type="text" placeholder="مثال: مواد خام">
            <input type="number" placeholder="قيمة الضرر (ريال)" oninput="calculateSectionTotal('inventoryDamage','inventoryDamageTotal','inventoryDamageTotalUSD')">
            <select class="severity" oninput="calculateSectionTotal('inventoryDamage','inventoryDamageTotal','inventoryDamageTotalUSD')">
              <option value="1">100%</option>
              <option value="0.6">60%</option>
            </select>
            <input type="number" placeholder="مدة الضرر (بالأشهر)" oninput="calculateSectionTotal('inventoryDamage','inventoryDamageTotal','inventoryDamageTotalUSD')">
            <select class="currency">
              <option value="YER">ريال يمني</option>
              <option value="USD">دولار أمريكي</option>
            </select>
            <button class="remove-btn" onclick="this.parentElement.remove(); calculateSectionTotal('inventoryDamage','inventoryDamageTotal','inventoryDamageTotalUSD')">
              <i class="fas fa-times"></i> حذف
            </button>
            <button class="add-btn" onclick="addDamage('inventoryDamage')">
              <i class="fas fa-plus"></i> إضافة بند
            </button>
          </div>
        </div>
        <div class="actions">
          <button class="btn" onclick="calculateSectionTotal('inventoryDamage','inventoryDamageTotal','inventoryDamageTotalUSD')">
            <i class="fas fa-calculator"></i> حساب أضرار المخزون والمواد
          </button>
        </div>
        <div class="total-box">
          <p>النتيجة بالريال: <span id="inventoryDamageTotal">0</span></p>
          <p>النتيجة بالدولار: <span id="inventoryDamageTotalUSD">0</span></p>
        </div>
      </div>
      
      <!-- 3. خسارة الكوادر البشرية -->
      <div class="section" id="humanLosses">
        <div class="section-title" style="color: #F1C40F;">
          <i class="fas fa-users"></i>
          <h2>خسارة الكوادر البشرية</h2>
        </div>
        <div class="section-intro">
          <p>
            تُحسب خسارة الكوادر البشرية (الفنية والإدارية) نتيجة الوفاة، الإصابة أو التسريح، بناءً على تكلفة التعويض وإعادة التوظيف والتأهيل.<br>
            <strong>مثال:</strong> إذا خسر مشروع شركة موظفًا أساسيًا، يُحسب التعويض وفقًا لتكلفة استبداله.<br>
            <strong>المرجع القانوني:</strong> معايير الأمم المتحدة والقوانين المحلية.
          </p>
        </div>
        <div class="dynamic-list" id="humanLosses">
          <div class="item-card">
            <input type="text" placeholder="مثال: موظف رئيسي">
            <input type="number" placeholder="قيمة التعويض (ريال)" oninput="calculateSectionTotal('humanLosses','humanTotalYER','humanTotalUSD')">
            <input type="number" placeholder="مدة الضرر (بالسنوات)" oninput="calculateSectionTotal('humanLosses','humanTotalYER','humanTotalUSD')">
            <select class="currency">
              <option value="YER">ريال يمني</option>
              <option value="USD">دولار أمريكي</option>
            </select>
            <button class="remove-btn" onclick="this.parentElement.remove(); calculateSectionTotal('humanLosses','humanTotalYER','humanTotalUSD')">
              <i class="fas fa-times"></i> حذف
            </button>
            <button class="add-btn" onclick="addDamage('humanLosses')">
              <i class="fas fa-plus"></i> إضافة بند
            </button>
          </div>
        </div>
        <div class="actions">
          <button class="btn" onclick="calculateSectionTotal('humanLosses','humanTotalYER','humanTotalUSD')">
            <i class="fas fa-calculator"></i> حساب خسارة الكوادر البشرية
          </button>
        </div>
        <div class="total-box">
          <p>النتيجة بالريال: <span id="humanTotalYER">0</span></p>
          <p>النتيجة بالدولار: <span id="humanTotalUSD">0</span></p>
        </div>
      </div>
      
      <!-- 4. الأضرار المالية والتدفقات النقدية -->
      <div class="section" id="financialDirect">
        <div class="section-title" style="color: #F1C40F;">
          <i class="fas fa-money-bill-wave"></i>
          <h2>الأضرار المالية والتدفقات النقدية</h2>
        </div>
        <div class="section-intro">
          <p>
            تُحسب الأضرار المالية والتدفقات النقدية (مثل فقدان الإيرادات والدفعات المتأخرة) بناءً على التحليل المالي للبيانات السابقة. <br>
            <strong>مثال:</strong> إذا توقفت الدفعات النقدية لشهر، يُحسب التعويض وفقًا للإيرادات المفقودة.<br>
            <strong>المرجع القانوني:</strong> IAS 37.
          </p>
        </div>
        <div class="dynamic-list" id="financialDirect">
          <div class="item-card">
            <input type="text" placeholder="مثال: خسارة إيرادات شهرية">
            <input type="number" placeholder="مقدار الخسارة (ريال)" oninput="calculateSectionTotal('financialDirect','financialDirectTotal','financialDirectTotalUSD')">
            <input type="number" placeholder="مدة الضرر (بالأشهر)" oninput="calculateSectionTotal('financialDirect','financialDirectTotal','financialDirectTotalUSD')">
            <select class="currency">
              <option value="YER">ريال يمني</option>
              <option value="USD">دولار أمريكي</option>
            </select>
            <button class="remove-btn" onclick="this.parentElement.remove(); calculateSectionTotal('financialDirect','financialDirectTotal','financialDirectTotalUSD')">
              <i class="fas fa-times"></i> حذف
            </button>
            <button class="add-btn" onclick="addDamage('financialDirect')">
              <i class="fas fa-plus"></i> إضافة بند
            </button>
          </div>
        </div>
        <div class="actions">
          <button class="btn" onclick="calculateSectionTotal('financialDirect','financialDirectTotal','financialDirectTotalUSD')">
            <i class="fas fa-calculator"></i> حساب الأضرار المالية
          </button>
        </div>
        <div class="total-box">
          <p>النتيجة بالريال: <span id="financialDirectTotal">0</span></p>
          <p>النتيجة بالدولار: <span id="financialDirectTotalUSD">0</span></p>
        </div>
      </div>
      
      <!-- 5. الخسائر التشغيلية -->
      <div class="section" id="operationalLosses">
        <div class="section-title" style="color: #F1C40F;">
          <i class="fas fa-cogs"></i>
          <h2>الخسائر التشغيلية</h2>
        </div>
        <div class="section-intro">
          <p>
            تُحسب الخسائر التشغيلية الناتجة عن توقف العمليات وتأخير تنفيذ المشاريع وفقاً للتكاليف الإضافية والإيرادات المفقودة. <br>
            <strong>مثال:</strong> إذا توقف الإنتاج لمدة 2 شهر، يُحسب التعويض بناءً على خسائر الإنتاج.<br>
            <strong>المرجع القانوني:</strong> معايير FIDIC.
          </p>
        </div>
        <div class="dynamic-list" id="operationalLosses">
          <div class="item-card">
            <input type="text" placeholder="مثال: توقف عملية الإنتاج">
            <input type="number" placeholder="المبلغ (ريال)" oninput="calculateSectionTotal('operationalLosses','operationalTotalYER','operationalTotalUSD')">
            <input type="number" placeholder="مدة التأخير (بالأشهر)" oninput="calculateSectionTotal('operationalLosses','operationalTotalYER','operationalTotalUSD')">
            <select class="currency">
              <option value="YER">ريال يمني</option>
              <option value="USD">دولار أمريكي</option>
            </select>
            <button class="remove-btn" onclick="this.parentElement.remove(); calculateSectionTotal('operationalLosses','operationalTotalYER','operationalTotalUSD')">
              <i class="fas fa-times"></i> حذف
            </button>
            <button class="add-btn" onclick="addDamage('operationalLosses')">
              <i class="fas fa-plus"></i> إضافة بند
            </button>
          </div>
        </div>
        <div class="actions">
          <button class="btn" onclick="calculateSectionTotal('operationalLosses','operationalTotalYER','operationalTotalUSD')">
            <i class="fas fa-calculator"></i> حساب الخسائر التشغيلية
          </button>
        </div>
        <div class="total-box">
          <p>النتيجة بالريال: <span id="operationalTotalYER">0</span></p>
          <p>النتيجة بالدولار: <span id="operationalTotalUSD">0</span></p>
        </div>
      </div>
      
      <!-- 6. خسائر تأخر صرف المستحقات -->
      <div class="section" id="delayedPayments">
        <div class="section-title" style="color: #F1C40F;">
          <i class="fas fa-hourglass-half"></i>
          <h2>خسائر تأخر صرف المستحقات</h2>
        </div>
        <div class="section-intro">
          <p>
            تُحسب خسائر تأخر صرف المستحقات بناءً على الإيرادات المفقودة والتكاليف الإضافية مثل الفوائد البنكية. <br>
            <strong>مثال:</strong> إذا تأخرت المدفوعات لمدة 3 أشهر، يُحسب التعويض بناءً على الخسائر الشهرية.<br>
            <strong>المرجع القانوني:</strong> معايير البنك الدولي والأمم المتحدة.
          </p>
        </div>
        <div class="dynamic-list" id="delayedPayments">
          <div class="item-card">
            <input type="text" placeholder="مثال: تأخر صرف مستحقات شهرية">
            <input type="number" placeholder="المبلغ (ريال)" oninput="calculateSectionTotal('delayedPayments','delayedTotalYER','delayedTotalUSD')">
            <input type="number" placeholder="مدة التأخير (بالأشهر)" oninput="calculateSectionTotal('delayedPayments','delayedTotalYER','delayedTotalUSD')">
            <select class="currency">
              <option value="YER">ريال يمني</option>
              <option value="USD">دولار أمريكي</option>
            </select>
            <button class="remove-btn" onclick="this.parentElement.remove(); calculateSectionTotal('delayedPayments','delayedTotalYER','delayedTotalUSD')">
              <i class="fas fa-times"></i> حذف
            </button>
            <button class="add-btn" onclick="addDamage('delayedPayments')">
              <i class="fas fa-plus"></i> إضافة بند
            </button>
          </div>
        </div>
        <div class="actions">
          <button class="btn" onclick="calculateSectionTotal('delayedPayments','delayedTotalYER','delayedTotalUSD')">
            <i class="fas fa-calculator"></i> حساب خسائر التأخر
          </button>
        </div>
        <div class="total-box">
          <p>النتيجة بالريال: <span id="delayedTotalYER">0</span></p>
          <p>النتيجة بالدولار: <span id="delayedTotalUSD">0</span></p>
        </div>
      </div>
      
      <!-- 7. الأضرار المؤسسية -->
      <div class="section" id="institutionalDamages">
        <div class="section-title" style="color: #F1C40F;">
          <i class="fas fa-building"></i>
          <h2>الأضرار المؤسسية</h2>
        </div>
        <div class="section-intro">
          <p>
            تُحسب الأضرار المؤسسية (مثل فقدان الثقة والسمعة وتدهور العلاقات الإدارية) بناءً على تقييمات داخلية وخارجية. <br>
            <strong>مثال:</strong> إذا انخفضت سمعة الشركة مما أدى إلى فقدان العملاء بنسبة 40%.<br>
            <strong>المرجع القانوني:</strong> معايير الشركات والقوانين التجارية.
          </p>
        </div>
        <div class="dynamic-list" id="institutionalDamages">
          <div class="item-card">
            <input type="text" placeholder="مثال: تدهور العلاقات المؤسسية">
            <input type="number" placeholder="قيمة الضرر (ريال)" oninput="calculateSectionTotal('institutionalDamages','institutionalTotalYER','institutionalTotalUSD')">
            <input type="number" placeholder="مدة الضرر (بالسنوات)" oninput="calculateSectionTotal('institutionalDamages','institutionalTotalYER','institutionalTotalUSD')">
            <select class="currency">
              <option value="YER">ريال يمني</option>
              <option value="USD">دولار أمريكي</option>
            </select>
            <button class="remove-btn" onclick="this.parentElement.remove(); calculateSectionTotal('institutionalDamages','institutionalTotalYER','institutionalTotalUSD')">
              <i class="fas fa-times"></i> حذف
            </button>
            <button class="add-btn" onclick="addDamage('institutionalDamages')">
              <i class="fas fa-plus"></i> إضافة بند
            </button>
          </div>
        </div>
        <div class="actions">
          <button class="btn" onclick="calculateSectionTotal('institutionalDamages','institutionalTotalYER','institutionalTotalUSD')">
            <i class="fas fa-calculator"></i> حساب الأضرار المؤسسية
          </button>
        </div>
        <div class="total-box">
          <p>النتيجة بالريال: <span id="institutionalTotalYER">0</span></p>
          <p>النتيجة بالدولار: <span id="institutionalTotalUSD">0</span></p>
        </div>
      </div>
      
      <!-- 8. خسائر المطالبة بالتعويضات والمتابعة القانونية والإجرائية -->
      <div class="section" id="legalClaimsLosses">
        <div class="section-title" style="color: #F1C40F;">
          <i class="fas fa-gavel"></i>
          <h2>خسائر المطالبة بالتعويضات والمتابعة القانونية</h2>
        </div>
        <div class="section-intro">
          <p>
            تُحسب خسائر المطالبة بالتعويضات والمتابعة القانونية (المصاريف القانونية، تكاليف المحامين، التأخير في الحصول على التعويض) بناءً على تقديرات التكاليف القانونية والإجرائية. <br>
            <strong>مثال:</strong> إذا بلغت المصاريف القانونية 20% من قيمة المطالبة.<br>
            <strong>المرجع القانوني:</strong> القوانين التجارية والمحاكم.
          </p>
        </div>
        <div class="dynamic-list" id="legalClaimsLosses">
          <div class="item-card">
            <input type="text" placeholder="مثال: مصاريف قانونية">
            <input type="number" placeholder="المبلغ (ريال)" oninput="calculateSectionTotal('legalClaimsLosses','legalClaimsTotalYER','legalClaimsTotalUSD')">
            <input type="number" placeholder="مدة العملية (بالأشهر)" oninput="calculateSectionTotal('legalClaimsLosses','legalClaimsTotalYER','legalClaimsTotalUSD')">
            <select class="currency">
              <option value="YER">ريال يمني</option>
              <option value="USD">دولار أمريكي</option>
            </select>
            <button class="remove-btn" onclick="this.parentElement.remove(); calculateSectionTotal('legalClaimsLosses','legalClaimsTotalYER','legalClaimsTotalUSD')">
              <i class="fas fa-times"></i> حذف
            </button>
            <button class="add-btn" onclick="addDamage('legalClaimsLosses')">
              <i class="fas fa-plus"></i> إضافة بند
            </button>
          </div>
        </div>
        <div class="actions">
          <button class="btn" onclick="calculateSectionTotal('legalClaimsLosses','legalClaimsTotalYER','legalClaimsTotalUSD')">
            <i class="fas fa-calculator"></i> حساب خسائر المطالبة القانونية
          </button>
        </div>
        <div class="total-box">
          <p>النتيجة بالريال: <span id="legalClaimsTotalYER">0</span></p>
          <p>النتيجة بالدولار: <span id="legalClaimsTotalUSD">0</span></p>
        </div>
      </div>
      
      <!-- 9. تكاليف إعادة التأهيل والتشغيل والتدريب للكوادر البشرية -->
      <div class="section" id="rehabilitationCosts">
        <div class="section-title" style="color: #F1C40F;">
          <i class="fas fa-chalkboard-teacher"></i>
          <h2>تكاليف إعادة التأهيل والتشغيل والتدريب</h2>
        </div>
        <div class="section-intro">
          <p>
            تُحسب تكاليف إعادة التأهيل والتشغيل والتدريب للكوادر البشرية بناءً على تكلفة البرامج التدريبية ومصاريف إعادة التأهيل. <br>
            <strong>مثال:</strong> إذا بلغت تكلفة التدريب 15% من القيمة الإجمالية للكوادر المتأثرة.<br>
            <strong>المرجع القانوني:</strong> معايير إعادة التأهيل الدولية والقوانين المحلية.
          </p>
        </div>
        <div class="dynamic-list" id="rehabilitationCosts">
          <div class="item-card">
            <input type="text" placeholder="مثال: برنامج تأهيل">
            <input type="number" placeholder="التكلفة (ريال)" oninput="calculateSectionTotal('rehabilitationCosts','rehabTotalYER','rehabTotalUSD')">
            <input type="number" placeholder="مدة البرنامج (بالأشهر)" oninput="calculateSectionTotal('rehabilitationCosts','rehabTotalYER','rehabTotalUSD')">
            <select class="currency">
              <option value="YER">ريال يمني</option>
              <option value="USD">دولار أمريكي</option>
            </select>
            <button class="remove-btn" onclick="this.parentElement.remove(); calculateSectionTotal('rehabilitationCosts','rehabTotalYER','rehabTotalUSD')">
              <i class="fas fa-times"></i> حذف
            </button>
            <button class="add-btn" onclick="addDamage('rehabilitationCosts')">
              <i class="fas fa-plus"></i> إضافة بند
            </button>
          </div>
        </div>
        <div class="actions">
          <button class="btn" onclick="calculateSectionTotal('rehabilitationCosts','rehabTotalYER','rehabTotalUSD')">
            <i class="fas fa-calculator"></i> حساب تكاليف التأهيل والتدريب
          </button>
        </div>
        <div class="total-box">
          <p>النتيجة بالريال: <span id="rehabTotalYER">0</span></p>
          <p>النتيجة بالدولار: <span id="rehabTotalUSD">0</span></p>
        </div>
      </div>
      
      <!-- (ثانياً: الأضرار غير المباشرة) -->
      <!-- 10. تعطيل الإنتاج والتأخير -->
      <div class="section" id="productionDelay">
        <div class="section-title" style="color: #F1C40F;">
          <i class="fas fa-stopwatch"></i>
          <h2>تعطيل الإنتاج والتأخير</h2>
        </div>
        <div class="section-intro">
          <p>
            تُحسب خسائر تعطيل الإنتاج والتأخير بناءً على خسائر الإيرادات المتوقعة وتأثير التأخير على العمليات التشغيلية. <br>
            <strong>مثال:</strong> إذا توقف الإنتاج لمدة 2 أشهر، يُحسب التعويض بناءً على الإيرادات المفقودة.<br>
            <strong>المرجع القانوني:</strong> معايير البنك الدولي.
          </p>
        </div>
        <div class="dynamic-list" id="productionDelay">
          <div class="item-card">
            <input type="text" placeholder="مثال: توقف الإنتاج">
            <input type="number" placeholder="المبلغ (ريال)" oninput="calculateSectionTotal('productionDelay','productionDelayTotalYER','productionDelayTotalUSD')">
            <input type="number" placeholder="مدة التأخير (بالأشهر)" oninput="calculateSectionTotal('productionDelay','productionDelayTotalYER','productionDelayTotalUSD')">
            <select class="currency">
              <option value="YER">ريال يمني</option>
              <option value="USD">دولار أمريكي</option>
            </select>
            <button class="remove-btn" onclick="this.parentElement.remove(); calculateSectionTotal('productionDelay','productionDelayTotalYER','productionDelayTotalUSD')">
              <i class="fas fa-times"></i> حذف
            </button>
            <button class="add-btn" onclick="addDamage('productionDelay')">
              <i class="fas fa-plus"></i> إضافة بند
            </button>
          </div>
        </div>
        <div class="actions">
          <button class="btn" onclick="calculateSectionTotal('productionDelay','productionDelayTotalYER','productionDelayTotalUSD')">
            <i class="fas fa-calculator"></i> حساب تعطيل الإنتاج
          </button>
        </div>
        <div class="total-box">
          <p>النتيجة بالريال: <span id="productionDelayTotalYER">0</span></p>
          <p>النتيجة بالدولار: <span id="productionDelayTotalUSD">0</span></p>
        </div>
      </div>
      
      <!-- 11. خسارة القدرة التنافسية -->
      <div class="section" id="competitiveLoss">
        <div class="section-title" style="color: #F1C40F;">
          <i class="fas fa-chart-line"></i>
          <h2>خسارة القدرة التنافسية</h2>
        </div>
        <div class="section-intro">
          <p>
            تُحسب خسارة القدرة التنافسية (فقدان العملاء والشركاء وتدهور السمعة) بناءً على تقييم الأثر على السوق والإيرادات المستقبلية. <br>
            <strong>مثال:</strong> إذا انخفضت حصة الشركة السوقية بنسبة 30% بسبب فقدان العملاء.<br>
            <strong>المرجع القانوني:</strong> القوانين التجارية.
          </p>
        </div>
        <div class="dynamic-list" id="competitiveLoss">
          <div class="item-card">
            <input type="text" placeholder="مثال: فقدان عملاء رئيسيين">
            <input type="number" placeholder="المبلغ (ريال)" oninput="calculateSectionTotal('competitiveLoss','competitiveLossTotalYER','competitiveLossTotalUSD')">
            <input type="number" placeholder="مدة التأثير (بالسنوات)" oninput="calculateSectionTotal('competitiveLoss','competitiveLossTotalYER','competitiveLossTotalUSD')">
            <select class="currency">
              <option value="YER">ريال يمني</option>
              <option value="USD">دولار أمريكي</option>
            </select>
            <button class="remove-btn" onclick="this.parentElement.remove(); calculateSectionTotal('competitiveLoss','competitiveLossTotalYER','competitiveLossTotalUSD')">
              <i class="fas fa-times"></i> حذف
            </button>
            <button class="add-btn" onclick="addDamage('competitiveLoss')">
              <i class="fas fa-plus"></i> إضافة بند
            </button>
          </div>
        </div>
        <div class="actions">
          <button class="btn" onclick="calculateSectionTotal('competitiveLoss','competitiveLossTotalYER','competitiveLossTotalUSD')">
            <i class="fas fa-calculator"></i> حساب خسارة القدرة التنافسية
          </button>
        </div>
        <div class="total-box">
          <p>النتيجة بالريال: <span id="competitiveLossTotalYER">0</span></p>
          <p>النتيجة بالدولار: <span id="competitiveLossTotalUSD">0</span></p>
        </div>
      </div>
      
      <!-- 12. الأضرار المعنوية والنفسية والصحية -->
      <div class="section" id="intangibleDamages">
        <div class="section-title" style="color: #F1C40F;">
          <i class="fas fa-heartbeat"></i>
          <h2>الأضرار المعنوية والنفسية والصحية</h2>
        </div>
        <div class="section-intro">
          <p>
            تُحسب الأضرار المعنوية والنفسية والصحية (مثل الإجهاد النفسي، فقدان الثقة، وتأثيرها الصحي) بناءً على التقديرات العلاجية والنفسية. <br>
            <strong>مثال:</strong> إذا تسبب فقدان موظف رئيسي في تأثير نفسي على باقي الكوادر بنسبة 25%.<br>
            <strong>المرجع القانوني:</strong> معايير الأمم المتحدة والقوانين المحلية.
          </p>
        </div>
        <div class="dynamic-list" id="intangibleDamages">
          <div class="item-card">
            <input type="text" placeholder="مثال: تأثير نفسي">
            <input type="number" placeholder="قيمة التعويض (ريال)" oninput="calculateSectionTotal('intangibleDamages','intangibleTotalYER','intangibleTotalUSD')">
            <input type="number" placeholder="مدة الضرر (بالسنوات)" oninput="calculateSectionTotal('intangibleDamages','intangibleTotalYER','intangibleTotalUSD')">
            <select class="currency">
              <option value="YER">ريال يمني</option>
              <option value="USD">دولار أمريكي</option>
            </select>
            <button class="remove-btn" onclick="this.parentElement.remove(); calculateSectionTotal('intangibleDamages','intangibleTotalYER','intangibleTotalUSD')">
              <i class="fas fa-times"></i> حذف
            </button>
            <button class="add-btn" onclick="addDamage('intangibleDamages')">
              <i class="fas fa-plus"></i> إضافة بند
            </button>
          </div>
        </div>
        <div class="actions">
          <button class="btn" onclick="calculateSectionTotal('intangibleDamages','intangibleTotalYER','intangibleTotalUSD')">
            <i class="fas fa-calculator"></i> حساب الأضرار المعنوية
          </button>
        </div>
        <div class="total-box">
          <p>النتيجة بالريال: <span id="intangibleTotalYER">0</span></p>
          <p>النتيجة بالدولار: <span id="intangibleTotalUSD">0</span></p>
        </div>
      </div>
      
      <!-- 13. الضرر التكنولوجي أو البرمجي -->
      <div class="section" id="techDamage">
        <div class="section-title" style="color: #F1C40F;">
          <i class="fas fa-laptop-code"></i>
          <h2>الضرر التكنولوجي أو البرمجي</h2>
        </div>
        <div class="section-intro">
          <p>
            تُحسب الأضرار التكنولوجية أو البرمجية (مثل فقدان البيانات أو توقف الأنظمة الإلكترونية) بناءً على تكلفة استعادة الأنظمة وخسارة الإنتاجية. <br>
            <strong>مثال:</strong> إذا توقف نظام المعلومات لمدة 2 شهر، يتم احتساب تكلفة استعادة البيانات والتأثير على الإنتاج.<br>
            <strong>المرجع القانوني:</strong> معايير الشركات والتكنولوجيا.
          </p>
        </div>
        <div class="dynamic-list" id="techDamage">
          <div class="item-card">
            <input type="text" placeholder="مثال: توقف نظام معلومات">
            <input type="number" placeholder="التكلفة (ريال)" oninput="calculateSectionTotal('techDamage','techDamageTotalYER','techDamageTotalUSD')">
            <input type="number" placeholder="مدة التأثير (بالأشهر)" oninput="calculateSectionTotal('techDamage','techDamageTotalYER','techDamageTotalUSD')">
            <select class="currency">
              <option value="YER">ريال يمني</option>
              <option value="USD">دولار أمريكي</option>
            </select>
            <button class="remove-btn" onclick="this.parentElement.remove(); calculateSectionTotal('techDamage','techDamageTotalYER','techDamageTotalUSD')">
              <i class="fas fa-times"></i> حذف
            </button>
            <button class="add-btn" onclick="addDamage('techDamage')">
              <i class="fas fa-plus"></i> إضافة بند
            </button>
          </div>
        </div>
        <div class="actions">
          <button class="btn" onclick="calculateSectionTotal('techDamage','techDamageTotalYER','techDamageTotalUSD')">
            <i class="fas fa-calculator"></i> حساب الضرر التكنولوجي
          </button>
        </div>
        <div class="total-box">
          <p>النتيجة بالريال: <span id="techDamageTotalYER">0</span></p>
          <p>النتيجة بالدولار: <span id="techDamageTotalUSD">0</span></p>
        </div>
      </div>
      
      <!-- 14. خسارة العملاء والشركاء والسمعة -->
      <div class="section" id="reputationLoss">
        <div class="section-title" style="color: #F1C40F;">
          <i class="fas fa-users"></i>
          <h2>خسارة العملاء والسمعة</h2>
        </div>
        <div class="section-intro">
          <p>
            تُحسب خسارة العملاء والشركاء وتدهور السمعة الاعتبارية للشركة بناءً على تقييم تأثيرها على الإيرادات وحصة السوق. <br>
            <strong>مثال:</strong> إذا انخفضت حصة السوق بنسبة 30% بسبب تراجع السمعة.<br>
            <strong>المرجع القانوني:</strong> القوانين التجارية والمعايير الدولية.
          </p>
        </div>
        <div class="dynamic-list" id="reputationLoss">
          <div class="item-card">
            <input type="text" placeholder="مثال: فقدان عملاء رئيسيين">
            <input type="number" placeholder="المبلغ (ريال)" oninput="calculateSectionTotal('reputationLoss','reputationLossTotalYER','reputationLossTotalUSD')">
            <input type="number" placeholder="مدة التأثير (بالسنوات)" oninput="calculateSectionTotal('reputationLoss','reputationLossTotalYER','reputationLossTotalUSD')">
            <select class="currency">
              <option value="YER">ريال يمني</option>
              <option value="USD">دولار أمريكي</option>
            </select>
            <button class="remove-btn" onclick="this.parentElement.remove(); calculateSectionTotal('reputationLoss','reputationLossTotalYER','reputationLossTotalUSD')">
              <i class="fas fa-times"></i> حذف
            </button>
            <button class="add-btn" onclick="addDamage('reputationLoss')">
              <i class="fas fa-plus"></i> إضافة بند
            </button>
          </div>
        </div>
        <div class="actions">
          <button class="btn" onclick="calculateSectionTotal('reputationLoss','reputationLossTotalYER','reputationLossTotalUSD')">
            <i class="fas fa-calculator"></i> حساب خسارة السمعة
          </button>
        </div>
        <div class="total-box">
          <p>النتيجة بالريال: <span id="reputationLossTotalYER">0</span></p>
          <p>النتيجة بالدولار: <span id="reputationLossTotalUSD">0</span></p>
        </div>
      </div>
      
      <!-- 15. خسارة الخطط المستقبلية والاستثمارية -->
      <div class="section" id="futurePlansLoss">
        <div class="section-title" style="color: #F1C40F;">
          <i class="fas fa-chart-line"></i>
          <h2>خسارة الخطط المستقبلية والاستثمارية</h2>
        </div>
        <div class="section-intro">
          <p>
            تُحسب خسارة الخطط المستقبلية والاستثمارية بناءً على التقديرات المالية للمشاريع المستقبلية المتوقعة وفقدان فرص النمو. <br>
            <strong>مثال:</strong> إذا تأثرت خطط استثمارية بنسبة 25%.<br>
            <strong>المرجع القانوني:</strong> معايير تقييم الاستثمارات.
          </p>
        </div>
        <div class="dynamic-list" id="futurePlansLoss">
          <div class="item-card">
            <input type="text" placeholder="مثال: تأجيل مشروع استثماري">
            <input type="number" placeholder="المبلغ (ريال)" oninput="calculateSectionTotal('futurePlansLoss','futurePlansTotalYER','futurePlansTotalUSD')">
            <input type="number" placeholder="مدة التأثير (بالسنوات)" oninput="calculateSectionTotal('futurePlansLoss','futurePlansTotalYER','futurePlansTotalUSD')">
            <select class="currency">
              <option value="YER">ريال يمني</option>
              <option value="USD">دولار أمريكي</option>
            </select>
            <button class="remove-btn" onclick="this.parentElement.remove(); calculateSectionTotal('futurePlansLoss','futurePlansTotalYER','futurePlansTotalUSD')">
              <i class="fas fa-times"></i> حذف
            </button>
            <button class="add-btn" onclick="addFuturePlansLoss()">
              <i class="fas fa-plus"></i> إضافة بند
            </button>
          </div>
        </div>
        <div class="actions">
          <button class="btn" onclick="calculateSectionTotal('futurePlansLoss','futurePlansTotalYER','futurePlansTotalUSD')">
            <i class="fas fa-calculator"></i> حساب خسارة الخطط المستقبلية
          </button>
        </div>
        <div class="total-box">
          <p>النتيجة بالريال: <span id="futurePlansTotalYER">0</span></p>
          <p>النتيجة بالدولار: <span id="futurePlansTotalUSD">0</span></p>
        </div>
      </div>
      
      <!-- (ثالثاً: أضرار أخرى) -->
      <!-- 16. أضرار أخرى -->
      <div class="section" id="otherDamages">
        <div class="section-title" style="color: #F1C40F;">
          <i class="fas fa-question-circle"></i>
          <h2>أضرار أخرى</h2>
        </div>
        <div class="section-intro">
          <p>
            أدخل أي أضرار أخرى غير مصنفة ضمن الأقسام السابقة. يمكن استخدام هذا القسم لإضافة بنود ذات طبيعة خاصة.
          </p>
        </div>
        <div class="dynamic-list" id="otherDamages">
          <div class="item-card">
            <input type="text" placeholder="تفاصيل الضرر">
            <input type="number" placeholder="المبلغ (ريال)" oninput="calculateSectionTotal('otherDamages','otherTotalYER','otherTotalUSD')">
            <input type="number" placeholder="مدة الضرر (بالسنوات)" oninput="calculateSectionTotal('otherDamages','otherTotalYER','otherTotalUSD')">
            <select class="currency">
              <option value="YER">ريال يمني</option>
              <option value="USD">دولار أمريكي</option>
            </select>
            <button class="remove-btn" onclick="this.parentElement.remove(); calculateSectionTotal('otherDamages','otherTotalYER','otherTotalUSD')">
              <i class="fas fa-times"></i> حذف
            </button>
            <button class="add-btn" onclick="addDamage('otherDamages')">
              <i class="fas fa-plus"></i> إضافة بند
            </button>
          </div>
        </div>
        <div class="actions">
          <button class="btn" onclick="calculateSectionTotal('otherDamages','otherTotalYER','otherTotalUSD')">
            <i class="fas fa-calculator"></i> حساب الأضرار الأخرى
          </button>
        </div>
        <div class="total-box">
          <p>النتيجة بالريال: <span id="otherTotalYER">0</span></p>
          <p>النتيجة بالدولار: <span id="otherTotalUSD">0</span></p>
        </div>
      </div>
      
    </div> <!-- نهاية قسم حساب الأضرار وأنواعها -->
    
    
<!-- الخلاصة النهائية 

<script>
  function calculateFinalSummary() {
    let totalYER = 0, totalUSD = 0;
    const sections = [
      'fixedAssetsTotal', 'inventoryDamageTotal', 'humanTotalYER', 'financialDirectTotal',
      'operationalTotalYER', 'delayedTotalYER', 'institutionalTotalYER', 'legalClaimsTotalYER',
      'rehabTotalYER', 'productionDelayTotalYER', 'competitiveLossTotalYER', 'intangibleTotalYER',
      'techDamageTotalYER', 'reputationLossTotalYER', 'futurePlansTotalYER', 'otherTotalYER'
    ];
    const sectionsUSD = [
      'fixedAssetsTotalUSD', 'inventoryDamageTotalUSD', 'humanTotalUSD', 'financialDirectTotalUSD',
      'operationalTotalUSD', 'delayedTotalUSD', 'institutionalTotalUSD', 'legalClaimsTotalUSD',
      'rehabTotalUSD', 'productionDelayTotalUSD', 'competitiveLossTotalUSD', 'intangibleTotalUSD',
      'techDamageTotalUSD', 'reputationLossTotalUSD', 'futurePlansTotalUSD', 'otherTotalUSD'
    ];

    sections.forEach(id => {
      let value = parseFloat(document.getElementById(id).innerText) || 0;
      totalYER += value;
    });
    sectionsUSD.forEach(id => {
      let value = parseFloat(document.getElementById(id).innerText) || 0;
      totalUSD += value;
    });

    document.getElementById('totalSumYER').innerText = totalYER.toFixed(2);
    document.getElementById('totalSumUSD').innerText = totalUSD.toFixed(2);
  }
</script>

<!-- قسم إدارة ملفات المطالبات -->
    <div class="extra-section" id="claimsManagement">
      <div class="section-title" style="color: #F1C40F;">
        <i class="fas fa-folder-open"></i>
        <h2>إدارة ملفات المطالبات</h2>
      </div>
      <div class="section-intro">
        <p>
          يتيح لك هذا القسم إدارة ملفات المطالبات الخاصة بك:
        </p>
        <ol>
          <li>تخزين كافة ملفات المطالبات التي تم إعدادها باستخدام النظام.</li>
          <li>إمكانية تصدير الملفات بصيغة PDF أو مشاركتها إلكترونيًا.</li>
          <li>متابعة حالة المطالبة وتحديث بيانات الملف وإرفاق الوثائق اللازمة.</li>
          <li>تصدير تقارير مفصلة عن المطالبات للمتابعة مع الجهات المختصة.</li>
        </ol>
      </div>
    </div>
    
    <!-- قسم الوثائق والمستندات والدلائل -->
    <div class="extra-section documents-section" id="documentsSection">
      <div class="section-title" style="color: #F1C40F;">
        <i class="fas fa-file-alt"></i>
        <h2>الوثائق والمستندات والدلائل</h2>
      </div>
      <div class="section-intro">
        <p>
          يُمكن للمقاول إضافة كافة الوثائق والمستندات التي تُثبت الأضرار والخسائر، مثل:
        </p>
        <ul>
          <li>صور وفيديوهات توثيقية (مثال: صور المباني المتضررة).</li>
          <li>تقارير فنية من مهندسين متخصصين.</li>
          <li>عقود واتفاقيات سابقة.</li>
          <li>فواتير ومستندات تثبت التكاليف.</li>
          <li>أدلة أخرى تدعم مطالبة التعويض.</li>
        </ul>
        <p>
          بعد رفع الملفات، يرجى الضغط على زر "موافقة على الوثائق" لتأكيد صحة الملفات المُرفقة.
        </p>
      </div>
      <div class="file-upload">
        <input type="file" id="documentsInput" multiple>
        <label for="documentsInput"><i class="fas fa-upload"></i> رفع الملفات</label>
      </div>
      <button class="approve-btn" onclick="approveDocuments()">
        <i class="fas fa-check"></i> موافقة على الوثائق
      </button>
    </div>
    
    <!-- قسم الخلاصة النهائية -->
    
    <div class="container">
        <div class="section" id="finalSummary">
            <div class="section-title">
                <i class="fas fa-file-invoice-dollar"></i>
                <h2>الخلاصة النهائية</h2>
            </div>
            <div class="section-intro">
                <p>يوضح الجدول التالي إجمالي الأضرار المحسوبة لكل قسم.</p>
            </div>
            <table id="summaryTable">
                <thead>
                    <tr>
                        <th class="column-1">رقم البند</th>
                        <th class="column-2">الوصف</th>
                        <th class="column-3">المبلغ بالريال </th>
                        <th class="column-4">المبلغ بالدولار</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>1</td>
                        <td>أضرار الأصول الثابتة</td>
                        <td id="fixedAssetsTotal">0</td>
                        <td id="fixedAssetsTotalUSD">0</td>
                    </tr>
                    <tr>
                        <td>2</td>
                        <td>أضرار المخزون</td>
                        <td id="inventoryDamageTotal">0</td>
                        <td id="inventoryDamageTotalUSD">0</td>
                    </tr>
                    <tr>
                        <td>3</td>
                        <td>الكوادر البشرية</td>
                        <td id="humanTotalYER">0</td>
                        <td id="humanTotalUSD">0</td>
                    </tr>
                    <tr>
                        <td>4</td>
                        <td>الأضرار المالية</td>
                        <td id="financialDirectTotal">0</td>
                        <td id="financialDirectTotalUSD">0</td>
                    </tr>
                    <tr>
                        <td>5</td>
                        <td>الخسائر التشغيلية</td>
                        <td id="operationalTotalYER">0</td>
                        <td id="operationalTotalUSD">0</td>
                    </tr>
                    <tr>
                        <td>6</td>
                        <td>خسائر التأخر</td>
                        <td id="delayedTotalYER">0</td>
                        <td id="delayedTotalUSD">0</td>
                    </tr>
                    <tr>
                        <td>7</td>
                        <td>الأضرار المؤسسية</td>
                        <td id="institutionalTotalYER">0</td>
                        <td id="institutionalTotalUSD">0</td>
                    </tr>
                    <tr>
                        <td>8</td>
                        <td>خسائر المطالبة القانونية</td>
                        <td id="legalClaimsTotalYER">0</td>
                        <td id="legalClaimsTotalUSD">0</td>
                    </tr>
                    <tr>
                        <td>9</td>
                        <td>تكاليف التأهيل</td>
                        <td id="rehabTotalYER">0</td>
                        <td id="rehabTotalUSD">0</td>
                    </tr>
                    <tr>
                        <td>10</td>
                        <td>تعطيل الإنتاج</td>
                        <td id="productionDelayTotalYER">0</td>
                        <td id="productionDelayTotalUSD">0</td>
                    </tr>
                    <tr>
                        <td>11</td>
                        <td>خسارة القدرة التنافسية</td>
                        <td id="competitiveLossTotalYER">0</td>
                        <td id="competitiveLossTotalUSD">0</td>
                    </tr>
                    <tr>
                        <td>12</td>
                        <td>الأضرار المعنوية والصحية</td>
                        <td id="intangibleTotalYER">0</td>
                        <td id="intangibleTotalUSD">0</td>
                    </tr>
                    <tr>
                        <td>13</td>
                        <td>الضرر التكنولوجي</td>
                        <td id="techDamageTotalYER">0</td>
                        <td id="techDamageTotalUSD">0</td>
                    </tr>
                    <tr>
                        <td>14</td>
                        <td>خسارة العملاء والسمعة</td>
                        <td id="reputationLossTotalYER">0</td>
                        <td id="reputationLossTotalUSD">0</td>
                    </tr>
                    <tr>
                        <td>15</td>
                        <td>خسارة الخطط المستقبلية</td>
                        <td id="futurePlansTotalYER">0</td>
                        <td id="futurePlansTotalUSD">0</td>
                    </tr>
                    <tr>
                        <td>16</td>
                        <td>الأضرار الأخرى</td>
                        <td id="otherTotalYER">0</td>
                        <td id="otherTotalUSD">0</td>
                    </tr>
                    <tr class="total-row">
                        <td></td>
                        <td>الإجمالي الكلي</td>
                        <td id="totalSumYER">0</td>
                        <td id="totalSumUSD">0</td>
                    </tr>
                </tbody>
            </table>
            <div class="actions">
                <button class="btn-calculate" onclick="calculateFinalSummary()">
                    <i class="fas fa-calculator"></i> حساب الإجمالي
                </button>
            </div>
        </div>

    </div>
    
    <!-- قسم الدليل الإرشادي الشامل لنيل التعويضات -->
    <div class="extra-section" id="guidelines">
      <div class="section-title" style="color: #F1C40F;">
        <i class="fas fa-chalkboard-teacher"></i>
        <h2>الدليل الإرشادي للمطالبة بالتعويضات</h2>
      </div>
      <div class="section-intro">
        <h3>المقدمة</h3>
        <p>
          يهدف هذا الدليل إلى توضيح الخطوات والإجراءات التي يجب أن يتبعها المقاولون المتضررون نتيجة الحرب للحصول على تعويض عادل. يعتمد الدليل على المعايير الدولية والممارسات الفضلى في توثيق المطالبات والمرافعة القانونية لضمان حقوق المتضررين.
        </p>
        <hr style="border: none; border-top: 1px dashed var(--accent-color); margin: 1rem 0;">
        <h3>المرحلة الأولى: التوثيق الدقيق للأضرار والخسائر</h3>
        <p><strong>الخطوة 1: جمع الأدلة المادية</strong></p>
        <ul>
          <li>التقاط صور وفيديوهات واضحة لجميع الأضرار والخسائر.</li>
          <li>تصوير كل زاوية للمنشآت والمعدات المتضررة.</li>
          <li>استخدام تقنية GPS لتحديد الموقع الدقيق.</li>
        </ul>
        <p><strong>الخطوة 2: إعداد قائمة مفصلة بالأضرار</strong></p>
        <ul>
          <li>تحديد نوع الضرر (مدني/عسكري، مباشر/غير مباشر).</li>
          <li>إدراج تفاصيل العناصر المتضررة ووصفها بدقة.</li>
          <li>تحديد تاريخ الضرر لتقييم مدة التعطل.</li>
        </ul>
        <p><strong>الخطوة 3: توثيق الأضرار بالوثائق الرسمية</strong></p>
        <ul>
          <li>جمع العقود الرسمية والوثائق المالية قبل الضرر.</li>
          <li>الحصول على إفادات من شهود العيان والعاملين.</li>
          <li>تسجيل محاضر رسمية لدى الجهات المختصة.</li>
        </ul>
        <hr style="border: none; border-top: 1px dashed var(--accent-color); margin: 1rem 0;">
        <h3>المرحلة الثانية: حساب الخسائر والتعويضات المطلوبة</h3>
        <p><strong>الخطوة 4: تصنيف الخسائر</strong></p>
        <ul>
          <li>خسائر مباشرة: تشمل أضرار الأصول الثابتة، المخزون، الكوادر البشرية، الأضرار المالية، التشغيلية، خسائر التأخر، الأضرار المؤسسية، خسائر المطالبة القانونية، وتكاليف التأهيل.</li>
          <li>خسائر غير مباشرة: تشمل تعطيل الإنتاج، خسارة القدرة التنافسية، الأضرار المعنوية والنفسية والصحية، الضرر التكنولوجي، خسارة العملاء والسمعة، وخسارة الخطط المستقبلية.</li>
        </ul>
        <p><strong>الخطوة 5: استخدام معايير التقييم الدولية</strong></p>
        <ul>
          <li>تقييم تكلفة الإصلاح والاستبدال بناءً على الأسعار الحالية.</li>
          <li>تقدير تكلفة الفرصة البديلة والإيرادات المفقودة.</li>
          <li>تطبيق معايير التقييم القانونية والمالية.</li>
        </ul>
        <p><strong>الخطوة 6: توثيق الحسابات المالية</strong></p>
        <ul>
          <li>استخدام جداول Excel دقيقة لحساب الخسائر.</li>
          <li>إعداد تقارير مالية موقعة من محاسب قانوني معتمد.</li>
        </ul>
        <hr style="border: none; border-top: 1px dashed var(--accent-color); margin: 1rem 0;">
        <h3>المرحلة الثالثة: التقديم للجهات المختصة</h3>
        <p><strong>الخطوة 7: تحديد الجهة المختصة بتقديم المطالبة</strong></p>
        <ul>
          <li>الحكومة المحلية أو الوزارات المختصة.</li>
          <li>الهيئات القضائية والمحاكم الوطنية.</li>
          <li>المنظمات الدولية مثل الأمم المتحدة والبنك الدولي.</li>
        </ul>
        <p><strong>الخطوة 8: إعداد ملف التعويضات</strong></p>
        <ul>
          <li>خطاب رسمي يوضح المطالبة بالتعويض.</li>
          <li>قائمة بالأضرار والخسائر موثقة بالأدلة.</li>
          <li>التقارير المالية لتقدير حجم التعويضات المطلوبة.</li>
          <li>نسخ من العقود والمستندات القانونية.</li>
          <li>شهادات من الجهات المختصة والشهود.</li>
        </ul>
        <hr style="border: none; border-top: 1px dashed var(--accent-color); margin: 1rem 0;">
        <h3>المرحلة الرابعة: المتابعة القانونية والتفاوض</h3>
        <p><strong>الخطوة 9: تقديم الدعوى القانونية</strong></p>
        <ul>
          <li>توكيل محامٍ متخصص في قضايا التعويضات.</li>
          <li>رفع الدعوى أمام المحاكم المختصة في حالة رفض التعويض.</li>
          <li>متابعة الإجراءات القانونية والتواصل مع الجهات المعنية.</li>
        </ul>
        <p><strong>الخطوة 10: التفاوض وتسوية النزاعات</strong></p>
        <ul>
          <li>استخدام الأدلة الدامغة أثناء التفاوض.</li>
          <li>البحث عن حلول ودية أو اللجوء إلى التحكيم.</li>
          <li>استخدام وسائل الإعلام والضغط المجتمعي لدعم المطالبة.</li>
        </ul>
      </div>
    </div>
    
    <!-- قسم الأسئلة الشائعة (FAQ) -->
    
<!-- الدليل المرجعي القانوني لتعويض الأعيان المدنية وشركات المقاولات المتضررة -->
<div class="extra-section" id="legalReference">
  <div class="section-title" style="color: #F1C40F;">
    <i class="fas fa-balance-scale"></i>
    <h2>الدليل القانوني - المراجع القانونية للمطالبة بالتعويضات</h2>
  </div>
  <div class="section-intro">
    <h3>القوانين والتشريعات الدولية ذات الصلة</h3>

    <h4>1. اتفاقيات جنيف لعام 1949 والبروتوكولات الإضافية</h4>
    <ul>
      <li><strong>اتفاقية جنيف الرابعة (1949):</strong> تحظر استهداف الأعيان المدنية وتضمن التعويضات عن الأضرار الناجمة عن النزاعات المسلحة.</li>
      <li><strong>البروتوكول الإضافي الأول (1977):</strong> يؤكد على حماية الممتلكات المدنية وضمان التعويضات في حالات الضرر.</li>
    </ul>

    <h4>2. النظام الأساسي للمحكمة الجنائية الدولية (اتفاقية روما 1998)</h4>
    <ul>
      <li><strong>المادة 8:</strong> تعتبر استهداف المنشآت المدنية جريمة حرب تستوجب المساءلة والتعويض.</li>
      <li><strong>المادة 75:</strong> تنص على حق الضحايا في التعويض العادل وإعادة التأهيل.</li>
    </ul>

    <h4>3. قرارات الأمم المتحدة ذات الصلة</h4>
    <ul>
      <li><strong>قرار مجلس الأمن رقم 687 (1991):</strong> فرض تعويضات على العراق عن الأضرار التي لحقت بالكويت، مما يشكل سابقة قانونية لتعويضات الحروب.</li>
      <li><strong>قرار مجلس الأمن رقم 2175 (2014):</strong> يدعو إلى حماية الأعيان المدنية والبنى التحتية من آثار النزاعات المسلحة.</li>
    </ul>

    <h4>4. مبادئ الأمم المتحدة بشأن التعويضات وإعادة التأهيل للضحايا</h4>
    <p>تؤكد على حق الضحايا في الحصول على تعويضات مادية ومعنوية تشمل إعادة الإعمار والاسترداد المالي.</p>

    <h4>5. القوانين الوطنية الخاصة بالتعويضات (في حالة توفرها)</h4>
    <p>أي قوانين محلية تنظم تعويضات الأضرار في اليمن، مثل القوانين المدنية والتجارية ذات الصلة بالتعويضات عن الأضرار والخسائر.</p>
  </div>
</div>

<!-- الختام والتوصيات -->
<div class="extra-section" id="conclusion">
  <div class="section-title" style="color: #F1C40F;">
    <i class="fas fa-check-circle"></i>
    <h2>الختام والتوصيات</h2>
  </div>
  <div class="section-intro">
    <ul>
      <li>على المقاولين توثيق كل الأضرار فور حدوثها لضمان استحقاق التعويض.</li>
      <li>يجب تقديم المطالبات وفقًا للمعايير القانونية الدولية والمحلية.</li>
      <li>ينصح بالاستعانة بمحامين وخبراء ماليين لرفع الدعاوى بفعالية.</li>
      <li>يمكن اللجوء إلى التحكيم الدولي في حال تعذر الحصول على تعويض محليًا.</li>
    </ul>
    <p><strong>هذا الدليل يقدم خارطة طريق شاملة تساعد المقاولين اليمنيين في تقديم مطالبات تعويض ناجحة وفق الأطر القانونية الدولية.</strong></p>
  </div>
</div>
<div class="extra-section faq-section" id="faqSection">
      <h2>الأسئلة الشائعة</h2>
      <div class="faq-item">
        <h3 onclick="toggleFaq(this)">1. ما هي الخطوات الأساسية لتوثيق الأضرار؟</h3>
        <div class="faq-answer">
          <p>يجب التقاط صور وفيديوهات واضحة، استخدام تقنية GPS، وإعداد قائمة مفصلة بالأضرار مع توثيقها بالعقود والفواتير والتقارير الرسمية.</p>
        </div>
      </div>
      <div class="faq-item">
        <h3 onclick="toggleFaq(this)">2. كيف يتم حساب التعويضات؟</h3>
        <div class="faq-answer">
          <p>يتم حساب التعويضات بناءً على تكلفة الإصلاح والاستبدال ونسبة الخسارة وفقًا للمعايير الدولية مثل IVSC وRICS.</p>
        </div>
      </div>
      <div class="faq-item">
        <h3 onclick="toggleFaq(this)">3. ما هي الوثائق المطلوبة لدعم المطالبة؟</h3>
        <div class="faq-answer">
          <p>تشمل الوثائق المطلوبة العقود، الفواتير، التقارير الرسمية، صور وفيديوهات للموقع، وإفادات الشهود.</p>
        </div>
      </div>
      <div class="faq-item">
        <h3 onclick="toggleFaq(this)">4. كيف يمكن إدارة ملفات المطالبات في النظام؟</h3>
        <div class="faq-answer">
          <p>يوفر النظام قسم إدارة ملفات المطالبات لتخزين الملفات، تصديرها بصيغة PDF، ومتابعة حالة المطالبة مع تحديث البيانات وإرفاق الوثائق.</p>
        </div>
      </div>
      <div class="faq-item">
        <h3 onclick="toggleFaq(this)">5. هل يمكن رفع ملفات متعددة لدعم المطالبة؟</h3>
        <div class="faq-answer">
          <p>نعم، يمكن رفع عدد غير محدود من الملفات في قسم الوثائق والمستندات والدلائل مع إمكانية الموافقة عليها.</p>
        </div>
      </div>
      <div class="faq-item">
        <h3 onclick="toggleFaq(this)">6. كيف يتم حساب الإجمالي النهائي للتعويضات؟</h3>
        <div class="faq-answer">
          <p>يتم جمع النتائج الفرعية من كافة الأقسام وعرض الإجمالي في قسم الخلاصة النهائية باستخدام زر الحساب.</p>
        </div>
      </div>
      <div class="faq-item">
        <h3 onclick="toggleFaq(this)">7. ما مدى دقة النظام في حساب التعويضات؟</h3>
        <div class="faq-answer">
          <p>يعتمد النظام على معايير دولية وأفضل الممارسات العالمية مع استخدام دوال حسابية دقيقة لضمان النتائج الدقيقة.</p>
        </div>
      </div>
      <div class="faq-item">
        <h3 onclick="toggleFaq(this)">8. هل يمكن تعديل البيانات بعد إدخالها؟</h3>
        <div class="faq-answer">
          <p>نعم، يمكن تعديل البيانات في أي وقت قبل تقديم ملف المطالبة.</p>
        </div>
      </div>
      <div class="faq-item">
        <h3 onclick="toggleFaq(this)">9. ما الإجراءات المتبعة في حال رفض المطالبة؟</h3>
        <div class="faq-answer">
          <p>يمكنك توكيل محامٍ متخصص ورفع دعوى قانونية أمام الجهات المختصة وفق الإجراءات القانونية.</p>
        </div>
      </div>
      <div class="faq-item">
        <h3 onclick="toggleFaq(this)">10. هل يوجد دليل إرشادي مفصل في النظام؟</h3>
        <div class="faq-answer">
          <p>نعم، يوجد قسم "الدليل الإرشادي" يحتوي على كافة الخطوات والإجراءات للحصول على التعويض.</p>
        </div>
      </div>
      <div class="faq-item">
        <h3 onclick="toggleFaq(this)">11. هل يدعم النظام تصدير ملفات المطالبات؟</h3>
        <div class="faq-answer">
          <p>نعم، يمكن تصدير الملفات بصيغة PDF من خلال قسم إدارة ملفات المطالبات.</p>
        </div>
      </div>
      <div class="faq-item">
        <h3 onclick="toggleFaq(this)">12. كيف يمكن متابعة حالة المطالبة؟</h3>
        <div class="faq-answer">
          <p>يوفر النظام خاصية متابعة حالة المطالبة عبر تحديث البيانات وإرفاق الوثائق والتواصل مع الجهات المختصة.</p>
        </div>
      </div>
      <div class="faq-item">
        <h3 onclick="toggleFaq(this)">13. هل يمكن مشاركة ملف المطالبة إلكترونيًا؟</h3>
        <div class="faq-answer">
          <p>نعم، يحتوي النظام على خاصية مشاركة الملف إلكترونيًا عبر وسائل التواصل والتصدير إلى PDF.</p>
        </div>
      </div>
      <div class="faq-item">
        <h3 onclick="toggleFaq(this)">14. كيف يمكن الحصول على دعم فني للنظام؟</h3>
        <div class="faq-answer">
          <p>يمكنك التواصل مع فريق الدعم الفني عبر بيانات الاتصال المتوفرة في الفوتر.</p>
        </div>
      </div>
      <div class="faq-item">
        <h3 onclick="toggleFaq(this)">15. هل يتم تحديث النظام وفقًا للمعايير الدولية؟</h3>
        <div class="faq-answer">
          <p>بالتأكيد، يتم تحديث النظام بانتظام ليتوافق مع أحدث المعايير الدولية وأفضل الممارسات العالمية.</p>
        </div>
      </div>
    </div>
    
    <!-- قسم الإقرار والموافقة -->
    <div class="section">
      <div class="section-title" style="color: #F1C40F;">
        <i class="fas fa-check-circle"></i>
        <h2>الإقرار والموافقة</h2>
      </div>
      <div class="section-intro">
        <p>
          بموجب هذا، أقر بصحة البيانات والمعلومات المدخلة وأوافق على استخدامها لحساب الأضرار والخسائر، وأتعهد بتحمل المسؤولية القانونية عن دقتها.
        </p>
        <div class="input-group">
          <label style="color: #F1C40F;">
            <input type="checkbox" id="agreement" required> أوافق على صحة البيانات المقدمة.
          </label>
        </div>
      </div>
    </div>
    
    <!-- قسم أزرار الإجراءات -->
    <div class="actions">
      <button class="btn" onclick="printForm()">
        <i class="fas fa-print"></i> طباعة النموذج
      </button>
      <button class="btn" onclick="exportToPDF()">
        <i class="fas fa-file-pdf"></i> تصدير إلى PDF
      </button>
      <button class="btn" onclick="shareForm()">
        <i class="fas fa-share"></i> مشاركة النموذج
      </button>
      <button class="btn" onclick="sendEmail()">
        <i class="fas fa-envelope"></i> إرسال النموذج للإيميل
      </button>
    </div>
    
<div class="section">
    <button class="btn" onclick="submitClaimFile()">
        <i class="fas fa-paper-plane"></i> إرسال ملف المطالبة
    </button>
</div>
<script>
    function submitClaimFile() {
        let formData = new FormData();
        formData.append("fileNumber", document.getElementById("fileNumber").innerText);
        formData.append("companyName", document.getElementById("companyName").value);
        formData.append("contractorName", document.getElementById("contractorName").value);

        fetch("https://your-email-api-endpoint", {
            method: "POST",
            body: formData
        }).then(response => {
            if (response.ok) {
                alert("تم إرسال ملف المطالبة بنجاح!");
            } else {
                alert("حدث خطأ أثناء إرسال الملف.");
            }
        });
    }
</script>

<div class="section">
    <input type="text" id="claimFileNumber" placeholder="أدخل رقم الملف">
    <button class="btn" onclick="manageClaimFile()">
        <i class="fas fa-folder-open"></i> إدارة ملف المطالبة
    </button>
</div>
<script>
    function manageClaimFile() {
        let fileNumber = document.getElementById("claimFileNumber").value;
        if (fileNumber) {
            window.open("https://kimo23576.github.io/GUYC3/?fileNumber=" + fileNumber, "_blank");
        } else {
            alert("يرجى إدخال رقم الملف!");
        }
    }
</script>

<div class="floating-button" onclick="trackClaimFile()">
    <i class="fas fa-search"></i> متابعة الملف
</div>
<style>
    .floating-button {
        position: fixed;
        bottom: 20px;
        right: 20px;
        background: #F1C40F;
        color: #1B2631;
        padding: 15px;
        border-radius: 50px;
        cursor: pointer;
        box-shadow: 0px 4px 10px rgba(0,0,0,0.2);
        font-weight: bold;
    }
</style>
<script>
    function trackClaimFile() {
        let fileNumber = prompt("أدخل رقم الملف لمتابعته:");
        if (fileNumber) {
            window.open("https://kimo23576.github.io/GUYC3/?fileNumber=" + fileNumber, "_blank");
        }
    }
</script>
    <!-- الفوتر -->
    <div class="footer">
      <div class="contact-box">
        <i class="fas fa-phone"></i>
        <span>01-450553</span>
      </div>
      <div class="contact-box">
        <i class="fas fa-envelope"></i>
        <span>info@guyc-ye.com</span>
      </div>
      <div class="contact-box">
        <i class="fas fa-globe"></i>
        <span><a href="https://guyc-ye.com/" target="_blank">guyc-ye.com</a></span>
      </div>
      <p>© 2025 الاتحاد العام للمقاولين اليمنيين. جميع الحقوق محفوظة.</p>
    </div>
  
  
  <script>
    'use strict';
    const { jsPDF } = window.jspdf;
    
    // توليد رقم ملف فريد وتحديث التاريخ
    function generateFileNumber() {
      const timestamp = Date.now().toString().slice(-6);
      const randomNum = Math.floor(1000 + Math.random() * 9000);
      return `GUYC-${timestamp}-${randomNum}`;
    }
    function updateDateTime() {
      const options = { 
        weekday: 'long', 
        year: 'numeric', 
        month: 'long', 
        day: 'numeric',
        hour: 'numeric',
        minute: 'numeric',
        hour12: true 
      };
      document.getElementById('currentDate').textContent = new Date().toLocaleDateString('ar-YE', options);
      document.getElementById('fileNumber').textContent = `رقم الملف: ${generateFileNumber()}`;
    }
    
    // دالة لإضافة بند جديد في قسم ديناميكي
    function addDamage(sectionId) {
      const templates = {
        fixedAssets: `
          <input type="text" placeholder="مثال: مبنى رئيسي">
          <input type="number" placeholder="قيمة الضرر (ريال)" oninput="calculateSectionTotal('fixedAssets','fixedAssetsTotal','fixedAssetsTotalUSD')">
          <select class="severity" oninput="calculateSectionTotal('fixedAssets','fixedAssetsTotal','fixedAssetsTotalUSD')">
            <option value="1">100%</option>
            <option value="0.8">80%</option>
            <option value="0.5">50%</option>
          </select>
          <input type="number" placeholder="مدة الضرر (بالسنوات)" oninput="calculateSectionTotal('fixedAssets','fixedAssetsTotal','fixedAssetsTotalUSD')">
          <select class="currency">
            <option value="YER">ريال يمني</option>
            <option value="USD">دولار أمريكي</option>
          </select>
        `,
        inventoryDamage: `
          <input type="text" placeholder="مثال: مواد خام">
          <input type="number" placeholder="قيمة الضرر (ريال)" oninput="calculateSectionTotal('inventoryDamage','inventoryDamageTotal','inventoryDamageTotalUSD')">
          <select class="severity" oninput="calculateSectionTotal('inventoryDamage','inventoryDamageTotal','inventoryDamageTotalUSD')">
            <option value="1">100%</option>
            <option value="0.6">60%</option>
          </select>
          <input type="number" placeholder="مدة الضرر (بالأشهر)" oninput="calculateSectionTotal('inventoryDamage','inventoryDamageTotal','inventoryDamageTotalUSD')">
          <select class="currency">
            <option value="YER">ريال يمني</option>
            <option value="USD">دولار أمريكي</option>
          </select>
        `,
        humanLosses: `
          <input type="text" placeholder="مثال: موظف رئيسي">
          <input type="number" placeholder="قيمة التعويض (ريال)" oninput="calculateSectionTotal('humanLosses','humanTotalYER','humanTotalUSD')">
          <input type="number" placeholder="مدة الضرر (بالسنوات)" oninput="calculateSectionTotal('humanLosses','humanTotalYER','humanTotalUSD')">
          <select class="currency">
            <option value="YER">ريال يمني</option>
            <option value="USD">دولار أمريكي</option>
          </select>
        `,
        financialDirect: `
          <input type="text" placeholder="مثال: خسارة إيرادات شهرية">
          <input type="number" placeholder="مقدار الخسارة (ريال)" oninput="calculateSectionTotal('financialDirect','financialDirectTotal','financialDirectTotalUSD')">
          <input type="number" placeholder="مدة الضرر (بالأشهر)" oninput="calculateSectionTotal('financialDirect','financialDirectTotal','financialDirectTotalUSD')">
          <select class="currency">
            <option value="YER">ريال يمني</option>
            <option value="USD">دولار أمريكي</option>
          </select>
        `,
        operationalLosses: `
          <input type="text" placeholder="مثال: توقف الإنتاج">
          <input type="number" placeholder="المبلغ (ريال)" oninput="calculateSectionTotal('operationalLosses','operationalTotalYER','operationalTotalUSD')">
          <input type="number" placeholder="مدة التأخير (بالأشهر)" oninput="calculateSectionTotal('operationalLosses','operationalTotalYER','operationalTotalUSD')">
          <select class="currency">
            <option value="YER">ريال يمني</option>
            <option value="USD">دولار أمريكي</option>
          </select>
        `,
        delayedPayments: `
          <input type="text" placeholder="مثال: تأخر صرف مستحقات شهرية">
          <input type="number" placeholder="المبلغ (ريال)" oninput="calculateSectionTotal('delayedPayments','delayedTotalYER','delayedTotalUSD')">
          <input type="number" placeholder="مدة التأخير (بالأشهر)" oninput="calculateSectionTotal('delayedPayments','delayedTotalYER','delayedTotalUSD')">
          <select class="currency">
            <option value="YER">ريال يمني</option>
            <option value="USD">دولار أمريكي</option>
          </select>
        `,
        institutionalDamages: `
          <input type="text" placeholder="مثال: تدهور العلاقات المؤسسية">
          <input type="number" placeholder="قيمة الضرر (ريال)" oninput="calculateSectionTotal('institutionalDamages','institutionalTotalYER','institutionalTotalUSD')">
          <input type="number" placeholder="مدة الضرر (بالسنوات)" oninput="calculateSectionTotal('institutionalDamages','institutionalTotalYER','institutionalTotalUSD')">
          <select class="currency">
            <option value="YER">ريال يمني</option>
            <option value="USD">دولار أمريكي</option>
          </select>
        `,
        legalClaimsLosses: `
          <input type="text" placeholder="مثال: مصاريف قانونية">
          <input type="number" placeholder="المبلغ (ريال)" oninput="calculateSectionTotal('legalClaimsLosses','legalClaimsTotalYER','legalClaimsTotalUSD')">
          <input type="number" placeholder="مدة العملية (بالأشهر)" oninput="calculateSectionTotal('legalClaimsLosses','legalClaimsTotalYER','legalClaimsTotalUSD')">
          <select class="currency">
            <option value="YER">ريال يمني</option>
            <option value="USD">دولار أمريكي</option>
          </select>
        `,
        rehabilitationCosts: `
          <input type="text" placeholder="مثال: برنامج تأهيل">
          <input type="number" placeholder="التكلفة (ريال)" oninput="calculateSectionTotal('rehabilitationCosts','rehabTotalYER','rehabTotalUSD')">
          <input type="number" placeholder="مدة البرنامج (بالأشهر)" oninput="calculateSectionTotal('rehabilitationCosts','rehabTotalYER','rehabTotalUSD')">
          <select class="currency">
            <option value="YER">ريال يمني</option>
            <option value="USD">دولار أمريكي</option>
          </select>
        `,
        productionDelay: `
          <input type="text" placeholder="مثال: توقف الإنتاج">
          <input type="number" placeholder="المبلغ (ريال)" oninput="calculateSectionTotal('productionDelay','productionDelayTotalYER','productionDelayTotalUSD')">
          <input type="number" placeholder="مدة التأخير (بالأشهر)" oninput="calculateSectionTotal('productionDelay','productionDelayTotalYER','productionDelayTotalUSD')">
          <select class="currency">
            <option value="YER">ريال يمني</option>
            <option value="USD">دولار أمريكي</option>
          </select>
        `,
        competitiveLoss: `
          <input type="text" placeholder="مثال: فقدان عملاء رئيسيين">
          <input type="number" placeholder="المبلغ (ريال)" oninput="calculateSectionTotal('competitiveLoss','competitiveLossTotalYER','competitiveLossTotalUSD')">
          <input type="number" placeholder="مدة التأثير (بالسنوات)" oninput="calculateSectionTotal('competitiveLoss','competitiveLossTotalYER','competitiveLossTotalUSD')">
          <select class="currency">
            <option value="YER">ريال يمني</option>
            <option value="USD">دولار أمريكي</option>
          </select>
        `,
        techDamage: `
          <input type="text" placeholder="مثال: توقف نظام معلومات">
          <input type="number" placeholder="التكلفة (ريال)" oninput="calculateSectionTotal('techDamage','techDamageTotalYER','techDamageTotalUSD')">
          <input type="number" placeholder="مدة التأثير (بالأشهر)" oninput="calculateSectionTotal('techDamage','techDamageTotalYER','techDamageTotalUSD')">
          <select class="currency">
            <option value="YER">ريال يمني</option>
            <option value="USD">دولار أمريكي</option>
          </select>
        `,
        reputationLoss: `
          <input type="text" placeholder="مثال: فقدان عملاء">
          <input type="number" placeholder="المبلغ (ريال)" oninput="calculateSectionTotal('reputationLoss','reputationLossTotalYER','reputationLossTotalUSD')">
          <input type="number" placeholder="مدة التأثير (بالسنوات)" oninput="calculateSectionTotal('reputationLoss','reputationLossTotalYER','reputationLossTotalUSD')">
          <select class="currency">
            <option value="YER">ريال يمني</option>
            <option value="USD">دولار أمريكي</option>
          </select>
        `
      };
      let template = templates[sectionId];
      if (!template) { template = document.getElementById(sectionId).innerHTML; }
      const newItem = document.createElement('div');
      newItem.className = 'item-card';
      newItem.innerHTML = template + `<button class="remove-btn" onclick="this.parentElement.remove(); calculateSectionTotal('${sectionId}','${getTotalId(sectionId, true)}','${getTotalId(sectionId, false)}')">
          <i class="fas fa-times"></i> حذف</button>
          <button class="add-btn" onclick="addDamage('${sectionId}')">
          <i class="fas fa-plus"></i> إضافة بند</button>`;
      document.getElementById(sectionId).appendChild(newItem);
    }
    
    // دالة لاسترجاع معرف العنصر الخاص بالنتيجة (بالريال أو الدولار)
    function getTotalId(sectionId, isYER) {
      const mapping = {
        fixedAssets: { YER: 'fixedAssetsTotal', USD: 'fixedAssetsTotalUSD' },
        inventoryDamage: { YER: 'inventoryDamageTotal', USD: 'inventoryDamageTotalUSD' },
        humanLosses: { YER: 'humanTotalYER', USD: 'humanTotalUSD' },
        financialDirect: { YER: 'financialDirectTotal', USD: 'financialDirectTotalUSD' },
        operationalLosses: { YER: 'operationalTotalYER', USD: 'operationalTotalUSD' },
        delayedPayments: { YER: 'delayedTotalYER', USD: 'delayedTotalUSD' },
        institutionalDamages: { YER: 'institutionalTotalYER', USD: 'institutionalTotalUSD' },
        legalClaimsLosses: { YER: 'legalClaimsTotalYER', USD: 'legalClaimsTotalUSD' },
        rehabilitationCosts: { YER: 'rehabTotalYER', USD: 'rehabTotalUSD' },
        productionDelay: { YER: 'productionDelayTotalYER', USD: 'productionDelayTotalUSD' },
        competitiveLoss: { YER: 'competitiveLossTotalYER', USD: 'competitiveLossTotalUSD' },
        techDamage: { YER: 'techDamageTotalYER', USD: 'techDamageTotalUSD' },
        reputationLoss: { YER: 'reputationLossTotalYER', USD: 'reputationLossTotalUSD' },
        intangibleDamages: { YER: 'intangibleTotalYER', USD: 'intangibleTotalUSD' },
        delayedPayments: { YER: 'delayedTotalYER', USD: 'delayedTotalUSD' }, // مكرر – يُستخدم سابقاً
        otherDamages: { YER: 'otherTotalYER', USD: 'otherTotalUSD' }
      };
      return isYER ? mapping[sectionId].YER : mapping[sectionId].USD;
    }
    
    // دالة حساب الإجمالي لكل قسم (نفس الدالة المستخدمة لجميع الأقسام)
    function calculateSectionTotal(sectionId, totalYERId, totalUSDId) {
      const exchangeRate = parseFloat(document.getElementById('exchangeRate').value) || 1;
      let totalYER = 0, totalUSD = 0;
      document.querySelectorAll(`#${sectionId} .item-card`).forEach(item => {
        const value = parseFloat(item.querySelector('input[type="number"]').value) || 0;
        const severity = parseFloat(item.querySelector('.severity')?.value) || 1;
        const durationEl = item.querySelector('input[placeholder*="مدة"]');
        const duration = durationEl ? parseFloat(durationEl.value) || 1 : 1;
        const amount = value * severity * duration;
        const currency = item.querySelector('.currency').value;
        if (currency === 'YER') totalYER += amount;
        else totalUSD += amount;
      });
      document.getElementById(totalYERId).textContent = totalYER.toLocaleString('ar-YE') + " ريال";
      document.getElementById(totalUSDId).textContent = (totalUSD + (totalYER / exchangeRate)).toLocaleString('en-US') + " USD";
    }
    
    // دالة حساب الإجمالي النهائي لجميع الأقسام
    function calculateFinalTotal() {
      // جمع نتائج جميع الأقسام (يتم جمع النتائج من الأقسام المباشرة وغير المباشرة وأضرار أخرى)
      const direct = parseFloat(document.getElementById('fixedAssetsTotal').textContent) || 0 +
                     parseFloat(document.getElementById('inventoryDamageTotal').textContent) || 0 +
                     parseFloat(document.getElementById('humanTotalYER').textContent) || 0 +
                     parseFloat(document.getElementById('financialDirectTotal').textContent) || 0 +
                     parseFloat(document.getElementById('operationalTotalYER').textContent) || 0 +
                     parseFloat(document.getElementById('delayedTotalYER').textContent) || 0 +
                     parseFloat(document.getElementById('institutionalTotalYER').textContent) || 0 +
                     parseFloat(document.getElementById('legalClaimsTotalYER').textContent) || 0 +
                     parseFloat(document.getElementById('rehabTotalYER').textContent) || 0;
      const indirect = parseFloat(document.getElementById('productionDelayTotalYER').textContent) || 0 +
                       parseFloat(document.getElementById('competitiveLossTotalYER').textContent) || 0 +
                       parseFloat(document.getElementById('intangibleTotalYER').textContent) || 0 +
                       parseFloat(document.getElementById('techDamageTotalYER').textContent) || 0 +
                       parseFloat(document.getElementById('reputationLossTotalYER').textContent) || 0 +
                       parseFloat(document.getElementById('futurePlansTotalYER').textContent) || 0;
      const other = parseFloat(document.getElementById('otherTotalYER').textContent) || 0;
      const grand = direct + indirect + other;
      document.getElementById('finalDirectTotal').textContent = direct.toLocaleString('ar-YE');
      document.getElementById('finalIndirectTotal').textContent = indirect.toLocaleString('ar-YE');
      document.getElementById('finalDelayedTotal').textContent = document.getElementById('delayedTotalYER').textContent;
      document.getElementById('finalOtherTotal').textContent = other.toLocaleString('ar-YE');
      document.getElementById('grandTotal').textContent = grand.toLocaleString('ar-YE');
    }
    
    // وظائف إضافية: الطباعة، التصدير، المشاركة والإرسال عبر البريد الإلكتروني
    function printForm() { window.print(); }
    function exportToPDF() {
      const doc = new jsPDF();
      doc.text("الإجمالي النهائي للتعويضات:", 10, 10);
      doc.text(`بالريال اليمني: ${document.getElementById('grandTotal').textContent}`, 10, 20);
      doc.save("الإجمالي_النهائي.pdf");
    }
    function shareForm() {
      if(navigator.share) {
        navigator.share({
          title: 'الإجمالي النهائي للتعويضات',
          text: `الإجمالي: ${document.getElementById('grandTotal').textContent} ريال`,
          url: window.location.href
        }).then(() => { console.log('تمت المشاركة بنجاح'); })
          .catch((error) => { console.error('حدث خطأ أثناء المشاركة:', error); });
      } else { alert('المشاركة غير مدعومة في هذا المتصفح.'); }
    }
    function sendEmail() {
      const subject = encodeURIComponent("ملف التعويضات - الاتحاد العام للمقاولين اليمنيين");
      const body = encodeURIComponent(`مرحباً،
      
يرجى الاطلاع على ملف التعويضات النهائي:

الإجمالي: ${document.getElementById('grandTotal').textContent} ريال

مع تحيات فريق الاتحاد العام للمقاولين اليمنيين.`);
      window.location.href = `mailto:info@guyc-ye.com?subject=${subject}&body=${body}`;
    }
    
    // دالة الموافقة على الوثائق في قسم الوثائق والمستندات
    function approveDocuments() {
      alert("تمت الموافقة على الملفات المُضافة.");
    }
    
    // دالة تبديل عرض الإجابة في قسم الأسئلة الشائعة (FAQ)
    function toggleFaq(element) {
      const parent = element.parentElement;
      parent.classList.toggle("active");
      const answer = parent.querySelector(".faq-answer");
      if(parent.classList.contains("active")) {
        answer.style.maxHeight = answer.scrollHeight + "px";
      } else {
        answer.style.maxHeight = "0";
      }
    }
    
    // التهيئة الأولية عند تحميل الصفحة
    window.addEventListener('load', () => {
      updateDateTime();
      setInterval(updateDateTime, 60000);
    });
  </script>
