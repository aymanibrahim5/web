<!DOCTYPE html>
<html lang="ar" dir="rtl">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>كويز شخصيات نسائية</title>
    <link
      href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;700&display=swap"
      rel="stylesheet"
    />
    <style>
      :root {
        --primary-color: #6a4c93;
        --secondary-color: #8a5a44;
        --accent-color: #f8b195;
        --light-color: #f9f9f9;
        --dark-color: #333;
        --correct-color: #4caf50;
        --wrong-color: #f44336;
        --unanswered-color: #e0e0e0;
        --answered-color: #6a4c93;
        --current-color: #f8b195;
        --warning-color: #ff9800;
      }

      * {
        box-sizing: border-box;
        margin: 0;
        padding: 0;
      }

      body {
        font-family: "Tajawal", Arial, sans-serif;
        background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
        color: var(--dark-color);
        line-height: 1.6;
        min-height: 100vh;
        padding: 20px;
      }

      .container {
        max-width: 1200px;
        margin: 0 auto;
        display: flex;
        flex-direction: column;
        gap: 20px;
      }

      .quiz-header {
        text-align: center;
        margin-bottom: 20px;
        padding: 20px;
        background: white;
        border-radius: 10px;
        box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        position: relative;
      }

      .quiz-header h1 {
        color: var(--primary-color);
        margin-bottom: 10px;
        font-size: 1.8rem;
      }

      .timer-container {
        display: flex;
        justify-content: center;
        align-items: center;
        margin-top: 10px;
        font-weight: bold;
        font-size: 1.2rem;
      }

      .timer {
        padding: 5px 10px;
        background-color: var(--primary-color);
        color: white;
        border-radius: 5px;
        margin-right: 8px;
      }

      .timer.warning {
        background-color: var(--warning-color);
        animation: pulse 1s infinite;
      }

      .timer.danger {
        background-color: var(--wrong-color);
        animation: pulse 0.5s infinite;
      }

      @keyframes pulse {
        0% {
          opacity: 1;
        }
        50% {
          opacity: 0.7;
        }
        100% {
          opacity: 1;
        }
      }

      .quiz-wrapper {
        display: flex;
        flex-direction: column;
        gap: 20px;
      }

      @media (min-width: 992px) {
        .quiz-wrapper {
          flex-direction: row;
        }
      }

      .questions-nav {
        background: white;
        border-radius: 10px;
        padding: 15px;
        box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        order: 2;
      }

      @media (min-width: 992px) {
        .questions-nav {
          width: 250px;
          order: 1;
          position: sticky;
          top: 20px;
          align-self: flex-start;
        }
      }

      .nav-title {
        font-weight: bold;
        margin-bottom: 15px;
        color: var(--primary-color);
        text-align: center;
        font-size: 1.2rem;
      }

      .question-numbers {
        display: grid;
        grid-template-columns: repeat(5, 1fr);
        gap: 10px;
      }

      .question-number {
        width: 40px;
        height: 40px;
        display: flex;
        align-items: center;
        justify-content: center;
        background: var(--unanswered-color);
        border-radius: 50%;
        cursor: pointer;
        transition: all 0.3s;
        font-weight: bold;
        color: white;
        border: 2px solid transparent;
      }

      .question-number:hover {
        transform: scale(1.05);
      }

      .question-number.answered {
        background: var(--answered-color);
      }

      .question-number.current {
        border: 3px solid var(--current-color);
        transform: scale(1.1);
      }

      .quiz-content {
        flex: 1;
        background: white;
        border-radius: 10px;
        padding: 25px;
        box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        order: 1;
      }

      @media (min-width: 992px) {
        .quiz-content {
          order: 2;
        }
      }

      .question-container {
        display: none;
      }

      .question-container.active {
        display: block;
        animation: fadeIn 0.5s;
      }

      .question {
        margin-bottom: 25px;
        font-size: 1.2rem;
        font-weight: bold;
        color: var(--primary-color);
        line-height: 1.5;
      }

      .options {
        margin-top: 20px;
        display: grid;
        grid-template-columns: 1fr;
        gap: 12px;
      }

      @media (min-width: 768px) {
        .options {
          grid-template-columns: 1fr 1fr;
        }
      }

      .option {
        display: flex;
        align-items: center;
        padding: 15px;
        background: #f9f9f9;
        border-radius: 8px;
        cursor: pointer;
        transition: all 0.2s;
        border: 2px solid #e0e0e0;
      }

      .option:hover {
        background: #f0f0f0;
        border-color: var(--primary-color);
      }

      .option input[type="radio"] {
        margin-left: 15px;
        width: 18px;
        height: 18px;
        cursor: pointer;
        accent-color: var(--primary-color);
      }

      .option label {
        flex: 1;
        cursor: pointer;
        margin-right: 10px;
      }

      .option.correct {
        background: rgba(76, 175, 80, 0.1);
        border-color: var(--correct-color);
      }

      .option.incorrect {
        background: rgba(244, 67, 54, 0.1);
        border-color: var(--wrong-color);
      }

      .option.correct-answer {
        background: rgba(76, 175, 80, 0.2);
        border-color: var(--correct-color);
      }

      .navigation-buttons {
        display: flex;
        justify-content: space-between;
        margin-top: 30px;
        gap: 15px;
      }

      .nav-btn {
        padding: 12px 25px;
        background: var(--primary-color);
        color: white;
        border: none;
        border-radius: 8px;
        font-size: 1rem;
        cursor: pointer;
        transition: all 0.3s;
        display: flex;
        align-items: center;
        gap: 8px;
        font-family: "Tajawal", sans-serif;
      }

      .nav-btn:hover {
        background: var(--secondary-color);
        transform: translateY(-2px);
      }

      .nav-btn:disabled {
        background: #cccccc;
        cursor: not-allowed;
        transform: none;
      }

      .nav-btn.finish-btn {
        background: var(--accent-color);
        color: var(--dark-color);
      }

      .nav-btn.finish-btn:hover {
        background: #e69d7a;
      }

      .progress-container {
        width: 100%;
        background: #e0e0e0;
        border-radius: 10px;
        height: 10px;
        margin-bottom: 20px;
        overflow: hidden;
      }

      .progress-bar {
        height: 100%;
        background: linear-gradient(
          to right,
          var(--primary-color),
          var(--secondary-color)
        );
        border-radius: 10px;
        width: 0%;
        transition: width 0.5s ease;
      }

      .progress-text {
        text-align: center;
        margin-bottom: 10px;
        font-weight: bold;
        color: var(--primary-color);
      }

      .result-modal {
        display: none;
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: rgba(0, 0, 0, 0.5);
        z-index: 1000;
        justify-content: center;
        align-items: center;
        backdrop-filter: blur(5px);
      }

      .result-content {
        background: white;
        border-radius: 15px;
        padding: 30px;
        width: 90%;
        max-width: 500px;
        text-align: center;
        box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        animation: modalFadeIn 0.3s;
      }

      .result-title {
        color: var(--primary-color);
        margin-bottom: 20px;
        font-size: 1.5rem;
      }

      .circle-progress {
        position: relative;
        width: 150px;
        height: 150px;
        margin: 0 auto 20px;
      }

      .circle-progress svg {
        width: 100%;
        height: 100%;
      }

      .circle-progress circle {
        fill: none;
        stroke-width: 10;
        stroke-linecap: round;
        transform: rotate(-90deg);
        transform-origin: 50% 50%;
      }

      .circle-bg {
        stroke: #f0f0f0;
      }

      .circle-fill {
        stroke: var(--primary-color);
        stroke-dasharray: 440;
        stroke-dashoffset: 440;
        transition: stroke-dashoffset 1s ease-in-out;
      }

      .progress-text-result {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        font-size: 2rem;
        font-weight: bold;
        color: var(--primary-color);
      }

      .score-text {
        margin-bottom: 20px;
        font-size: 1.2rem;
      }
      
      .timeout-message {
        color: var(--wrong-color);
        font-weight: bold;
        margin-bottom: 15px;
        display: none;
      }

      .result-actions {
        margin-top: 25px;
        display: flex;
        justify-content: center;
        gap: 15px;
        flex-wrap: wrap;
      }

      .action-btn {
        padding: 10px 20px;
        border: none;
        border-radius: 8px;
        font-size: 1rem;
        cursor: pointer;
        transition: all 0.3s;
        font-family: "Tajawal", sans-serif;
      }

      .review-btn {
        background: var(--secondary-color);
        color: white;
      }

      .review-btn:hover {
        background: #7a4a34;
        transform: translateY(-2px);
      }

      .close-btn {
        background: var(--primary-color);
        color: white;
      }

      .close-btn:hover {
        background: #5a3c7a;
        transform: translateY(-2px);
      }

      @keyframes fadeIn {
        from {
          opacity: 0;
          transform: translateY(20px);
        }
        to {
          opacity: 1;
          transform: translateY(0);
        }
      }

      @keyframes modalFadeIn {
        from {
          opacity: 0;
          transform: scale(0.8);
        }
        to {
          opacity: 1;
          transform: scale(1);
        }
      }

      @media (max-width: 768px) {
        .question-numbers {
          grid-template-columns: repeat(4, 1fr);
        }

        .question {
          font-size: 1.1rem;
        }

        .nav-btn {
          padding: 10px 15px;
          font-size: 0.9rem;
        }
      }

      @media (max-width: 480px) {
        .question-numbers {
          grid-template-columns: repeat(3, 1fr);
        }

        .quiz-header h1 {
          font-size: 1.5rem;
        }

        .navigation-buttons {
          flex-direction: column;
        }

        .nav-btn {
          width: 100%;
          justify-content: center;
        }
      }
    </style>
  </head>
  <body>
    <div class="container">
      <div class="quiz-header">
        <h1>كويز شخصيات نسائية</h1>
        <div class="timer-container">
          <span>الوقت المتبقي:</span>
          <span class="timer" id="timer">07:00</span>
        </div>
      </div>

      <div class="quiz-wrapper">
        <div class="quiz-content">
          <div class="progress-text" id="progress-text">السؤال 1 من 20</div>
          <div class="progress-container">
            <div class="progress-bar" id="progress-bar"></div>
          </div>

          <form id="quizForm">
            <div class="question-container active" id="q1">
              <div class="question">
                1. أول امرأة مصرية تتقلد منصب وزاري في تاريخ مصر؟
              </div>
              <div class="options">
                <div class="option">
                  <input
                    type="radio"
                    id="q1-option1"
                    name="q1"
                    value="درية شفيق"
                  />
                  <label for="q1-option1">درية شفيق</label>
                </div>
                <div class="option">
                  <input
                    type="radio"
                    id="q1-option2"
                    name="q1"
                    value="حكمت أبو زيد"
                  />
                  <label for="q1-option2">حكمت أبو زيد</label>
                </div>
                <div class="option">
                  <input
                    type="radio"
                    id="q1-option3"
                    name="q1"
                    value="هدى شعراوي"
                  />
                  <label for="q1-option3">هدى شعراوي</label>
                </div>
                <div class="option">
                  <input
                    type="radio"
                    id="q1-option4"
                    name="q1"
                    value="نبوية موسى"
                  />
                  <label for="q1-option4">نبوية موسى</label>
                </div>
              </div>
            </div>

            <div class="question-container" id="q2">
              <div class="question">
                2. قادت جيشًا وحكمت مصر كفرعون وكانت واحدة من أشهر النساء في
                التاريخ القديم؟
              </div>
              <div class="options">
                <div class="option">
                  <input
                    type="radio"
                    id="q2-option1"
                    name="q2"
                    value="كليوباترا"
                  />
                  <label for="q2-option1">كليوباترا</label>
                </div>
                <div class="option">
                  <input
                    type="radio"
                    id="q2-option2"
                    name="q2"
                    value="نفرتيتي"
                  />
                  <label for="q2-option2">نفرتيتي</label>
                </div>
                <div class="option">
                  <input
                    type="radio"
                    id="q2-option3"
                    name="q2"
                    value="حتشبسوت"
                  />
                  <label for="q2-option3">حتشبسوت</label>
                </div>
                <div class="option">
                  <input type="radio" id="q2-option4" name="q2" value="تيي" />
                  <label for="q2-option4">تيي</label>
                </div>
              </div>
            </div>

            <div class="question-container" id="q3">
              <div class="question">
                3. ناشطة نسوية نظمت أول مظاهرة نسائية ضد الاحتلال البريطاني سنة
                1919؟
              </div>
              <div class="options">
                <div class="option">
                  <input
                    type="radio"
                    id="q3-option1"
                    name="q3"
                    value="صفية زغلول"
                  />
                  <label for="q3-option1">صفية زغلول</label>
                </div>
                <div class="option">
                  <input
                    type="radio"
                    id="q3-option2"
                    name="q3"
                    value="هدى شعراوي"
                  />
                  <label for="q3-option2">هدى شعراوي</label>
                </div>
                <div class="option">
                  <input
                    type="radio"
                    id="q3-option3"
                    name="q3"
                    value="درية شفيق"
                  />
                  <label for="q3-option3">درية شفيق</label>
                </div>
                <div class="option">
                  <input
                    type="radio"
                    id="q3-option4"
                    name="q3"
                    value="جميلة بوحيرد"
                  />
                  <label for="q3-option4">جميلة بوحيرد</label>
                </div>
              </div>
            </div>

            <div class="question-container" id="q4">
              <div class="question">
                4. واحدة من أوائل الفنانات المصريات في السينما الصامتة؟
              </div>
              <div class="options">
                <div class="option">
                  <input
                    type="radio"
                    id="q4-option1"
                    name="q4"
                    value="آسيا داغر"
                  />
                  <label for="q4-option1">آسيا داغر</label>
                </div>
                <div class="option">
                  <input
                    type="radio"
                    id="q4-option2"
                    name="q4"
                    value="ليلى مراد"
                  />
                  <label for="q4-option2">ليلى مراد</label>
                </div>
                <div class="option">
                  <input
                    type="radio"
                    id="q4-option3"
                    name="q4"
                    value="أم كلثوم"
                  />
                  <label for="q4-option3">أم كلثوم</label>
                </div>
                <div class="option">
                  <input
                    type="radio"
                    id="q4-option4"
                    name="q4"
                    value="تحية كاريوكا"
                  />
                  <label for="q4-option4">تحية كاريوكا</label>
                </div>
              </div>
            </div>
            <div class="question-container" id="q5">
              <div class="question">5. أول قاضية في مصر والعالم العربي؟</div>
              <div class="options">
                <div class="option">
                  <input
                    type="radio"
                    id="q5-option1"
                    name="q5"
                    value="تهاني الجبالي"
                  />
                  <label for="q5-option1">تهاني الجبالي</label>
                </div>
                <div class="option">
                  <input
                    type="radio"
                    id="q5-option2"
                    name="q5"
                    value="فاطمة البلتاجي"
                  />
                  <label for="q5-option2">فاطمة البلتاجي</label>
                </div>
                <div class="option">
                  <input
                    type="radio"
                    id="q5-option3"
                    name="q5"
                    value="ليلى مراد"
                  />
                  <label for="q5-option3">ليلى مراد</label>
                </div>
                <div class="option">
                  <input
                    type="radio"
                    id="q5-option4"
                    name="q5"
                    value="جميلة إسماعيل"
                  />
                  <label for="q5-option4">جميلة إسماعيل</label>
                </div>
              </div>
            </div>

            <div class="question-container" id="q6">
              <div class="question">6. سياسية مصرية ورئيسة حزب الدستور؟</div>
              <div class="options">
                <div class="option">
                  <input
                    type="radio"
                    id="q6-option1"
                    name="q6"
                    value="بثينة كامل"
                  />
                  <label for="q6-option1">بثينة كامل</label>
                </div>
                <div class="option">
                  <input
                    type="radio"
                    id="q6-option2"
                    name="q6"
                    value="جميلة إسماعيل"
                  />
                  <label for="q6-option2">جميلة إسماعيل</label>
                </div>
                <div class="option">
                  <input
                    type="radio"
                    id="q6-option3"
                    name="q6"
                    value="لميس الحديدي"
                  />
                  <label for="q6-option3">لميس الحديدي</label>
                </div>
                <div class="option">
                  <input
                    type="radio"
                    id="q6-option4"
                    name="q6"
                    value="منى الشاذلي"
                  />
                  <label for="q6-option4">منى الشاذلي</label>
                </div>
              </div>
            </div>

            <div class="question-container" id="q7">
              <div class="question">
                7. آخر فرعون من الأسرة البطلمية وكان لها علاقة سياسية مع يوليوس
                قيصر؟
              </div>
              <div class="options">
                <div class="option">
                  <input
                    type="radio"
                    id="q7-option1"
                    name="q7"
                    value="حتشبسوت"
                  />
                  <label for="q7-option1">حتشبسوت</label>
                </div>
                <div class="option">
                  <input
                    type="radio"
                    id="q7-option2"
                    name="q7"
                    value="كليوباترا السابعة"
                  />
                  <label for="q7-option2">كليوباترا السابعة</label>
                </div>
                <div class="option">
                  <input
                    type="radio"
                    id="q7-option3"
                    name="q7"
                    value="نفرتاري"
                  />
                  <label for="q7-option3">نفرتاري</label>
                </div>
                <div class="option">
                  <input type="radio" id="q7-option4" name="q7" value="تيي" />
                  <label for="q7-option4">تيي</label>
                </div>
              </div>
            </div>

            <div class="question-container" id="q8">
              <div class="question">
                8. أول مذيعة نشرة أخبار في التليفزيون المصري؟
              </div>
              <div class="options">
                <div class="option">
                  <input
                    type="radio"
                    id="q8-option1"
                    name="q8"
                    value="صفاء حجازي"
                  />
                  <label for="q8-option1">صفاء حجازي</label>
                </div>
                <div class="option">
                  <input
                    type="radio"
                    id="q8-option2"
                    name="q8"
                    value="آمال فهمي"
                  />
                  <label for="q8-option2">آمال فهمي</label>
                </div>
                <div class="option">
                  <input
                    type="radio"
                    id="q8-option3"
                    name="q8"
                    value="منى الشاذلي"
                  />
                  <label for="q8-option3">منى الشاذلي</label>
                </div>
                <div class="option">
                  <input
                    type="radio"
                    id="q8-option4"
                    name="q8"
                    value="هالة سرحان"
                  />
                  <label for="q8-option4">هالة سرحان</label>
                </div>
              </div>
            </div>

            <div class="question-container" id="q9">
              <div class="question">
                9. فنانة مصرية لقبت بـ'سيدة الشاشة العربية'؟
              </div>
              <div class="options">
                <div class="option">
                  <input
                    type="radio"
                    id="q9-option1"
                    name="q9"
                    value="شادية"
                  />
                  <label for="q9-option1">شادية</label>
                </div>
                <div class="option">
                  <input
                    type="radio"
                    id="q9-option2"
                    name="q9"
                    value="نجلاء فتحي"
                  />
                  <label for="q9-option2">نجلاء فتحي</label>
                </div>
                <div class="option">
                  <input
                    type="radio"
                    id="q9-option3"
                    name="q9"
                    value="فاتن حمامة"
                  />
                  <label for="q9-option3">فاتن حمامة</label>
                </div>
                <div class="option">
                  <input
                    type="radio"
                    id="q9-option4"
                    name="q9"
                    value="ماجدة الخطيب"
                  />
                  <label for="q9-option4">ماجدة الخطيب</label>
                </div>
              </div>
            </div>

            <div class="question-container" id="q10">
              <div class="question">
                10. زوجة الرئيس الراحل أنور السادات ونا
