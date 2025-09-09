<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HACKERS IELTS Listening - Chapter 1 (Full)</title>
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- Thư viện để tạo file Excel -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/xlsx/0.18.5/xlsx.full.min.js"></script>

    <style>
        body { font-family: 'Inter', sans-serif; scroll-behavior: smooth; }
        .transcript { background-color: #f7fafc; border: 1px solid #e2e8f0; padding: 1rem; margin-top: 1rem; border-radius: 0.375rem; line-height: 1.6; }
        .highlight { background-color: #fefcbf; font-weight: 600; }
        .transcript h4 { font-size: 1.125rem; font-weight: bold; margin-bottom: 0.5rem; }
        .correct-answer-highlight { background-color: #c6f6d5 !important; border: 2px solid #38a169; padding: 0.25rem 0.5rem; border-radius: 0.375rem; display: inline-block; }
        .incorrect-user-answer { text-decoration: line-through; color: #e53e3e; }
        .hidden { display: none; }
        .result-correct { color: #2d6a4f; }
        .result-incorrect { color: #c53030; }

        /* CSS cho phần template PDF (ẩn) - không còn sử dụng */
    </style>
</head>
<body class="bg-gray-100 text-gray-800">
    <div class="container mx-auto p-4 md:p-8">
        <header class="text-center mb-8">
            <h1 class="text-3xl md:text-4xl font-bold text-blue-700">HACKERS IELTS Listening</h1>
            <p class="text-lg text-gray-600">Bài tập tương tác - Chapter 1: Multiple Choice</p>
        </header>

        <main id="main-content">
            <section class="mb-8">
                <h2 class="text-2xl font-semibold border-b-2 border-green-500 pb-2 mb-4">Hackers Practice</h2>
                <div id="practice-container-hp"></div>

                <h2 class="text-2xl font-semibold border-b-2 border-blue-500 pb-2 mb-4 mt-12">Hackers Test</h2>
                <div id="practice-container-ht"></div>
            </section>
            
            <!-- Khu vực Nộp bài và Xuất file duy nhất -->
            <section id="control-panel" class="mt-12 p-6 bg-white rounded-lg shadow-md border-t-4 border-blue-700 sticky bottom-0">
                <h2 class="text-2xl font-semibold mb-4">Hoàn Thành & Chấm Điểm</h2>
                <p class="text-gray-600 mb-4">Sau khi hoàn thành các bài tập, hãy nhập tên và nhấn nút bên dưới để kiểm tra kết quả toàn bộ Chapter 1.</p>
                <div class="my-4">
                    <label for="global-name" class="block font-medium mb-1 text-lg">Tên của bạn:</label>
                    <input type="text" id="global-name" class="w-full md:w-1/2 p-2 border rounded-md" placeholder="Nhập tên của bạn...">
                </div>
                <button onclick="submitAllAnswers()" class="w-full md:w-auto px-6 py-3 bg-blue-700 text-white font-bold rounded-lg hover:bg-blue-800 transition-transform transform hover:scale-105 text-lg">
                    ✅ Chấm Toàn Bộ Bài & Xem Kết Quả
                </button>
            </section>
        </main>

        <!-- Khu vực hiển thị kết quả tổng hợp -->
        <div id="global-results-container" class="hidden"></div>
        
    <script>
        // --- DATA CHO TOÀN BỘ CHAPTER 1 ---
        const answerKey = {
            'ch1_hp1-4': { title: "Hackers Practice: Questions 1-4", keys: { 'ch1_q1': "A", 'ch1_q2': "B", 'ch1_q3': "C", 'ch1_q4': "A" } },
            'ch1_hp5-7': { title: "Hackers Practice: Questions 5-7", keys: { 'ch1_q5-7': ["A", "C", "F"] } },
            'ch1_hp8-11': { title: "Hackers Practice: Questions 8-11", keys: { 'ch1_q8': "B", 'ch1_q9': "C", 'ch1_q10': "A", 'ch1_q11': "B" } },
            'ch1_hp12-16': { title: "Hackers Practice: Questions 12-16", keys: { 'ch1_q12-13': ["B", "D"], 'ch1_q14': "B", 'ch1_q15': "A", 'ch1_q16': "B" } },
            'ch1_hp17-20': { title: "Hackers Practice: Questions 17-20", keys: { 'ch1_q17': "A", 'ch1_q18': "A", 'ch1_q19-20': ["A", "D"] } },
            'ch1_hp21-25': { title: "Hackers Practice: Questions 21-25", keys: { 'ch1_q21': "A", 'ch1_q22': "C", 'ch1_q23': "B", 'ch1_q24': "A", 'ch1_q25': "B" } },
            'ch1_ht1-10': { title: "Hackers Test: Section 2, Questions 1-10", keys: { 'ch1_tq1-2': ["C", "E"], 'ch1_tq3': "fast food", 'ch1_tq4': "local", 'ch1_tq5': "ground", 'ch1_tq6': "A", 'ch1_tq7': "C", 'ch1_tq8': "A", 'ch1_tq9': "A", 'ch1_tq10': "B" } },
            'ch1_ht11-20': { title: "Hackers Test: Section 3, Questions 11-20", keys: { 'ch1_tq11-12': ["A", "C"], 'ch1_tq13-14': ["A", "D"], 'ch1_tq15-16': ["B", "D"], 'ch1_tq17': "C", 'ch1_tq18': "C", 'ch1_tq19': "C", 'ch1_tq20': "A" } }
        };
        
        const fullContentData = {
            'ch1_hp1-4': { html: `<p class="mb-4">Choose the correct letter, A, B or C.</p><div class="space-y-4"><div><p><strong>1.</strong> Alex is mostly interested in seeing</p><div class="space-y-1 pl-4"><div><input type="radio" id="ch1_q1_a" name="ch1_q1" value="A"><label for="ch1_q1_a"> A. art galleries.</label></div><div><input type="radio" id="ch1_q1_b" name="ch1_q1" value="B"><label for="ch1_q1_b"> B. contemporary culture.</label></div><div><input type="radio" id="ch1_q1_c" name="ch1_q1" value="C"><label for="ch1_q1_c"> C. historical sites.</label></div></div></div><div><p><strong>2.</strong> The 'Top Spots' half-day tour begins at</p><div class="space-y-1 pl-4"><div><input type="radio" id="ch1_q2_a" name="ch1_q2" value="A"><label for="ch1_q2_a"> A. 7 am.</label></div><div><input type="radio" id="ch1_q2_b" name="ch1_q2" value="B"><label for="ch1_q2_b"> B. 9 am.</label></div><div><input type="radio" id="ch1_q2_c" name="ch1_q2" value="C"><label for="ch1_q2_c"> C. 2 pm.</label></div></div></div><div><p><strong>3.</strong> How much will Alex have to pay for his tour?</p><div class="space-y-1 pl-4"><div><input type="radio" id="ch1_q3_a" name="ch1_q3" value="A"><label for="ch1_q3_a"> A. $25</label></div><div><input type="radio" id="ch1_q3_b" name="ch1_q3" value="B"><label for="ch1_q3_b"> B. $45</label></div><div><input type="radio" id="ch1_q3_c" name="ch1_q3" value="C"><label for="ch1_q3_c"> C. $70</label></div></div></div><div><p><strong>4.</strong> What will the guide for the Thursday tour be doing at Central Station?</p><div class="space-y-1 pl-4"><div><input type="radio" id="ch1_q4_a" name="ch1_q4" value="A"><label for="ch1_q4_a"> A. displaying a company sign</label></div><div><input type="radio" id="ch1_q4_b" name="ch1_q4" value="B"><label for="ch1_q4_b"> B. distributing apparel to participants</label></div><div><input type="radio" id="ch1_q4_c" name="ch1_q4" value="C"><label for="ch1_q4_c"> C. collecting payments from participants</label></div></div></div></div>`, transcript: `<div class="transcript mt-6"><h4>Transcript</h4><p><strong>W:</strong> ...What in our city are you interested in seeing?<br><strong>M:</strong> Well, I am curious about both historical sites and contemporary culture. But I'm also interested in old architecture. So, <span class="highlight">I do want to tour some art galleries more than anything.</span><br><strong>M:</strong> ...What time does the half-day tour start?<br><strong>W:</strong> <span class="highlight">It’s from 9 am to 2 pm this Wednesday.</span><br><strong>M:</strong> ...I reckon the Thursday tour will suit me best. What is the cost for that tour?<br><strong>W:</strong> It's $70 per person. But we have a special this month. You get $25 off if you make at least two bookings.<br><strong>M:</strong> That seems reasonable. <span class="highlight">However, I’m the only person, so please book just one spot for me.</span><br><strong>W:</strong> ...Thank you, Alex. <span class="highlight">On the day of the tour, there will be a guide at Central Station to meet you. The guide will be holding a large sign</span> and wearing a T-shirt with Sunwave Tours printed on it.</p></div>`},
            'ch1_hp5-7': { html: `<p class="mb-4">Choose <strong>THREE</strong> letters, A-G.</p><p class="mb-2">Which <strong>THREE</strong> things does the speaker say travellers should make sure to do when making payments overseas?</p><div class="space-y-1"><div><input type="checkbox" id="ch1_q5-7_a" name="ch1_q5-7" value="A"><label for="ch1_q5-7_a"> A. take advantage of tax refunds</label></div><div><input type="checkbox" id="ch1_q5-7_b" name="ch1_q5-7" value="B"><label for="ch1_q5-7_b"> B. get the correct change</label></div><div><input type="checkbox" id="ch1_q5-7_c" name="ch1_q5-7" value="C"><label for="ch1_q5-7_c"> C. pay with money rather than cards</label></div><div><input type="checkbox" id="ch1_q5-7_d" name="ch1_q5-7" value="D"><label for="ch1_q5-7_d"> D. avoid counterfeit cash</label></div><div><input type="checkbox" id="ch1_q5-7_e" name="ch1_q5-7" value="E"><label for="ch1_q5-7_e"> E. pay credit card fees</label></div><div><input type="checkbox" id="ch1_q5-7_f" name="ch1_q5-7" value="F"><label for="ch1_q5-7_f"> F. get a good exchange rate</label></div><div><input type="checkbox" id="ch1_q5-7_g" name="ch1_q5-7" value="G"><label for="ch1_q5-7_g"> G. pay traveller taxes</label></div></div>`, transcript: `<div class="transcript mt-6"><h4>Transcript</h4><p>...So, my first point is about payment... pulling out a credit card... is not such a good idea when overseas... So, <span class="highlight">use cash if at all possible</span>.<br>And that brings me to my next word of advice: <span class="highlight">check the exchange rates offered for your currency before making payments</span>... it is better to exchange your money in a bank which ensures better rates...<br><span class="highlight">Also, it is always a good idea to get tax refunds for your purchases when possible, as it can save you a lot of money.</span></p></div>`},
            'ch1_hp8-11': { html: `<p class="mb-4">Choose the correct letter, A, B or C.</p><h4 class="font-semibold mb-2">Devils Tower National Monument</h4><div class="space-y-4"><div><p><strong>8.</strong> Guests can inquire about routes at the</p><div class="space-y-1 pl-4"><div><input type="radio" id="ch1_q8_a" name="ch1_q8" value="A"><label for="ch1_q8_a"> A. visitor centre.</label></div><div><input type="radio" id="ch1_q8_b" name="ch1_q8" value="B"><label for="ch1_q8_b"> B. climbing office.</label></div><div><input type="radio" id="ch1_q8_c" name="ch1_q8" value="C"><label for="ch1_q8_c"> C. gift shop.</label></div></div></div><div><p><strong>9.</strong> Devils Tower was made a national monument because of its importance to</p><div class="space-y-1 pl-4"><div><input type="radio" id="ch1_q9_a" name="ch1_q9" value="A"><label for="ch1_q9_a"> A. previous explorers.</label></div><div><input type="radio" id="ch1_q9_b" name="ch1_q9" value="B"><label for="ch1_q9_b"> B. rock climbers.</label></div><div><input type="radio" id="ch1_q9_c" name="ch1_q9" value="C"><label for="ch1_q9_c"> C. native people.</label></div></div></div><div><p><strong>10.</strong> According to the speaker, why was the formation called Devils Tower?</p><div class="space-y-1 pl-4"><div><input type="radio" id="ch1_q10_a" name="ch1_q10" value="A"><label for="ch1_q10_a"> A. Its name was misinterpreted.</label></div><div><input type="radio" id="ch1_q10_b" name="ch1_q10" value="B"><label for="ch1_q10_b"> B. Its summit is difficult to reach.</label></div><div><input type="radio" id="ch1_q10_c" name="ch1_q10" value="C"><label for="ch1_q10_c"> C. Its trails can be dangerous.</label></div></div></div><div><p><strong>11.</strong> Visitors are not allowed to</p><div class="space-y-1 pl-4"><div><input type="radio" id="ch1_q11_a" name="ch1_q11" value="A"><label for="ch1_q11_a"> A. bring food into the park.</label></div><div><input type="radio" id="ch1_q11_b" name="ch1_q11" value="B"><label for="ch1_q11_b"> B. give food to wildlife.</label></div><div><input type="radio" id="ch1_q11_c" name="ch1_q11" value="C"><label for="ch1_q11_c"> C. leave the marked trails.</label></div></div></div></div>`, transcript: `<div class="transcript mt-6"><h4>Transcript</h4><p><strong>Guide:</strong> ...there are lots of great routes for hiking and rock climbing here in the park. <span class="highlight">If you are interested, you can ask about those activities at our climbing office.</span><br>To local Native Americans, this is a significant site. <span class="highlight">Because of that and its striking beauty, Devils Tower was made an official national monument</span> over a century ago.<br>...So, how did the rock formation get its unusual name? ... His interpreter is said to have <span class="highlight">made an error translating the native language</span> and said the unusual formation was named Bad God's Tower.<br>...it is vital that you <span class="highlight">do not feed animals you may encounter in the park.</span></p></div>`},
            'ch1_hp12-16': { html: `<h4 class="font-semibold mb-2">Psychology Study Abroad Programme</h4><div class="question mb-6"><strong class="block mb-2">Questions 12-13:</strong> Choose <strong>TWO</strong> letters, A-E.<p class="mb-2">Which <strong>TWO</strong> aspects of the programme was Laura particularly positive about?</p><div class="space-y-1"><div><input type="checkbox" id="ch1_q12-13_a" name="ch1_q12-13" value="A"><label for="ch1_q12-13_a"> A. the application process</label></div><div><input type="checkbox" id="ch1_q12-13_b" name="ch1_q12-13" value="B"><label for="ch1_q12-13_b"> B. the quality of the lectures</label></div><div><input type="checkbox" id="ch1_q12-13_c" name="ch1_q12-13" value="C"><label for="ch1_q12-13_c"> C. the advice on her thesis</label></div><div><input type="checkbox" id="ch1_q12-13_d" name="ch1_q12-13" value="D"><label for="ch1_q12-13_d"> D. the expertise of the professors</label></div><div><input type="checkbox" id="ch1_q12-13_e" name="ch1_q12-13" value="E"><label for="ch1_q12-13_e"> E. the field trips</label></div></div></div><div class="question"><strong class="block mb-2">Questions 14-16:</strong> Choose the correct letter, A, B or C.<div class="space-y-4"><div><p><strong>14.</strong> Laura says that the psychometrics course</p><div class="space-y-1 pl-4"><div><input type="radio" id="ch1_q14_a" name="ch1_q14" value="A"><label for="ch1_q14_a"> A. involved difficult topics.</label></div><div><input type="radio" id="ch1_q14_b" name="ch1_q14" value="B"><label for="ch1_q14_b"> B. was not too complex.</label></div><div><input type="radio" id="ch1_q14_c" name="ch1_q14" value="C"><label for="ch1_q14_c"> C. was for advanced students.</label></div></div></div><div><p><strong>15.</strong> Why does Laura recommend the adult counselling course to John?</p><div class="space-y-1 pl-4"><div><input type="radio" id="ch1_q15_a" name="ch1_q15" value="A"><label for="ch1_q15_a"> A. It is the focus of John's study.</label></div><div><input type="radio" id="ch1_q15_b" name="ch1_q15" value="B"><label for="ch1_q15_b"> B. It is highly praised by the school.</label></div><div><input type="radio" id="ch1_q15_c" name="ch1_q15" value="C"><label for="ch1_q15_c"> C. It involves fewer assignments.</label></div></div></div><div><p><strong>16.</strong> How does the psychology course differ in Singapore compared to the UK?</p><div class="space-y-1 pl-4"><div><input type="radio" id="ch1_q16_a" name="ch1_q16" value="A"><label for="ch1_q16_a"> A. There is less data to learn.</label></div><div><input type="radio" id="ch1_q16_b" name="ch1_q16" value="B"><label for="ch1_q16_b"> B. The course is less theoretical.</label></div><div><input type="radio" id="ch1_q16_c" name="ch1_q16" value="C"><label for="ch1_q16_c"> C. They have to learn statistics.</label></div></div></div></div></div>`, transcript: `<div class="transcript mt-6"><h4>Transcript</h4><p><strong>John:</strong> ...And what did you think about the lectures there?<br><strong>Laura:</strong> <span class="highlight">They were excellent. I found all of them very informative and insightful.</span><br><strong>John:</strong> And the lecturers themselves?<br><strong>Laura:</strong> <span class="highlight">They are all experts in their areas. A few of them are even published authors.</span><br><strong>Laura:</strong> ...I was intimidated by the subject at first, but <span class="highlight">I didn't find it overly complicated as it was just an introductory course.</span><br><strong>Laura:</strong> <span class="highlight">I know that you're focusing your studies on counselling, so you should take the adult counselling course</span> that is offered as well.<br><strong>Laura:</strong> ...The type of psychology they teach is very similar to statistics...<span class="highlight">Far less of the theory and discussion we had in the UK</span>...</p></div>`},
            'ch1_hp17-20': { html: `<div class="question mb-6"><strong class="block mb-2">Questions 17-18:</strong> Choose the correct letter, A, B or C.<div class="space-y-4"><div><p><strong>17.</strong> Alice's biometric access system will</p><div class="space-y-1 pl-4"><div><input type="radio" id="ch1_q17_a" name="ch1_q17" value="A"><label for="ch1_q17_a"> A. use drivers' thumbprints to open car locks.</label></div><div><input type="radio" id="ch1_q17_b" name="ch1_q17" value="B"><label for="ch1_q17_b"> B. scan the driver's eyes to unlock the car.</label></div><div><input type="radio" id="ch1_q17_c" name="ch1_q17" value="C"><label for="ch1_q17_c"> C. turn on the ignition when someone sits in the car.</label></div></div></div><div><p><strong>18.</strong> The sponsorship from the university includes</p><div class="space-y-1 pl-4"><div><input type="radio" id="ch1_q18_a" name="ch1_q18" value="A"><label for="ch1_q18_a"> A. financial support.</label></div><div><input type="radio" id="ch1_q18_b" name="ch1_q18" value="B"><label for="ch1_q18_b"> B. personal advising.</label></div><div><input type="radio" id="ch1_q18_c" name="ch1_q18" value="C"><label for="ch1_q18_c"> C. laboratory training.</label></div></div></div></div></div><div class="question"><strong class="block mb-2">Questions 19-20:</strong> Choose <strong>TWO</strong> letters, A-E.<p class="mb-2">Which <strong>TWO</strong> characteristics of the proposal have specific requirements?</p><div class="space-y-1"><div><input type="checkbox" id="ch1_q19-20_a" name="ch1_q19-20" value="A"><label for="ch1_q19-20_a"> A. length</label></div><div><input type="checkbox" id="ch1_q19-20_b" name="ch1_q19-20" value="B"><label for="ch1_q19-20_b"> B. punctuation</label></div><div><input type="checkbox" id="ch1_q19-20_c" name="ch1_q19-20" value="C"><label for="ch1_q19-20_c"> C. file format</label></div><div><input type="checkbox" id="ch1_q19-20_d" name="ch1_q19-20" value="D"><label for="ch1_q19-20_d"> D. graphics</label></div><div><input type="checkbox" id="ch1_q19-20_e" name="ch1_q19-20" value="E"><label for="ch1_q19-20_e"> E. references</label></div></div></div>`, transcript: `<div class="transcript mt-6"><h4>Transcript</h4><p><strong>Alice:</strong> ...<span class="highlight">Drivers would place a thumb on the outdoor scanner to unlock the vehicle</span>...<br><strong>Professor:</strong> Oh, there actually is a sponsorship from the university... <span class="highlight">The cost of $200 for entering the competition would be lifted.</span> And of course, you'd be able to use materials for the project at our lab facilities...<br><strong>Professor:</strong> You'll first need to submit a proposal, <span class="highlight">no longer than one page</span>... The proposal <span class="highlight">must include a rough design or sketch of your idea</span>. Otherwise, the Dean won't accept it.</p></div>`},
            'ch1_hp21-25': { html: `<p class="mb-4">Choose the correct letter, A, B or C.</p><div class="space-y-4"><div><p><strong>21.</strong> One result of high sugar consumption is that</p><div class="space-y-1 pl-4"><div><input type="radio" id="ch1_q21_a" name="ch1_q21" value="A"><label for="ch1_q21_a"> A. it can cause diabetes.</label></div><div><input type="radio" id="ch1_q21_b" name="ch1_q21" value="B"><label for="ch1_q21_b"> B. it can lead to other more serious addictions.</label></div><div><input type="radio" id="ch1_q21_c" name="ch1_q21" value="C"><label for="ch1_q21_c"> C. it is a direct cause for increases in heart rates.</label></div></div></div><div><p><strong>22.</strong> Why is honey a good alternative to refined sugar?</p><div class="space-y-1 pl-4"><div><input type="radio" id="ch1_q22_a" name="ch1_q22" value="A"><label for="ch1_q22_a"> A. It tastes the same in drinks.</label></div><div><input type="radio" id="ch1_q22_b" name="ch1_q22" value="B"><label for="ch1_q22_b"> B. It has fewer calories than sugar.</label></div><div><input type="radio" id="ch1_q22_c" name="ch1_q22" value="C"><label for="ch1_q22_c"> C. It is more easily processed by the body.</label></div></div></div><div><p><strong>23.</strong> The speaker says people don't realise</p><div class="space-y-1 pl-4"><div><input type="radio" id="ch1_q23_a" name="ch1_q23" value="A"><label for="ch1_q23_a"> A. how much water should be consumed in a day.</label></div><div><input type="radio" id="ch1_q23_b" name="ch1_q23" value="B"><label for="ch1_q23_b"> B. how much sugar a soft drink contains.</label></div><div><input type="radio" id="ch1_q23_c" name="ch1_q23" value="C"><label for="ch1_q23_c"> C. how many vitamins are in herbal tea.</label></div></div></div><div><p><strong>24.</strong> Products which are said to be fat-free should be avoided because</p><div class="space-y-1 pl-4"><div><input type="radio" id="ch1_q24_a" name="ch1_q24" value="A"><label for="ch1_q24_a"> A. they often contain extra sugar.</label></div><div><input type="radio" id="ch1_q24_b" name="ch1_q24" value="B"><label for="ch1_q24_b"> B. they do not list every ingredient.</label></div><div><input type="radio" id="ch1_q24_c" name="ch1_q24" value="C"><label for="ch1_q24_c"> C. they are made with sugar substitutes.</label></div></div></div><div><p><strong>25.</strong> According to the speaker, people should eat fruits and vegetables because</p><div class="space-y-1 pl-4"><div><input type="radio" id="ch1_q25_a" name="ch1_q25" value="A"><label for="ch1_q25_a"> A. they are a sugarless alternative.</label></div><div><input type="radio" id="ch1_q25_b" name="ch1_q25" value="B"><label for="ch1_q25_b"> B. they can satisfy the desire for sweetness.</label></div><div><input type="radio" id="ch1_q25_c" name="ch1_q25" value="C"><label for="ch1_q25_c"> C. they are a natural way to diet.</label></div></div></div></div>`, transcript: `<div class="transcript mt-6"><h4>Transcript</h4><p>...sugar... <span class="highlight">is a direct cause for diabetes</span>, the rates of which have never been higher.<br>Something like honey provides sweetness and is better for <span class="highlight">digestion</span> than refined sugar, as it allows nutrients to be <span class="highlight">absorbed more easily</span>.<br>People don't realise the <span class="highlight">enormous sugar content in a soft drink</span>...<br>Another thing to avoid is manufactured food products that are labelled fat-free. Often, to make up for the flavour from missing fat, <span class="highlight">sugar is added</span>.<br>...the best thing people can do is get the sweetness they want through natural sources... Get it through fruits and vegetables, above all... That's the best way to get <span class="highlight">the sweetness your appetite may want</span>.</p></div>`},
            'ch1_ht1-10': { html: `<div class="question mb-6"><strong class="block mb-2">Questions 1-2:</strong> Choose <strong>TWO</strong> letters, A-E.<p class="mb-2">Which TWO sports will have national matches played at the Brighton Sports Complex?</p><div class="space-y-1"><div><input type="checkbox" id="ch1_tq1-2_a" name="ch1_tq1-2" value="A"><label for="ch1_tq1-2_a"> A. football</label></div><div><input type="checkbox" id="ch1_tq1-2_b" name="ch1_tq1-2" value="B"><label for="ch1_tq1-2_b"> B. volleyball</label></div><div><input type="checkbox" id="ch1_tq1-2_c" name="ch1_tq1-2" value="C"><label for="ch1_tq1-2_c"> C. tennis</label></div><div><input type="checkbox" id="ch1_tq1-2_d" name="ch1_tq1-2" value="D"><label for="ch1_tq1-2_d"> D. swimming</label></div><div><input type="checkbox" id="ch1_tq1-2_e" name="ch1_tq1-2" value="E"><label for="ch1_tq1-2_e"> E. basketball</label></div></div></div><div class="question mb-6"><strong class="block mb-2">Questions 3-5:</strong> Complete the notes below. <em>Write NO MORE THAN TWO WORDS for each answer.</em><h4 class="font-semibold mb-2">Brighton Sports Complex: Dining Facilities</h4><ul class="list-disc pl-5 space-y-2"><li>promote healthy habits by not giving licences to <strong>3</strong> <input type="text" name="ch1_tq3" class="border-b-2 w-24"> establishments</li><li>ingredients are from <strong>4</strong> <input type="text" name="ch1_tq4" class="border-b-2 w-24"> areas</li><li>located on the <strong>5</strong> <input type="text" name="ch1_tq5" class="border-b-2 w-24"> floor</li></ul></div><div class="question"><strong class="block mb-2">Questions 6-10:</strong> Choose the correct letter, A, B, or C.<div class="space-y-4"><div><p><strong>6.</strong> To become a Brighton Sports Complex member, people should</p><div class="space-y-1 pl-4"><div><input type="radio" id="ch1_tq6_a" name="ch1_tq6" value="A"><label for="ch1_tq6_a"> A. complete a registration document.</label></div><div><input type="radio" id="ch1_tq6_b" name="ch1_tq6" value="B"><label for="ch1_tq6_b"> B. submit payment at a reception desk.</label></div><div><input type="radio" id="ch1_tq6_c" name="ch1_tq6" value="C"><label for="ch1_tq6_c"> C. present a credit card for deposit.</label></div></div></div><div><p><strong>7.</strong> People who wish to use the swimming pool at the complex must</p><div class="space-y-1 pl-4"><div><input type="radio" id="ch1_tq7_a" name="ch1_tq7" value="A"><label for="ch1_tq7_a"> A. leave their ID card at an office.</label></div><div><input type="radio" id="ch1_tq7_b" name="ch1_tq7" value="B"><label for="ch1_tq7_b"> B. check availability online.</label></div><div><input type="radio" id="ch1_tq7_c" name="ch1_tq7" value="C"><label for="ch1_tq7_c"> C. pay an additional yearly charge.</label></div></div></div><div><p><strong>8.</strong> What will all visitors be able to use for free?</p><div class="space-y-1 pl-4"><div><input type="radio" id="ch1_tq8_a" name="ch1_tq8" value="A"><label for="ch1_tq8_a"> A. a parking facility</label></div><div><input type="radio" id="ch1_tq8_b" name="ch1_tq8" value="B"><label for="ch1_tq8_b"> B. a personal locker</label></div><div><input type="radio" id="ch1_tq8_c" name="ch1_tq8" value="C"><label for="ch1_tq8_c"> C. the Wi-Fi</label></div></div></div><div><p><strong>9.</strong> Why will it be difficult to park on Millers Road this weekend?</p><div class="space-y-1 pl-4"><div><input type="radio" id="ch1_tq9_a" name="ch1_tq9" value="A"><label for="ch1_tq9_a"> A. A route has been closed for repairs.</label></div><div><input type="radio" id="ch1_tq9_b" name="ch1_tq9" value="B"><label for="ch1_tq9_b"> B. A car park will undergo maintenance.</label></div><div><input type="radio" id="ch1_tq9_c" name="ch1_tq9" value="C"><label for="ch1_tq9_c"> C. A private event is occurring in the complex.</label></div></div></div><div><p><strong>10.</strong> Attendees of the grand opening can receive</p><div class="space-y-1 pl-4"><div><input type="radio" id="ch1_tq10_a" name="ch1_tq10" value="A"><label for="ch1_tq10_a"> A. a paid parking pass.</label></div><div><input type="radio" id="ch1_tq10_b" name="ch1_tq10" value="B"><label for="ch1_tq10_b"> B. apparel for free.</label></div><div><input type="radio" id="ch1_tq10_c" name="ch1_tq10" value="C"><label for="ch1_tq10_c"> C. protective gear with a logo.</label></div></div></div></div></div>`, transcript: `<div class="transcript mt-6"><h4>Transcript</h4><p>...the Brighton Sports Complex will be the largest athletic stadium our city has ever seen, serving primarily as the venue for national <span class="highlight">tennis</span> matches... Not only does the complex house twenty-two tennis courts, but it also has two full-sized <span class="highlight">basketball</span> courts... we did not grant retail licenses to any <span class="highlight">fast food</span> restaurants... All the ingredients are from <span class="highlight">local</span> sources... establishments, which have been placed on the <span class="highlight">ground</span> floor... Citizens will need to stop by the reception desk and fill out a <span class="highlight">registration form</span> to become a member... There will be an additional 100 pound <span class="highlight">annual charge</span> to use this facility [the swimming pool]... We also have our own car park and will offer <span class="highlight">complementary parking</span> to all guests... Millers Road... will be <span class="highlight">blocked off this weekend for street repairs</span>... Join us at the grand opening this Saturday at 10 am and pick up a <span class="highlight">free T-shirt</span> with our facility's logo on the front.</p></div>`},
            'ch1_ht11-20': { html: `<div class="question mb-6"><strong class="block mb-2">Questions 11-12:</strong> Choose <strong>TWO</strong> letters, A-E.<p class="mb-2">Which TWO tasks have the students already completed?</p><div class="space-y-1"><div><input type="checkbox" id="ch1_tq11-12_a" name="ch1_tq11-12" value="A"><label for="ch1_tq11-12_a"> A. an outline for the assignment's structure</label></div><div><input type="checkbox" id="ch1_tq11-12_b" name="ch1_tq11-12" value="B"><label for="ch1_tq11-12_b"> B. the central part of the document</label></div><div><input type="checkbox" id="ch1_tq11-12_c" name="ch1_tq11-12" value="C"><label for="ch1_tq11-12_c"> C. the introduction to their report</label></div><div><input type="checkbox" id="ch1_tq11-12_d" name="ch1_tq11-12" value="D"><label for="ch1_tq11-12_d"> D. data gathering on globalised businesses</label></div><div><input type="checkbox" id="ch1_tq11-12_e" name="ch1_tq11-12" value="E"><label for="ch1_tq11-12_e"> E. a summary of their research methodology</label></div></div></div><div class="question mb-6"><strong class="block mb-2">Questions 13-14:</strong> Choose <strong>TWO</strong> letters, A-E.<p class="mb-2">Which <strong>TWO</strong> effects did Burger King's approach have when it launched restaurants in India?</p><div class="space-y-1"><div><input type="checkbox" id="ch1_tq13-14_a" name="ch1_tq13-14" value="A"><label for="ch1_tq13-14_a"> A. positive opinion of the brand around India</label></div><div><input type="checkbox" id="ch1_tq13-14_b" name="ch1_tq13-14" value="B"><label for="ch1_tq13-14_b"> B. stores spread throughout the region</label></div><div><input type="checkbox" id="ch1_tq13-14_c" name="ch1_tq13-14" value="C"><label for="ch1_tq13-14_c"> C. certain products put off consumers</label></div><div><input type="checkbox" id="ch1_tq13-14_d" name="ch1_tq13-14" value="D"><label for="ch1_tq13-14_d"> D. enhanced image in neighbouring countries</label></div><div><input type="checkbox" id="ch1_tq13-14_e" name="ch1_tq13-14" value="E"><label for="ch1_tq13-14_e"> E. its menu was seen as inappropriate</label></div></div></div><div class="question mb-6"><strong class="block mb-2">Questions 15-16:</strong> Choose <strong>TWO</strong> letters, A-E.<p class="mb-2">Which <strong>TWO</strong> elements of its ads did a Swedish vodka company change for each region?</p><div class="space-y-1"><div><input type="checkbox" id="ch1_tq15-16_a" name="ch1_tq15-16" value="A"><label for="ch1_tq15-16_a"> A. the type of graphics used</label></div><div><input type="checkbox" id="ch1_tq15-16_b" name="ch1_tq15-16" value="B"><label for="ch1_tq15-16_b"> B. the language of promotional material</label></div><div><input type="checkbox" id="ch1_tq15-16_c" name="ch1_tq15-16" value="C"><label for="ch1_tq15-16_c"> C. the size of printed advertisements</label></div><div><input type="checkbox" id="ch1_tq15-16_d" name="ch1_tq15-16" value="D"><label for="ch1_tq15-16_d"> D. the colours used in materials</label></div><div><input type="checkbox" id="ch1_tq15-16_e" name="ch1_tq15-16" value="E"><label for="ch1_tq15-16_e"> E. the brand names of products</label></div></div></div><div class="question"><strong class="block mb-2">Questions 17-20:</strong> Choose the correct letter, A, B or C.<div class="space-y-4"><div><p><strong>17.</strong> The advertisements shown for Calvin Klein caused problems because</p><div class="space-y-1 pl-4"><div><input type="radio" id="ch1_tq17_a" name="ch1_tq17" value="A"><label for="ch1_tq17_a"> A. they were considered not contemporary enough.</label></div><div><input type="radio" id="ch1_tq17_b" name="ch1_tq17" value="B"><label for="ch1_tq17_b"> B. they focused too much on younger consumers.</label></div><div><input type="radio" id="ch1_tq17_c" name="ch1_tq17" value="C"><label for="ch1_tq17_c"> C. they were deemed inappropriate by some consumers.</label></div></div></div><div><p><strong>18.</strong> A design feature that Calvin Klein introduced in its 2013 line was</p><div class="space-y-1 pl-4"><div><input type="radio" id="ch1_tq18_a" name="ch1_tq18" value="A"><label for="ch1_tq18_a"> A. new and brighter colours.</label></div><div><input type="radio" id="ch1_tq18_b" name="ch1_tq18" value="B"><label for="ch1_tq18_b"> B. clothes tailored to each age group.</label></div><div><input type="radio" id="ch1_tq18_c" name="ch1_tq18" value="C"><label for="ch1_tq18_c"> C. aspects of traditional outfits.</label></div></div></div><div><p><strong>19.</strong> How will the students include graphs in their report?</p><div class="space-y-1 pl-4"><div><input type="radio" id="ch1_tq19_a" name="ch1_tq19" value="A"><label for="ch1_tq19_a"> A. in an appendix at the end</label></div><div><input type="radio" id="ch1_tq19_b" name="ch1_tq19" value="B"><label for="ch1_tq19_b"> B. in a separate printed leaflet</label></div><div><input type="radio" id="ch1_tq19_c" name="ch1_tq19" value="C"><label for="ch1_tq19_c"> C. inserted throughout the text</label></div></div></div><div><p><strong>20.</strong> What will the students probably do next?</p><div class="space-y-1 pl-4"><div><input type="radio" id="ch1_tq20_a" name="ch1_tq20" value="A"><label for="ch1_tq20_a"> A. find images to use for their assignment</label></div><div><input type="radio" id="ch1_tq20_b" name="ch1_tq20" value="B"><label for="ch1_tq20_b"> B. go to a library to check out reference books</label></div><div><input type="radio" id="ch1_tq20_c" name="ch1_tq20" value="C"><label for="ch1_tq20_c"> C. create their own marketing plan</label></div></div></div></div></div>`, transcript: `<div class="transcript mt-6"><h4>Transcript</h4><p><strong>Matthew:</strong> <span class="highlight">We have finished our outline for the structure of the report, and I've just finished our introduction.</span><br><strong>Catherine:</strong> ...<span class="highlight">consumers' perceptions of Burger King's products improved there significantly.</span>...The company started to become more <span class="highlight">highly regarded in surrounding countries</span> in South East Asia too.<br><strong>Catherine:</strong> ...Absolute. This company decided to...<span class="highlight">incorporate cultural slang into each area's advertisements</span>...other elements in print ads, such as <span class="highlight">color, also varied</span> in different regions.<br><strong>Matthew:</strong> ...Calvin Klein had some trouble...and many consumers in foreign markets found them <span class="highlight">highly inappropriate</span>...the general consumer response there was that the clothes were too revealing.<br><strong>Matthew:</strong> ...the company turned things around by designing a new line in spring 2013 that <span class="highlight">featured elements of traditional clothing from various countries</span>...<br><strong>Professor:</strong> Ah, actually, <span class="highlight">you should mix the visual materials in with the text.</span><br><strong>Catherine:</strong> We're going to head to the library now to <span class="highlight">find some visual examples of globalized advertising.</span></p></div>`},
        };

        const userAnswers = {};

        function generateQuestionHTML(id, title, audioSrc, questionContentHTML) {
            return `
            <div id="container-${id}" class="practice-container bg-white p-6 rounded-lg shadow-md mb-6">
                <h3 class="text-xl font-bold mb-3">${title}</h3>
                <div class="part-1-doing">
                    <audio controls class="w-full mb-4" src="${audioSrc}" title="${title} Audio"></audio>
                    ${questionContentHTML}
                </div>
            </div>`;
        }
        
        document.addEventListener('DOMContentLoaded', () => {
            const hpContainer = document.getElementById('practice-container-hp');
            const htContainer = document.getElementById('practice-container-ht');
            
            // Đã sửa: Ánh xạ ID bài tập với tên tệp audio chính xác
            const audioMapping = {
                'ch1_hp1-4': 'CH1_HP1-4.mp3',
                'ch1_hp5-7': 'CH1_HP5-7.mp3',
                'ch1_hp8-11': 'CH1_HP8-11.mp3',
                'ch1_hp12-16': 'CH1_HP12-16.mp3',
                'ch1_hp17-20': 'CH1_HP17-20.mp3',
                'ch1_hp21-25': 'CH1_HP21-25.mp3',
                'ch1_ht1-10': 'CH1_HT1-10.mp3',
                'ch1_ht11-20': 'CH1_HT11-20.mp3'
            };

            for(const id in answerKey) {
                const data = fullContentData[id];
                const audioSrc = audioMapping[id];
                if(data && audioSrc) {
                    const html = generateQuestionHTML(id, answerKey[id].title, audioSrc, data.html);
                    if (id.includes('_hp')) {
                        hpContainer.innerHTML += html;
                    } else if (id.includes('_ht')) {
                        htContainer.innerHTML += html;
                    }
                }
            }
        });

        function submitAllAnswers() {
            const mainContent = document.getElementById('main-content');
            const resultsContainer = document.getElementById('global-results-container');
            let resultsHtml = '';
            let totalCorrect = 0;
            let totalQuestions = 0;

            for (const sectionId in answerKey) {
                const container = document.getElementById(`container-${sectionId}`);
                if (!container) continue;

                const sectionAnswers = answerKey[sectionId].keys;
                userAnswers[sectionId] = { results: {}, total: 0, correctCount: 0 };
                let questionCount = 0;
                let correctCount = 0;

                resultsHtml += `<div class="p-6 bg-white rounded-lg shadow-md mb-6">
                                <h3 class="text-xl font-bold mb-3">${answerKey[sectionId].title}</h3>`;

                for (const key in sectionAnswers) {
                    questionCount++;
                    const correctAnswer = sectionAnswers[key];
                    const questionNumText = key.split('_')[1].replace('tq','').replace('q','');
                    let isCorrect = false;
                    let userAnswerDisplay = '';

                    const inputs = container.querySelectorAll(`[name="${key}"]`);
                    if (inputs.length > 0 && inputs[0].type === 'checkbox') {
                        const userCheckboxes = Array.from(container.querySelectorAll(`input[name="${key}"]:checked`)).map(cb => cb.value);
                        userAnswerDisplay = userCheckboxes.length > 0 ? userCheckboxes.sort().join(', ') : 'Chưa trả lời';
                        if (userCheckboxes.length === correctAnswer.length && userCheckboxes.sort().every((val, index) => val === correctAnswer.sort()[index])) { isCorrect = true; }
                    } else if (inputs.length > 0 && inputs[0].type === 'radio') {
                        const userAnswerNode = container.querySelector(`input[name="${key}"]:checked`);
                        userAnswerDisplay = userAnswerNode ? userAnswerNode.value : 'Chưa trả lời';
                        if (userAnswerNode && userAnswerNode.value.toLowerCase() === correctAnswer.toLowerCase()) { isCorrect = true; }
                    } else {
                        const userInput = container.querySelector(`input[name="${key}"]`);
                        userAnswerDisplay = userInput.value.trim() || 'Chưa trả lời';
                        const correctOptions = String(correctAnswer).toLowerCase().split('/');
                        if (correctOptions.includes(userAnswerDisplay.toLowerCase())) { isCorrect = true; }
                    }
                    
                    userAnswers[sectionId].results[questionNumText] = { userAnswer: userAnswerDisplay, correctAnswer: Array.isArray(correctAnswer) ? correctAnswer.join(', ') : correctAnswer, isCorrect };

                    if(isCorrect) correctCount++;
                    
                    const resultClass = isCorrect ? 'result-correct' : 'result-incorrect';
                    resultsHtml += `<p class="p-2 my-1 border-b"><strong>Câu ${questionNumText}:</strong> <span class="${resultClass}">${userAnswerDisplay}</span> ${!isCorrect ? `(Đáp án đúng: ${userAnswers[sectionId].results[questionNumText].correctAnswer})` : '✔️'}</p>`;
                }
                userAnswers[sectionId].total = questionCount;
                userAnswers[sectionId].correctCount = correctCount;
                totalCorrect += correctCount;
                totalQuestions += questionCount;

                resultsHtml += `<p class="mt-4 font-bold">Điểm số: ${correctCount}/${questionCount}</p>`;
                resultsHtml += `<div id="details-${sectionId}" class="hidden">${fullContentData[sectionId].transcript}</div>`;
                resultsHtml += `<button onclick="toggleDetails('${sectionId}')" class="mt-2 px-3 py-1 bg-gray-200 rounded text-sm">Xem/Ẩn Transcript</button>`;
                resultsHtml += `</div>`;
            }

            mainContent.classList.add('hidden');
            
            const overallSummary = `
                <div class="p-8 bg-blue-100 border-blue-600 border-4 rounded-lg shadow-xl mb-8">
                    <h2 class="text-3xl font-bold text-blue-800 mb-4">Kết quả tổng hợp</h2>
                    <p class="text-2xl">Tổng điểm: <span class="font-bold text-blue-700">${totalCorrect} / ${totalQuestions}</span></p>
                    <div class="flex flex-wrap gap-4 mt-6">
                        <button id="export-button" onclick="exportAllToExcel()" class="px-6 py-3 bg-green-600 text-white font-bold rounded-lg hover:bg-green-700 transition-transform transform hover:scale-105 text-lg">📄 Xuất Toàn Bộ Đáp Án Ra Excel</button>
                        <button onclick="resetAll()" class="px-6 py-3 bg-red-600 text-white font-bold rounded-lg hover:bg-red-700 transition-transform transform hover:scale-105 text-lg">🔁 Làm Lại Toàn Bộ</button>
                    </div>
                </div>
            `;
            resultsContainer.innerHTML = overallSummary + resultsHtml;
            resultsContainer.classList.remove('hidden');
            window.scrollTo(0,0);
        }

        function toggleDetails(sectionId) {
            document.getElementById(`details-${sectionId}`).classList.toggle('hidden');
        }

        function resetAll() {
            document.getElementById('main-content').classList.remove('hidden');
            document.getElementById('global-results-container').innerHTML = '';
            document.getElementById('global-results-container').classList.add('hidden');
            document.querySelectorAll('input[type="radio"], input[type="checkbox"]').forEach(i => i.checked = false);
            document.querySelectorAll('input[type="text"]').forEach(i => i.value = '');
            Object.keys(userAnswers).forEach(key => delete userAnswers[key]);
        }
        
        async function exportAllToExcel() {
            const exportButton = document.getElementById('export-button');
            exportButton.disabled = true;
            exportButton.textContent = 'Đang xử lý...';

            const name = document.getElementById('global-name').value.trim() || "Anonymous";
            
            if (Object.keys(userAnswers).length === 0) {
                const dialog = document.createElement('div');
                dialog.className = 'fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center';
                dialog.innerHTML = `
                    <div class="bg-white p-6 rounded-lg shadow-lg">
                        <p class="mb-4">Không có dữ liệu để xuất.</p>
                        <button onclick="this.parentElement.parentElement.remove()" class="px-4 py-2 bg-blue-500 text-white rounded">Đóng</button>
                    </div>
                `;
                document.body.appendChild(dialog);
                exportButton.disabled = false;
                exportButton.textContent = '📄 Xuất Toàn Bộ Đáp Án Ra Excel';
                return;
            }
            
            try {
                const wb = XLSX.utils.book_new();

                for (const sectionId in userAnswers) {
                    if (userAnswers.hasOwnProperty(sectionId)) {
                        const sectionData = userAnswers[sectionId];
                        const sectionTitle = answerKey[sectionId].title;

                        const sheetData = [];
                        sheetData.push([sectionTitle]);
                        sheetData.push([`Tổng kết: ${sectionData.correctCount} / ${sectionData.total} câu đúng`]);
                        sheetData.push([]); 
                        sheetData.push(['Câu hỏi', 'Đáp án của bạn', 'Đáp án đúng', 'Kết quả']);

                        for (const [qNum, result] of Object.entries(sectionData.results)) {
                            sheetData.push([
                                qNum,
                                result.userAnswer,
                                result.correctAnswer,
                                result.isCorrect ? 'Đúng' : 'Sai'
                            ]);
                        }

                        const ws = XLSX.utils.aoa_to_sheet(sheetData);
                        ws['!cols'] = [
                            { wch: 10 }, { wch: 30 }, { wch: 30 }, { wch: 10 } 
                        ];
                        
                        let safeSheetName = sectionTitle.replace(/[:\\/?*[\]]/g, "").substring(0, 31);
                        XLSX.utils.book_append_sheet(wb, ws, safeSheetName);
                    }
                }

                XLSX.writeFile(wb, `KetQua_IELTS_Chapter1_${name.replace(/ /g, '_')}.xlsx`);

            } catch (error) {
                console.error("Lỗi khi tạo Excel:", error);
                 const dialog = document.createElement('div');
                dialog.className = 'fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center';
                dialog.innerHTML = `
                    <div class="bg-white p-6 rounded-lg shadow-lg">
                        <p class="mb-4">Đã xảy ra lỗi trong quá trình tạo file Excel. Vui lòng thử lại.</p>
                        <button onclick="this.parentElement.parentElement.remove()" class="px-4 py-2 bg-blue-500 text-white rounded">Đóng</button>
                    </div>
                `;
                document.body.appendChild(dialog);
            } finally {
                exportButton.disabled = false;
                exportButton.textContent = '📄 Xuất Toàn Bộ Đáp Án Ra Excel';
            }
        }
    </script>
</body>
</html>

