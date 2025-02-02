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
  <!-- Chart.js (لإضافة رسوم بيانية إذا دعت الحاجة) -->
  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
  <style>
    /* إعدادات الألوان والخطوط الأساسية – ألوان داكنة وفاخرة */
    :root {
      --primary-color: #1B2631;         /* أزرق داكن جداً */
      --secondary-color: #212F3D;       /* تدرج أزرق غامق */
      --accent-color: #F1C40F;          /* أصفر ذهبي لامع */
      --info-color: #2980B9;
      --bg-color: #1B2631;
      --section-bg: linear-gradient(135deg, #2E4053, #1B2631); /* تدرج داكن */
      --section-border: var(--accent-color);
      --text-color: #ECF0F1;
      --input-bg: #2C3E50;
      --animation-speed: 0.8s;
    }
    
    /* إعادة تعيين الأنماط الأساسية */
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
    
    /* الحاوية الرئيسية */
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
    
    /* Slider - شرائح العرض المتحركة */
    .slider {
      position: relative;
      overflow: hidden;
      border-radius: 15px;
      margin-bottom: 30px;
      box-shadow: 0 8px 30px rgba(0,0,0,0.5);
    }
    .slides {
      display: flex;
      transition: transform 1s ease;
      width: 100%;
    }
    .slide {
      min-width: 100%;
      padding: 20px;
      background: linear-gradient(135deg, #212F3D, #1B2631);
      color: #ECF0F1;
      text-align: center;
    }
    .slide h3 {
      margin-bottom: 10px;
      font-size: 1.8rem;
      color: var(--accent-color);
    }
    .slide p, .slide ul, .slide ol {
      font-size: 1rem;
      line-height: 1.6;
      text-align: justify;
      margin: 10px 0;
    }
    .slider-nav {
      text-align: center;
      margin-top: 10px;
    }
    .slider-nav button {
      background: var(--accent-color);
      border: none;
      color: #1B2631;
      padding: 8px 12px;
      margin: 0 5px;
      border-radius: 50%;
      cursor: pointer;
      transition: transform 0.3s ease;
    }
    .slider-nav button:hover {
      transform: scale(1.1);
    }
    
    /* الأقسام */
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
    
    /* قسم إضافي لأزرار الإجراءات: الآن تضم فقط أزرار الطباعة، التصدير، المشاركة والإرسال */
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
    
    /* أقسام إضافية: دليل المستخدم والتدريب وإدارة ملفات المطالبات */
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
    
    /* ميديا كويري للأجهزة الصغيرة */
    @media (max-width: 768px) {
      .header h1 { font-size: 2.8rem; }
      .header h2 { font-size: 1.4rem; }
      .section-title { font-size: 1.6rem; }
    }
    
    @media print {
      body { font-size: 12pt; background: white !important; }
      .header, .footer, button { display: none !important; }
    }
  </style>
</head>
<body>
  <div class="container">
    <!-- الهيدر -->
    <div class="header">
      <h1>الإستمارة الذكية لتسجيل الأضرار والخسائر</h1>
      <h2>قطاع المقاولات اليمني - الاتحاد العام للمقاولين اليمنيين</h2>
      <div class="reference-number" id="fileNumber"></div>
      <div class="timestamp" id="currentDate"></div>
      <p>زوروا موقعنا: <a href="https://guyc-ye.com/" target="_blank">guyc-ye.com</a></p>
    </div>
    
    <!-- Slider: شرائح العرض المتحركة -->
    <div class="slider">
      <div class="slides">
        <div class="slide">
          <h3>مقدمة</h3>
          <p>
            يواجه قطاع المقاولات في اليمن تحديات كبيرة بسبب الحرب والصراع المستمر، مما أدى إلى خسائر مادية جسيمة للمقاولين، سواء من حيث تدمير الممتلكات والمشاريع، أو التأخير في تنفيذ العقود، أو فقدان الإيرادات بسبب توقف الأعمال.
          </p>
          <p>
            يهدف هذا الدليل إلى تزويد المقاولين المتضررين بخطة عمل واضحة ومفصلة تمكنهم من المطالبة بالتعويضات العادلة عن الخسائر التي تكبدوها.
          </p>
        </div>
        <div class="slide">
          <h3>أهمية هذا الدليل</h3>
          <p>
            1. تزويد المقاولين بفهم واضح لكيفية توثيق الأضرار والخسائر.<br>
            2. شرح عملية حساب التعويضات وفقًا للمعايير الدولية.<br>
            3. توضيح إجراءات تقديم المطالبات إلى الجهات المختصة.<br>
            4. إرشاد المقاولين إلى الطرق القانونية للمطالبة بحقوقهم.
          </p>
        </div>
        <div class="slide">
          <h3>المرحلة الأولى: التوثيق الدقيق للأضرار والخسائر</h3>
          <p><strong>جمع الأدلة المادية:</strong></p>
          <ul>
            <li>التقاط صور وفيديوهات واضحة لجميع الأضرار.</li>
            <li>تصوير كل زاوية للمباني والمعدات.</li>
            <li>استخدام GPS لتحديد الموقع الدقيق.</li>
          </ul>
          <p><strong>إعداد قائمة مفصلة بالأضرار:</strong></p>
          <ul>
            <li>تحديد نوع الضرر ووصف العناصر المتضررة بدقة.</li>
          </ul>
          <p><strong>توثيق الأضرار بالوثائق الرسمية:</strong></p>
          <ul>
            <li>جمع العقود والفواتير والتقارير الرسمية.</li>
            <li>الحصول على إفادات من الشهود.</li>
          </ul>
        </div>
        <div class="slide">
          <h3>المرحلة الثانية: حساب الخسائر والتعويضات المطلوبة</h3>
          <p><strong>تصنيف الخسائر:</strong> مباشرة وغير مباشرة.</p>
          <p><strong>استخدام معايير التقييم الدولية:</strong></p>
          <ul>
            <li>تقييم تكلفة الإصلاح والاستبدال.</li>
            <li>تقدير تكلفة الفرصة البديلة والإيرادات المفقودة.</li>
          </ul>
          <p><strong>توثيق الحسابات المالية:</strong> إعداد تقارير مفصلة ومدعومة.</p>
        </div>
        <div class="slide">
          <h3>المرحلة الثالثة: التقديم للجهات المختصة</h3>
          <p>
            تحديد الجهة المختصة (الحكومة، الهيئات القضائية، المنظمات الدولية) وإعداد ملف تعويض يشمل كافة الأدلة والتقارير.
          </p>
        </div>
        <div class="slide">
          <h3>المرحلة الرابعة: المتابعة القانونية والتفاوض</h3>
          <p>
            تقديم الدعوى القانونية في حال الرفض، والتفاوض أو اللجوء للتحكيم لتسوية النزاعات.
          </p>
        </div>
        <div class="slide">
          <h3>الدليل المرجعي القانوني</h3>
          <p>
            اتفاقيات جنيف، النظام الأساسي للمحكمة الجنائية الدولية، قرارات الأمم المتحدة، والمبادئ الوطنية.
          </p>
        </div>
        <div class="slide">
          <h3>الختام والتوصيات</h3>
          <p>
            توثيق كل الأضرار، تقديم المطالبات وفق المعايير، والاستعانة بالخبراء للمطالبة بحقوقك.
          </p>
        </div>
      </div>
      <div class="slider-nav">
        <button onclick="prevSlide()"><i class="fas fa-chevron-right"></i></button>
        <button onclick="nextSlide()"><i class="fas fa-chevron-left"></i></button>
      </div>
    </div>
    
    <!-- مقدمة تعريفية -->
    <div class="section">
      <div class="section-title">
        <i class="fas fa-info-circle"></i>
        <h2>مقدمة تعريفية</h2>
      </div>
      <div class="section-intro">
        <p>
          يُعد هذا النظام منصة شاملة لتوثيق وحساب كافة أنواع الأضرار والخسائر الناتجة عن الأزمات، الحروب والنزاعات المسلحة وفقًا للمعايير الدولية وأفضل الممارسات العالمية. يساعد النظام المقاولين على إعداد ملف مطالبة متكامل ودقيق مدعومًا بالأدلة والمرجعيات القانونية.
        </p>
        <ul>
          <li><strong>الفئات المستهدفة:</strong> المقاولون، الشركات الإنشائية، الجهات الحكومية، منظمات المجتمع المدني.</li>
          <li><strong>أهمية النظام:</strong> توثيق شامل وحساب دقيق وإعداد ملف مطالبة متكامل.</li>
          <li><strong>تنويه:</strong> تُستخدم البيانات للتقييم الأولي وقد تخضع للمراجعة من الجهات المختصة.</li>
        </ul>
      </div>
    </div>
    
    <!-- إعدادات العملة -->
    <div class="section">
      <div class="section-title">
        <i class="fas fa-coins"></i>
        <h2>إعدادات العملة</h2>
      </div>
      <div class="input-group">
        <label>سعر صرف الدولار (USD) مقابل الريال (YER):</label>
        <input type="number" id="exchangeRate" placeholder="أدخل سعر الصرف" required>
      </div>
    </div>
    
    <!-- البيانات الأساسية -->
    <div class="section">
      <div class="section-title">
        <i class="fas fa-building"></i>
        <h2>البيانات الأساسية</h2>
      </div>
      <div class="input-group">
        <label>اسم الشركة/المؤسسة:</label>
        <input type="text" id="companyName" placeholder="أدخل اسم الشركة" required>
      </div>
      <div class="input-group">
        <label>اسم المقاول المسؤول:</label>
        <input type="text" id="contractorName" placeholder="أدخل اسم المقاول" required>
      </div>
      <div class="input-group">
        <label>رقم الهاتف:</label>
        <input type="tel" id="phoneNumber" placeholder="أدخل رقم الهاتف" required>
      </div>
    </div>
    
    <!-- قسم الأضرار المباشرة -->
    <div class="section" id="sectionDirect">
      <div class="section-title">
        <i class="fas fa-exclamation-circle"></i>
        <h2>1. الأضرار والخسائر المباشرة</h2>
      </div>
      <div class="section-intro">
        <p>
          <strong>طريقة الحساب:</strong> تُحسب قيمة الضرر بضرب القيمة المدخلة بنسبة الضرر (severity) ومدة الضرر.<br>
          <strong>المرجع القانوني:</strong> معايير IVSC وRICS – (مثال: المادة 15 من اتفاقية تقييم الأضرار الدولية).
        </p>
      </div>
      <!-- بند أضرار الأصول الثابتة -->
      <h3>أ. أضرار الأصول الثابتة</h3>
      <div class="dynamic-list" id="fixedAssets">
        <div class="item-card">
          <input type="text" placeholder="مثال: مبنى رئيسي">
          <input type="number" placeholder="قيمة الضرر (ريال)" oninput="calcFixedAssets()">
          <select class="severity" oninput="calcFixedAssets()">
            <option value="1">استبدال كامل (100%)</option>
            <option value="0.7">إصلاح جزئي (70%)</option>
            <option value="0.3">إصلاح بسيط (30%)</option>
          </select>
          <input type="number" placeholder="مدة الضرر (بالسنوات)" oninput="calcFixedAssets()">
          <select class="currency">
            <option value="YER">ريال يمني</option>
            <option value="USD">دولار أمريكي</option>
          </select>
          <button class="remove-btn" onclick="this.parentElement.remove(); calcFixedAssets()">
            <i class="fas fa-times"></i> حذف
          </button>
          <button class="add-btn" onclick="addDamage('fixedAssets')">
            <i class="fas fa-plus"></i> إضافة بند
          </button>
        </div>
      </div>
      <button class="btn" onclick="calcFixedAssets()">حساب أضرار الأصول الثابتة</button>
      <div class="total-box" id="fixedAssetsTotalBox">
        <h4>الإجمالي: <span id="fixedAssetsTotal">0</span> ريال</h4>
      </div>
      
      <!-- بند أضرار المخزون والمواد -->
      <h3>ب. الأضرار المادية للمخزون والمواد</h3>
      <div class="dynamic-list" id="inventoryDamage">
        <div class="item-card">
          <input type="text" placeholder="مثال: مواد خام">
          <input type="number" placeholder="قيمة الضرر (ريال)" oninput="calcInventoryDamage()">
          <select class="severity" oninput="calcInventoryDamage()">
            <option value="1">خسارة كاملة (100%)</option>
            <option value="0.5">خسارة جزئية (50%)</option>
          </select>
          <input type="number" placeholder="مدة الضرر (بالأشهر)" oninput="calcInventoryDamage()">
          <select class="currency">
            <option value="YER">ريال يمني</option>
            <option value="USD">دولار أمريكي</option>
          </select>
          <button class="remove-btn" onclick="this.parentElement.remove(); calcInventoryDamage()">
            <i class="fas fa-times"></i> حذف
          </button>
          <button class="add-btn" onclick="addDamage('inventoryDamage')">
            <i class="fas fa-plus"></i> إضافة بند
          </button>
        </div>
      </div>
      <button class="btn" onclick="calcInventoryDamage()">حساب أضرار المخزون</button>
      <div class="total-box" id="inventoryDamageTotalBox">
        <h4>الإجمالي: <span id="inventoryDamageTotal">0</span> ريال</h4>
      </div>
      
      <!-- بند الأضرار المالية والتدفقات النقدية -->
      <h3>ج. الأضرار المالية والتدفقات النقدية</h3>
      <div class="dynamic-list" id="financialDirect">
        <div class="item-card">
          <input type="text" placeholder="مثال: خسارة إيرادات شهرية">
          <input type="number" placeholder="مقدار الخسارة (ريال)" oninput="calcFinancialDirect()">
          <input type="number" placeholder="مدة الضرر (بالأشهر)" oninput="calcFinancialDirect()">
          <select class="currency">
            <option value="YER">ريال يمني</option>
            <option value="USD">دولار أمريكي</option>
          </select>
          <button class="remove-btn" onclick="this.parentElement.remove(); calcFinancialDirect()">
            <i class="fas fa-times"></i> حذف
          </button>
          <button class="add-btn" onclick="addDamage('financialDirect')">
            <i class="fas fa-plus"></i> إضافة بند
          </button>
        </div>
      </div>
      <button class="btn" onclick="calcFinancialDirect()">حساب الأضرار المالية</button>
      <div class="total-box" id="financialDirectTotalBox">
        <h4>الإجمالي: <span id="financialDirectTotal">0</span> ريال</h4>
      </div>
      
      <!-- بند الأضرار المؤسسية -->
      <h3>د. الأضرار المؤسسية</h3>
      <div class="dynamic-list" id="institutionalDamage">
        <div class="item-card">
          <input type="text" placeholder="مثال: فقدان موظف رئيسي">
          <input type="number" placeholder="قيمة الضرر (ريال)" oninput="calcInstitutionalDamage()">
          <select class="severity" oninput="calcInstitutionalDamage()">
            <option value="1">خسارة كاملة (100%)</option>
            <option value="0.5">خسارة جزئية (50%)</option>
          </select>
          <input type="number" placeholder="مدة الضرر (بالسنوات)" oninput="calcInstitutionalDamage()">
          <select class="currency">
            <option value="YER">ريال يمني</option>
            <option value="USD">دولار أمريكي</option>
          </select>
          <button class="remove-btn" onclick="this.parentElement.remove(); calcInstitutionalDamage()">
            <i class="fas fa-times"></i> حذف
          </button>
          <button class="add-btn" onclick="addDamage('institutionalDamage')">
            <i class="fas fa-plus"></i> إضافة بند
          </button>
        </div>
      </div>
      <button class="btn" onclick="calcInstitutionalDamage()">حساب الأضرار المؤسسية</button>
      <div class="total-box" id="institutionalDamageTotalBox">
        <h4>الإجمالي: <span id="institutionalDamageTotal">0</span> ريال</h4>
      </div>
    </div>
    
    <!-- قسم الأضرار غير المباشرة -->
    <div class="section" id="sectionIndirect">
      <div class="section-title">
        <i class="fas fa-exclamation-triangle"></i>
        <h2>2. الأضرار والخسائر غير المباشرة</h2>
      </div>
      <div class="section-intro">
        <p>
          <strong>طريقة الحساب:</strong> تُحسب قيمة الضرر غير المباشر بضرب القيمة المدخلة بنسبة التأثير ومدة الضرر.<br>
          <strong>المرجع القانوني:</strong> معايير الأمم المتحدة لتقييم الأضرار – (مثال: المادة 20 من اتفاقية التعويضات الدولية).
        </p>
      </div>
      <!-- بند تعطيل الإنتاج والتأخير -->
      <h3>أ. تعطيل الإنتاج والتأخير</h3>
      <div class="dynamic-list" id="productionDelay">
        <div class="item-card">
          <input type="text" placeholder="مثال: توقف الإنتاج">
          <input type="number" placeholder="خسارة شهرية (ريال)" oninput="calcProductionDelay()">
          <input type="number" placeholder="مدة التأخير (بالأشهر)" oninput="calcProductionDelay()">
          <select class="currency">
            <option value="YER">ريال يمني</option>
            <option value="USD">دولار أمريكي</option>
          </select>
          <button class="remove-btn" onclick="this.parentElement.remove(); calcProductionDelay()">
            <i class="fas fa-times"></i> حذف
          </button>
          <button class="add-btn" onclick="addDamage('productionDelay')">
            <i class="fas fa-plus"></i> إضافة بند
          </button>
        </div>
      </div>
      <button class="btn" onclick="calcProductionDelay()">حساب تعطيل الإنتاج</button>
      <div class="total-box" id="productionDelayTotalBox">
        <h4>الإجمالي: <span id="productionDelayTotal">0</span> ريال</h4>
      </div>
      
      <!-- بند خسارة القدرة التنافسية -->
      <h3>ب. خسارة القدرة التنافسية</h3>
      <div class="dynamic-list" id="competitiveLoss">
        <div class="item-card">
          <input type="text" placeholder="مثال: انخفاض حصص السوق">
          <input type="number" placeholder="خسارة شهرية (ريال)" oninput="calcCompetitiveLoss()">
          <input type="number" placeholder="مدة التأثير (بالأشهر)" oninput="calcCompetitiveLoss()">
          <select class="currency">
            <option value="YER">ريال يمني</option>
            <option value="USD">دولار أمريكي</option>
          </select>
          <button class="remove-btn" onclick="this.parentElement.remove(); calcCompetitiveLoss()">
            <i class="fas fa-times"></i> حذف
          </button>
          <button class="add-btn" onclick="addDamage('competitiveLoss')">
            <i class="fas fa-plus"></i> إضافة بند
          </button>
        </div>
      </div>
      <button class="btn" onclick="calcCompetitiveLoss()">حساب خسارة القدرة التنافسية</button>
      <div class="total-box" id="competitiveLossTotalBox">
        <h4>الإجمالي: <span id="competitiveLossTotal">0</span> ريال</h4>
      </div>
      
      <!-- بند الضرر التكنولوجي أو البرمجي -->
      <h3>ج. الضرر التكنولوجي أو البرمجي</h3>
      <div class="dynamic-list" id="techDamage">
        <div class="item-card">
          <input type="text" placeholder="مثال: تعطل نظام معلومات">
          <input type="number" placeholder="تكلفة الإصلاح (ريال)" oninput="calcTechDamage()">
          <input type="number" placeholder="مدة التعطل (بالأشهر)" oninput="calcTechDamage()">
          <select class="currency">
            <option value="YER">ريال يمني</option>
            <option value="USD">دولار أمريكي</option>
          </select>
          <button class="remove-btn" onclick="this.parentElement.remove(); calcTechDamage()">
            <i class="fas fa-times"></i> حذف
          </button>
          <button class="add-btn" onclick="addDamage('techDamage')">
            <i class="fas fa-plus"></i> إضافة بند
          </button>
        </div>
      </div>
      <button class="btn" onclick="calcTechDamage()">حساب الضرر التكنولوجي</button>
      <div class="total-box" id="techDamageTotalBox">
        <h4>الإجمالي: <span id="techDamageTotal">0</span> ريال</h4>
      </div>
      
      <!-- بند الأضرار البيئية -->
      <h3>د. الأضرار البيئية</h3>
      <div class="dynamic-list" id="envDamage">
        <div class="item-card">
          <input type="text" placeholder="مثال: تلوث بيئي">
          <input type="number" placeholder="تكلفة الإصلاح (ريال)" oninput="calcEnvDamage()">
          <input type="number" placeholder="مدة الضرر (بالسنوات)" oninput="calcEnvDamage()">
          <select class="currency">
            <option value="YER">ريال يمني</option>
            <option value="USD">دولار أمريكي</option>
          </select>
          <button class="remove-btn" onclick="this.parentElement.remove(); calcEnvDamage()">
            <i class="fas fa-times"></i> حذف
          </button>
          <button class="add-btn" onclick="addDamage('envDamage')">
            <i class="fas fa-plus"></i> إضافة بند
          </button>
        </div>
      </div>
      <button class="btn" onclick="calcEnvDamage()">حساب الأضرار البيئية</button>
      <div class="total-box" id="envDamageTotalBox">
        <h4>الإجمالي: <span id="envDamageTotal">0</span> ريال</h4>
      </div>
    </div>
    
    <!-- قسم خسائر تأخر دفع المستحقات -->
    <div class="section" id="sectionDelayed">
      <div class="section-title">
        <i class="fas fa-clock"></i>
        <h2>3. خسائر تأخر دفع المستحقات</h2>
      </div>
      <div class="section-intro">
        <p>
          <strong>طريقة الحساب:</strong> تُحسب الخسائر بضرب المبلغ المتأخر في مدة التأخير (بالأشهر) مع احتساب فائدة تراكمية بنسبة 5% سنويًا تقريبًا.<br>
          <strong>المرجع القانوني:</strong> معايير البنك الدولي والقوانين المحلية – (مثال: المادة 8 من اتفاقية التعويضات الوطنية).
        </p>
      </div>
      <div class="dynamic-list" id="delayedPayments">
        <div class="item-card">
          <input type="text" placeholder="مثال: تأخر دفع مستحقات مشروع X">
          <input type="number" placeholder="المبلغ المتأخر (ريال)" oninput="calculateSectionTotal('delayedPayments','delayedTotalYER','delayedTotalUSD')">
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
      <button class="btn" onclick="calculateSectionTotal('delayedPayments','delayedTotalYER','delayedTotalUSD')">حساب خسائر تأخر الدفع</button>
      <div class="total-box" id="delayedTotalBox">
        <h4>الإجمالي: <span id="delayedTotalYER">0</span> ريال | <span id="delayedTotalUSD">0</span> USD</h4>
      </div>
    </div>
    
    <!-- قسم الأضرار الأخرى -->
    <div class="section" id="sectionOther">
      <div class="section-title">
        <i class="fas fa-ellipsis-h"></i>
        <h2>4. الأضرار الأخرى</h2>
      </div>
      <div class="section-intro">
        <p>
          يمكنك هنا إضافة أنواع إضافية من الأضرار التي لم تُدرج سابقًا، مع تحديد الوصف، القيمة، المدة ونسبة التأثير. يُستخدم هذا القسم لتسجيل أضرار غير متوقعة أو خاصة.
        </p>
      </div>
      <div class="dynamic-list" id="otherDamages">
        <div class="item-card">
          <input type="text" placeholder="وصف الضرر">
          <input type="number" placeholder="المبلغ (ريال)" oninput="calculateSectionTotal('otherDamages','otherTotalYER','otherTotalUSD')">
          <input type="number" placeholder="مدة الضرر (بالأشهر/بالسنوات)" oninput="calculateSectionTotal('otherDamages','otherTotalYER','otherTotalUSD')">
          <select class="severity" oninput="calculateSectionTotal('otherDamages','otherTotalYER','otherTotalUSD')">
            <option value="1">تأثير كامل (100%)</option>
            <option value="0.5">تأثير جزئي (50%)</option>
          </select>
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
      <button class="btn" onclick="calculateSectionTotal('otherDamages','otherTotalYER','otherTotalUSD')">حساب الأضرار الأخرى</button>
      <div class="total-box" id="otherTotalBox">
        <h4>الإجمالي: <span id="otherTotalYER">0</span> ريال | <span id="otherTotalUSD">0</span> USD</h4>
      </div>
    </div>
    
    <!-- قسم دليل المستخدم والتدريب -->
    <div class="extra-section" id="userGuide">
      <div class="section-title">
        <i class="fas fa-book"></i>
        <h2>دليل المستخدم والتدريب</h2>
      </div>
      <div class="section-intro">
        <p>
          يحتوي هذا القسم على تعليمات مفصلة حول كيفية استخدام النظام وإعداد ملف المطالبة:
        </p>
        <ol>
          <li>ابدأ بإدخال بيانات الشركة والمقاول والاتصال في قسم "البيانات الأساسية".</li>
          <li>قم بتحديد سعر الصرف في قسم "إعدادات العملة".</li>
          <li>انتقل إلى أقسام الأضرار (المباشرة وغير المباشرة، خسائر تأخر الدفع، والأضرار الأخرى) وأدخل التفاصيل المطلوبة لكل بند مع تحديد القيمة، النسبة والمدة.</li>
          <li>استخدم زر "إضافة بند" لإدراج المزيد من البنود داخل كل قسم.</li>
          <li>اضغط على زر الحساب في كل قسم لمعاينة الإجمالي الفرعي لذلك القسم.</li>
          <li>انتقل إلى قسم "الخلاصة النهائية" لمراجعة وتجميع كافة النتائج.</li>
          <li>استخدم زر "حساب الإجمالي النهائي" الموجود داخل قسم الخلاصة.</li>
        </ol>
        <p>
          <strong>ملاحظة:</strong> تأكد من مراجعة كافة البيانات والوثائق قبل تقديم ملف المطالبة للجهات المختصة.
        </p>
      </div>
    </div>
    
    <!-- قسم إدارة ملفات المطالبات -->
    <div class="extra-section" id="claimsManagement">
      <div class="section-title">
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
          <li>متابعة حالة المطالبة من خلال تحديث بيانات الملف وإرفاق الوثائق اللازمة.</li>
          <li>تصدير تقارير مفصلة عن المطالبات للمتابعة مع الجهات المختصة.</li>
        </ol>
      </div>
    </div>
    
    <!-- قسم الخلاصة النهائية -->
    <div class="section" id="sectionFinal">
      <div class="section-title">
        <i class="fas fa-file-invoice-dollar"></i>
        <h2>5. الخلاصة النهائية</h2>
      </div>
      <div class="total-box" id="finalTotalBox">
        <p>الإجمالي المباشر: <span id="finalDirectTotal">0</span> ريال</p>
        <p>الإجمالي غير المباشر: <span id="finalIndirectTotal">0</span> ريال</p>
        <p>خسائر تأخر الدفع: <span id="finalDelayedTotal">0</span> ريال</p>
        <p>الأضرار الأخرى: <span id="finalOtherTotal">0</span> ريال</p>
        <p><strong>الإجمالي الكلي: <span id="grandTotal">0</span> ريال</strong></p>
        <!-- زر حساب الإجمالي النهائي موجود داخل هذا القسم -->
        <button class="btn" onclick="calculateFinalTotal()">
          <i class="fas fa-calculator"></i> حساب الإجمالي النهائي
        </button>
      </div>
    </div>
    
    <!-- قسم أزرار الإجراءات الجديدة -->
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
    
    <!-- قسم الدليل الإرشادي الشامل لنيل التعويضات -->
    <div class="extra-section" id="guidelines">
      <div class="section-title">
        <i class="fas fa-chalkboard-teacher"></i>
        <h2>الدليل الإرشادي الشامل لنيل التعويضات العادلة عن الأضرار والخسائر في قطاع المقاولات اليمني</h2>
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
          <li>خسائر مباشرة: تدمير المباني، الآليات، المعدات، المواد الخام.</li>
          <li>خسائر غير مباشرة: توقف المشروع، فقدان الإيرادات، تكاليف إضافية بسبب التأخير.</li>
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
    
    <!-- قسم الخاتمة والتوصيات -->
    <div class="section">
      <div class="section-title">
        <i class="fas fa-thumbs-up"></i>
        <h2>7. الخاتمة والتوصيات</h2>
      </div>
      <div class="section-intro">
        <p>
          نشكرك على استخدام هذا النظام الشامل لحساب الأضرار والخسائر. يُرجى مراجعة وتحديث البيانات وتوثيق كافة الأدلة قبل تقديم ملف المطالبة. نوصي بالتواصل مع الجهات المختصة للحصول على التعويضات العادلة وفق المعايير الدولية وأفضل الممارسات العالمية.
        </p>
      </div>
    </div>
    
    <!-- قسم الإقرار والموافقة -->
    <div class="section">
      <div class="section-title">
        <i class="fas fa-check-circle"></i>
        <h2>8. الإقرار والموافقة</h2>
      </div>
      <div class="section-intro">
        <p>
          بموجب هذا، أقر بصحة البيانات والمعلومات المدخلة وأوافق على استخدامها لحساب الأضرار والخسائر، وأتعهد بتحمل المسؤولية القانونية عن دقتها.
        </p>
        <div class="input-group">
          <label>
            <input type="checkbox" id="agreement" required> أوافق على صحة البيانات المقدمة.
          </label>
        </div>
      </div>
    </div>
    
    <!-- قسم أزرار الإجراءات الجديدة (بعد الإقرار وقبل الفوتر) -->
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
        directDamages: `
          <select class="damage-type">
            <option value="أضرار الأصول الثابتة">أضرار الأصول الثابتة<br>(المباني، المعدات، الأدوات)</option>
            <option value="أضرار المخزون">الأضرار المادية للمخزون والمواد</option>
            <option value="أضرار مالية">الأضرار المالية والتدفقات النقدية</option>
            <option value="أضرار مؤسسية">الأضرار المؤسسية<br>(فقدان الموظفين، إصابات العمل)</option>
          </select>
          <input type="text" placeholder="تفاصيل البند">
          <input type="number" placeholder="المبلغ" oninput="calculateSectionTotal('directDamages','directTotalYER','directTotalUSD')">
          <select class="severity" oninput="calculateSectionTotal('directDamages','directTotalYER','directTotalUSD')">
            <option value="1">استبدال كامل (100%)</option>
            <option value="0.7">إصلاح جزئي (70%)</option>
            <option value="0.3">إصلاح بسيط (30%)</option>
          </select>
          <input type="number" placeholder="مدة الضرر (بالسنوات)" oninput="calculateSectionTotal('directDamages','directTotalYER','directTotalUSD')">
          <select class="currency">
            <option value="YER">ريال يمني</option>
            <option value="USD">دولار أمريكي</option>
          </select>
        `,
        indirectDamages: `
          <select class="damage-type">
            <option value="تعطيل الإنتاج">تعطيل الإنتاج والتأخير</option>
            <option value="خسارة تنافسية">خسارة القدرة التنافسية</option>
            <option value="ضرر تقني">الضرر التكنولوجي أو البرمجي</option>
            <option value="أضرار بيئية">الأضرار البيئية</option>
          </select>
          <input type="text" placeholder="تفاصيل البند">
          <input type="number" placeholder="المبلغ" oninput="calculateSectionTotal('indirectDamages','indirectTotalYER','indirectTotalUSD')">
          <select class="severity" oninput="calculateSectionTotal('indirectDamages','indirectTotalYER','indirectTotalUSD')">
            <option value="1">تأثير كامل (100%)</option>
            <option value="0.5">تأثير جزئي (50%)</option>
          </select>
          <input type="number" placeholder="مدة الضرر (بالأشهر)" oninput="calculateSectionTotal('indirectDamages','indirectTotalYER','indirectTotalUSD')">
          <select class="currency">
            <option value="YER">ريال يمني</option>
            <option value="USD">دولار أمريكي</option>
          </select>
        `,
        fixedAssets: `
          <input type="text" placeholder="مثال: مبنى رئيسي">
          <input type="number" placeholder="قيمة الضرر (ريال)" oninput="calcFixedAssets()">
          <select class="severity" oninput="calcFixedAssets()">
            <option value="1">استبدال كامل (100%)</option>
            <option value="0.7">إصلاح جزئي (70%)</option>
            <option value="0.3">إصلاح بسيط (30%)</option>
          </select>
          <input type="number" placeholder="مدة الضرر (بالسنوات)" oninput="calcFixedAssets()">
          <select class="currency">
            <option value="YER">ريال يمني</option>
            <option value="USD">دولار أمريكي</option>
          </select>
        `,
        inventoryDamage: `
          <input type="text" placeholder="مثال: مواد خام">
          <input type="number" placeholder="قيمة الضرر (ريال)" oninput="calcInventoryDamage()">
          <select class="severity" oninput="calcInventoryDamage()">
            <option value="1">خسارة كاملة (100%)</option>
            <option value="0.5">خسارة جزئية (50%)</option>
          </select>
          <input type="number" placeholder="مدة الضرر (بالأشهر)" oninput="calcInventoryDamage()">
          <select class="currency">
            <option value="YER">ريال يمني</option>
            <option value="USD">دولار أمريكي</option>
          </select>
        `,
        financialDirect: `
          <input type="text" placeholder="مثال: خسارة إيرادات شهرية">
          <input type="number" placeholder="مقدار الخسارة (ريال)" oninput="calcFinancialDirect()">
          <input type="number" placeholder="مدة الضرر (بالأشهر)" oninput="calcFinancialDirect()">
          <select class="currency">
            <option value="YER">ريال يمني</option>
            <option value="USD">دولار أمريكي</option>
          </select>
        `,
        institutionalDamage: `
          <input type="text" placeholder="مثال: فقدان موظف رئيسي">
          <input type="number" placeholder="قيمة الضرر (ريال)" oninput="calcInstitutionalDamage()">
          <select class="severity" oninput="calcInstitutionalDamage()">
            <option value="1">خسارة كاملة (100%)</option>
            <option value="0.5">خسارة جزئية (50%)</option>
          </select>
          <input type="number" placeholder="مدة الضرر (بالسنوات)" oninput="calcInstitutionalDamage()">
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
      newItem.innerHTML = template + `<button class="remove-btn" onclick="this.parentElement.remove(); calculateSectionTotal('${sectionId}', '${getTotalId(sectionId, true)}', '${getTotalId(sectionId, false)}')">
          <i class="fas fa-times"></i> حذف</button>
          <button class="add-btn" onclick="addDamage('${sectionId}')">
          <i class="fas fa-plus"></i> إضافة بند</button>`;
      document.getElementById(sectionId).appendChild(newItem);
    }
    function getTotalId(sectionId, isYER) {
      if(sectionId === 'directDamages') return isYER ? 'directTotalYER' : 'directTotalUSD';
      if(sectionId === 'indirectDamages') return isYER ? 'indirectTotalYER' : 'indirectTotalUSD';
      if(sectionId === 'fixedAssets') return isYER ? 'fixedAssetsTotal' : 'fixedAssetsTotalUSD';
      if(sectionId === 'inventoryDamage') return isYER ? 'inventoryDamageTotal' : 'inventoryDamageTotalUSD';
      if(sectionId === 'financialDirect') return isYER ? 'financialDirectTotal' : 'financialDirectTotalUSD';
      if(sectionId === 'institutionalDamage') return isYER ? 'institutionalDamageTotal' : 'institutionalDamageTotalUSD';
      if(sectionId === 'delayedPayments') return isYER ? 'delayedTotalYER' : 'delayedTotalUSD';
      if(sectionId === 'otherDamages') return isYER ? 'otherTotalYER' : 'otherTotalUSD';
      return isYER ? sectionId + "TotalYER" : sectionId + "TotalUSD";
    }
    
    // دوال حساب لكل قسم:
    function calcFixedAssets() {
      let total = 0;
      document.querySelectorAll('#fixedAssets .item-card').forEach(item => {
        const value = parseFloat(item.querySelector('input[type="number"]').value) || 0;
        const severity = parseFloat(item.querySelector('.severity')?.value) || 1;
        const duration = parseFloat(item.querySelector('input[placeholder*="مدة الضرر"]')?.value) || 1;
        total += value * severity * duration;
      });
      document.getElementById('fixedAssetsTotal').textContent = total.toLocaleString('ar-YE') + " ريال";
    }
    function calcInventoryDamage() {
      let total = 0;
      document.querySelectorAll('#inventoryDamage .item-card').forEach(item => {
        const value = parseFloat(item.querySelector('input[type="number"]').value) || 0;
        const severity = parseFloat(item.querySelector('.severity')?.value) || 1;
        const duration = parseFloat(item.querySelector('input[placeholder*="مدة الضرر"]')?.value) || 1;
        total += value * severity * duration;
      });
      document.getElementById('inventoryDamageTotal').textContent = total.toLocaleString('ar-YE') + " ريال";
    }
    function calcFinancialDirect() {
      let total = 0;
      document.querySelectorAll('#financialDirect .item-card').forEach(item => {
        const value = parseFloat(item.querySelector('input[type="number"]').value) || 0;
        const duration = parseFloat(item.querySelector('input[placeholder*="مدة الضرر"]')?.value) || 1;
        total += value * duration;
      });
      document.getElementById('financialDirectTotal').textContent = total.toLocaleString('ar-YE') + " ريال";
    }
    function calcInstitutionalDamage() {
      let total = 0;
      document.querySelectorAll('#institutionalDamage .item-card').forEach(item => {
        const value = parseFloat(item.querySelector('input[type="number"]').value) || 0;
        const severity = parseFloat(item.querySelector('.severity')?.value) || 1;
        const duration = parseFloat(item.querySelector('input[placeholder*="مدة الضرر"]')?.value) || 1;
        total += value * severity * duration;
      });
      document.getElementById('institutionalDamageTotal').textContent = total.toLocaleString('ar-YE') + " ريال";
    }
    function calcProductionDelay() {
      let total = 0;
      document.querySelectorAll('#productionDelay .item-card').forEach(item => {
        const value = parseFloat(item.querySelector('input[type="number"]').value) || 0;
        const duration = parseFloat(item.querySelector('input[placeholder*="مدة التأخير"]')?.value) || 1;
        total += value * duration;
      });
      document.getElementById('productionDelayTotal').textContent = total.toLocaleString('ar-YE') + " ريال";
    }
    function calcCompetitiveLoss() {
      let total = 0;
      document.querySelectorAll('#competitiveLoss .item-card').forEach(item => {
        const value = parseFloat(item.querySelector('input[type="number"]').value) || 0;
        const duration = parseFloat(item.querySelector('input[placeholder*="مدة التأثير"]')?.value) || 1;
        total += value * duration;
      });
      document.getElementById('competitiveLossTotal').textContent = total.toLocaleString('ar-YE') + " ريال";
    }
    function calcTechDamage() {
      let total = 0;
      document.querySelectorAll('#techDamage .item-card').forEach(item => {
        const value = parseFloat(item.querySelector('input[type="number"]').value) || 0;
        const duration = parseFloat(item.querySelector('input[placeholder*="مدة التعطل"]')?.value) || 1;
        total += value * duration;
      });
      document.getElementById('techDamageTotal').textContent = total.toLocaleString('ar-YE') + " ريال";
    }
    function calcEnvDamage() {
      let total = 0;
      document.querySelectorAll('#envDamage .item-card').forEach(item => {
        const value = parseFloat(item.querySelector('input[type="number"]').value) || 0;
        const duration = parseFloat(item.querySelector('input[placeholder*="مدة الضرر"]')?.value) || 1;
        total += value * duration;
      });
      document.getElementById('envDamageTotal').textContent = total.toLocaleString('ar-YE') + " ريال";
    }
    
    // دالة حساب الإجمالي النهائي لجميع الأقسام
    function calculateFinalTotal() {
      const direct = parseFloat(document.getElementById('directTotalYER').textContent) || 0;
      const indirect = parseFloat(document.getElementById('indirectTotalYER').textContent) || 0;
      const delayed = document.getElementById('delayedTotalYER') ? parseFloat(document.getElementById('delayedTotalYER').textContent) || 0 : 0;
      const other = document.getElementById('otherTotalYER') ? parseFloat(document.getElementById('otherTotalYER').textContent) || 0 : 0;
      const grand = direct + indirect + delayed + other;
      document.getElementById('finalDirectTotal').textContent = direct.toLocaleString('ar-YE');
      document.getElementById('finalIndirectTotal').textContent = indirect.toLocaleString('ar-YE');
      if(document.getElementById('delayedTotalYER'))
        document.getElementById('finalDelayedTotal').textContent = delayed.toLocaleString('ar-YE');
      if(document.getElementById('otherTotalYER'))
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
    
    // Slider functions
    const slidesContainer = document.querySelector('.slides');
    let currentSlide = 0;
    const slides = document.querySelectorAll('.slide');
    const totalSlides = slides.length;
    
    function showSlide(index) {
      if (index < 0) currentSlide = totalSlides - 1;
      else if (index >= totalSlides) currentSlide = 0;
      else currentSlide = index;
      slidesContainer.style.transform = 'translateX(-' + currentSlide * 100 + '%)';
    }
    function nextSlide() { showSlide(currentSlide + 1); }
    function prevSlide() { showSlide(currentSlide - 1); }
    setInterval(nextSlide, 6000);
    
    // التهيئة الأولية عند تحميل الصفحة
    window.addEventListener('load', () => {
      updateDateTime();
      setInterval(updateDateTime, 60000);
    });
  </script>
</body>
</html>
