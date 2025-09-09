<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HACKERS IELTS Listening - Chapter 1 Practice</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        body {
            font-family: 'Inter', sans-serif;
        }
        .feedback p {
            margin: 0.25rem 0;
            padding: 0.5rem;
            border-radius: 0.25rem;
        }
        .correct {
            background-color: #e6fffa;
            color: #2d6a4f;
            border-left: 4px solid #38a169;
        }
        .incorrect {
            background-color: #fff5f5;
            color: #c53030;
            border-left: 4px solid #e53e3e;
        }
        .transcript {
            background-color: #f7fafc;
            border: 1px solid #e2e8f0;
            padding: 1rem;
            margin-top: 1rem;
            border-radius: 0.375rem;
            line-height: 1.6;
        }
        .highlight {
            background-color: #fefcbf; /* yellow-200 */
            font-weight: 600;
        }
        .transcript h4 {
            font-size: 1.125rem;
            font-weight: bold;
            margin-bottom: 0.5rem;
        }
    </style>
</head>
<body class="bg-gray-100 text-gray-800">
    <div class="container mx-auto p-4 md:p-8">
        <header class="text-center mb-8">
            <h1 class="text-3xl md:text-4xl font-bold text-blue-700">HACKERS IELTS Listening</h1>
            <p class="text-lg text-gray-600">Bài tập tương tác</p>
        </header>

        <main>
             <!-- Chapter 1 -->
            <section class="mb-8">
                <h2 class="text-2xl font-semibold border-b-2 border-green-500 pb-2 mb-4">Chapter 1: Multiple Choice</h2>

                <!-- Practice 1-4 -->
                <div class="question-group bg-white p-6 rounded-lg shadow-md mb-6">
                    <h3 class="text-xl font-bold mb-3">Hackers Practice: Questions 1-4</h3>
                     <audio controls class="w-full mb-4" src="CH1_HP1-4.mp3" title="Chapter 1 Practice 1-4 Audio"></audio>
                    <p class="mb-4">Choose the correct letter, A, B or C.</p>
                    <div class="space-y-4">
                        <div>
                            <p><strong>1.</strong> Alex is mostly interested in seeing</p>
                            <div class="space-y-1 pl-4">
                                <div><input type="radio" id="ch1_q1_a" name="ch1_q1" value="A"> <label for="ch1_q1_a">A. art galleries.</label></div>
                                <div><input type="radio" id="ch1_q1_b" name="ch1_q1" value="B"> <label for="ch1_q1_b">B. contemporary culture.</label></div>
                                <div><input type="radio" id="ch1_q1_c" name="ch1_q1" value="C"> <label for="ch1_q1_c">C. historical sites.</label></div>
                            </div>
                        </div>
                        <div>
                            <p><strong>2.</strong> The 'Top Spots' half-day tour begins at</p>
                            <div class="space-y-1 pl-4">
                                <div><input type="radio" id="ch1_q2_a" name="ch1_q2" value="A"> <label for="ch1_q2_a">A. 7 am.</label></div>
                                <div><input type="radio" id="ch1_q2_b" name="ch1_q2" value="B"> <label for="ch1_q2_b">B. 9 am.</label></div>
                                <div><input type="radio" id="ch1_q2_c" name="ch1_q2" value="C"> <label for="ch1_q2_c">C. 2 pm.</label></div>
                            </div>
                        </div>
                        <div>
                            <p><strong>3.</strong> How much will Alex have to pay for his tour?</p>
                             <div class="space-y-1 pl-4">
                                <div><input type="radio" id="ch1_q3_a" name="ch1_q3" value="A"> <label for="ch1_q3_a">A. $25</label></div>
                                <div><input type="radio" id="ch1_q3_b" name="ch1_q3" value="B"> <label for="ch1_q3_b">B. $45</label></div>
                                <div><input type="radio" id="ch1_q3_c" name="ch1_q3" value="C"> <label for="ch1_q3_c">C. $70</label></div>
                            </div>
                        </div>
                        <div>
                            <p><strong>4.</strong> What will the guide for the Thursday tour be doing at Central Station?</p>
                             <div class="space-y-1 pl-4">
                                <div><input type="radio" id="ch1_q4_a" name="ch1_q4" value="A"> <label for="ch1_q4_a">A. displaying a company sign</label></div>
                                <div><input type="radio" id="ch1_q4_b" name="ch1_q4" value="B"> <label for="ch1_q4_b">B. distributing apparel to participants</label></div>
                                <div><input type="radio" id="ch1_q4_c" name="ch1_q4" value="C"> <label for="ch1_q4_c">C. collecting payments from participants</label></div>
                            </div>
                        </div>
                    </div>
                    <div class="mt-4 space-x-2">
                        <button onclick="checkAnswers('ch1_1')" class="px-4 py-2 bg-blue-600 text-white rounded-lg hover:bg-blue-700 transition">Check Answers</button>
                        <button onclick="toggleTranscript('transcript-ch1-1')" class="px-4 py-2 bg-gray-600 text-white rounded-lg hover:bg-gray-700 transition">Show/Hide Transcript</button>
                    </div>
                    <div id="feedback-ch1_1" class="feedback mt-4 space-y-2"></div>
                    <div id="transcript-ch1-1" class="transcript hidden">
                        <h4>Transcript</h4>
                        <p><strong>W:</strong> ...What in our city are you interested in seeing?<br><strong>M:</strong> Well, I am curious about both historical sites and contemporary culture. But I'm also interested in old architecture. So, <span class="highlight">I do want to tour some art galleries more than anything.</span><br><strong>M:</strong> ...What time does the half-day tour start?<br><strong>W:</strong> <span class="highlight">It’s from 9 am to 2 pm this Wednesday.</span><br><strong>M:</strong> ...I reckon the Thursday tour will suit me best. What is the cost for that tour?<br><strong>W:</strong> It's $70 per person. But we have a special this month. <span class="highlight">You get $25 off if you make at least two bookings.</span><br><strong>M:</strong> That seems reasonable. However, I’m the only person, so please book just one spot for me.<br><strong>W:</strong> ...Thank you, Alex. <span class="highlight">On the day of the tour, there will be a guide at Central Station to meet you. The guide will be holding a large sign</span> and wearing a T-shirt with Sunwave Tours printed on it.</p>
                    </div>
                </div>

                <!-- Practice 5-7 -->
                <div class="question-group bg-white p-6 rounded-lg shadow-md mb-6">
                    <h3 class="text-xl font-bold mb-3">Hackers Practice: Questions 5-7</h3>
                    <audio controls class="w-full mb-4" src="CH1_HP5-7.mp3" title="Chapter 1 Practice 5-7 Audio"></audio>
                    <p class="mb-4">Choose <strong>THREE</strong> letters, A-G.</p>
                    <p class="mb-2">Which <strong>THREE</strong> things does the speaker say travellers should make sure to do when making payments overseas?</p>
                    <div class="space-y-1">
                        <div><input type="checkbox" name="ch1_q5_7" value="A"> <label>A. take advantage of tax refunds</label></div>
                        <div><input type="checkbox" name="ch1_q5_7" value="B"> <label>B. get the correct change</label></div>
                        <div><input type="checkbox" name="ch1_q5_7" value="C"> <label>C. pay with money rather than cards</label></div>
                        <div><input type="checkbox" name="ch1_q5_7" value="D"> <label>D. avoid counterfeit cash</label></div>
                        <div><input type="checkbox" name="ch1_q5_7" value="E"> <label>E. pay credit card fees</label></div>
                        <div><input type="checkbox" name="ch1_q5_7" value="F"> <label>F. get a good exchange rate</label></div>
                        <div><input type="checkbox" name="ch1_q5_7" value="G"> <label>G. pay traveller taxes</label></div>
                    </div>
                    <div class="mt-4 space-x-2">
                        <button onclick="checkAnswers('ch1_2')" class="px-4 py-2 bg-blue-600 text-white rounded-lg hover:bg-blue-700 transition">Check Answers</button>
                        <button onclick="toggleTranscript('transcript-ch1-2')" class="px-4 py-2 bg-gray-600 text-white rounded-lg hover:bg-gray-700 transition">Show/Hide Transcript</button>
                    </div>
                    <div id="feedback-ch1_2" class="feedback mt-4 space-y-2"></div>
                     <div id="transcript-ch1-2" class="transcript hidden">
                        <h4>Transcript</h4>
                        <p>...So, my first point is about payment... pulling out a credit card... is not such a good idea when overseas... So, <span class="highlight">use cash if at all possible</span>.<br>And that brings me to my next word of advice: <span class="highlight">check the exchange rates offered for your currency before making payments</span>... it is better to exchange your money in a bank which ensures better rates...<br><span class="highlight">Also, it is always a good idea to get tax refunds for your purchases when possible, as it can save you a lot of money.</span></p>
                    </div>
                </div>

                <!-- Practice 8-11 -->
                 <div class="question-group bg-white p-6 rounded-lg shadow-md mb-6">
                    <h3 class="text-xl font-bold mb-3">Hackers Practice: Questions 8-11</h3>
                     <audio controls class="w-full mb-4" src="CH1_HP8-11.mp3" title="Chapter 1 Practice 8-11 Audio"></audio>
                    <p class="mb-4">Choose the correct letter, A, B or C.</p>
                    <div class="space-y-4">
                        <div>
                            <p><strong>8.</strong> Guests can inquire about routes at the</p>
                            <div class="space-y-1 pl-4">
                                <div><input type="radio" name="ch1_q8" value="A"> <label>A. visitor centre.</label></div>
                                <div><input type="radio" name="ch1_q8" value="B"> <label>B. climbing office.</label></div>
                                <div><input type="radio" name="ch1_q8" value="C"> <label>C. gift shop.</label></div>
                            </div>
                        </div>
                        <div>
                            <p><strong>9.</strong> Devils Tower was made a national monument because of its importance to</p>
                            <div class="space-y-1 pl-4">
                                <div><input type="radio" name="ch1_q9" value="A"> <label>A. previous explorers.</label></div>
                                <div><input type="radio" name="ch1_q9" value="B"> <label>B. rock climbers.</label></div>
                                <div><input type="radio" name="ch1_q9" value="C"> <label>C. native people.</label></div>
                            </div>
                        </div>
                        <div>
                            <p><strong>10.</strong> According to the speaker, why was the formation called Devils Tower?</p>
                             <div class="space-y-1 pl-4">
                                <div><input type="radio" name="ch1_q10" value="A"> <label>A. Its name was misinterpreted.</label></div>
                                <div><input type="radio" name="ch1_q10" value="B"> <label>B. Its summit is difficult to reach.</label></div>
                                <div><input type="radio" name="ch1_q10" value="C"> <label>C. Its trails can be dangerous.</label></div>
                            </div>
                        </div>
                         <div>
                            <p><strong>11.</strong> Visitors are not allowed to</p>
                             <div class="space-y-1 pl-4">
                                <div><input type="radio" name="ch1_q11" value="A"> <label>A. bring food into the park.</label></div>
                                <div><input type="radio" name="ch1_q11" value="B"> <label>B. give food to wildlife.</label></div>
                                <div><input type="radio" name="ch1_q11" value="C"> <label>C. leave the marked trails.</label></div>
                            </div>
                        </div>
                    </div>
                    <div class="mt-4 space-x-2">
                        <button onclick="checkAnswers('ch1_3')" class="px-4 py-2 bg-blue-600 text-white rounded-lg hover:bg-blue-700 transition">Check Answers</button>
                        <button onclick="toggleTranscript('transcript-ch1-3')" class="px-4 py-2 bg-gray-600 text-white rounded-lg hover:bg-gray-700 transition">Show/Hide Transcript</button>
                    </div>
                    <div id="feedback-ch1_3" class="feedback mt-4 space-y-2"></div>
                     <div id="transcript-ch1-3" class="transcript hidden">
                        <h4>Transcript</h4>
                        <p><strong>Guide:</strong> ...there are lots of great routes for hiking and rock climbing here in the park. <span class="highlight">If you are interested, you can ask about those activities at our climbing office.</span><br>
                        To local Native Americans, this is a significant site. <span class="highlight">Because of that and its striking beauty, Devils Tower was made an official national monument</span> over a century ago.<br>
                        ...So, how did the rock formation get its unusual name? ... His interpreter is said to have <span class="highlight">made an error translating the native language</span> and said the unusual formation was named Bad God's Tower.<br>
                        ...it is vital that you <span class="highlight">do not feed animals you may encounter in the park.</span></p>
                    </div>
                </div>

                <!-- Practice 12-16 -->
                <div class="question-group bg-white p-6 rounded-lg shadow-md mb-6">
                    <h3 class="text-xl font-bold mb-3">Hackers Practice: Questions 12-16</h3>
                    <audio controls class="w-full mb-4" src="CH1_HP12-16.mp3" title="Chapter 1 Practice 12-16 Audio"></audio>
                    <div class="question mb-6">
                        <strong class="block mb-2">Questions 12-13:</strong> Choose <strong>TWO</strong> letters, A-E.
                        <p class="mb-2">Which <strong>TWO</strong> aspects of the programme was Laura particularly positive about?</p>
                        <div class="space-y-1">
                            <div><input type="checkbox" name="ch1_q12_13" value="A"> <label>A. the application process</label></div>
                            <div><input type="checkbox" name="ch1_q12_13" value="B"> <label>B. the quality of the lectures</label></div>
                            <div><input type="checkbox" name="ch1_q12_13" value="C"> <label>C. the advice on her thesis</label></div>
                            <div><input type="checkbox" name="ch1_q12_13" value="D"> <label>D. the expertise of the professors</label></div>
                            <div><input type="checkbox" name="ch1_q12_13" value="E"> <label>E. the field trips</label></div>
                        </div>
                    </div>
                     <div class="question">
                         <strong class="block mb-2">Questions 14-16:</strong> Choose the correct letter, A, B or C.
                        <div class="space-y-4">
                            <div>
                                <p><strong>14.</strong> Laura says that the psychometrics course</p>
                                <div class="space-y-1 pl-4">
                                  <div><input type="radio" name="ch1_q14" value="A"> <label>A. involved difficult topics.</label></div>
                                  <div><input type="radio" name="ch1_q14" value="B"> <label>B. was not too complex.</label></div>
                                  <div><input type="radio" name="ch1_q14" value="C"> <label>C. was for advanced students.</label></div>
                                </div>
                            </div>
                            <div>
                                <p><strong>15.</strong> Why does Laura recommend the adult counselling course to John?</p>
                                <div class="space-y-1 pl-4">
                                  <div><input type="radio" name="ch1_q15" value="A"> <label>A. It is the focus of John's study.</label></div>
                                  <div><input type="radio" name="ch1_q15" value="B"> <label>B. It is highly praised by the school.</label></div>
                                  <div><input type="radio" name="ch1_q15" value="C"> <label>C. It involves fewer assignments.</label></div>
                                </div>
                            </div>
                            <div>
                                <p><strong>16.</strong> How does the psychology course differ in Singapore compared to the UK?</p>
                                <div class="space-y-1 pl-4">
                                  <div><input type="radio" name="ch1_q16" value="A"> <label>A. There is less data to learn.</label></div>
                                  <div><input type="radio" name="ch1_q16" value="B"> <label>B. The course is less theoretical.</label></div>
                                  <div><input type="radio" name="ch1_q16" value="C"> <label>C. They have to learn statistics.</label></div>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="mt-4 space-x-2">
                        <button onclick="checkAnswers('ch1_4')" class="px-4 py-2 bg-blue-600 text-white rounded-lg hover:bg-blue-700 transition">Check Answers</button>
                        <button onclick="toggleTranscript('transcript-ch1-4')" class="px-4 py-2 bg-gray-600 text-white rounded-lg hover:bg-gray-700 transition">Show/Hide Transcript</button>
                    </div>
                    <div id="feedback-ch1_4" class="feedback mt-4 space-y-2"></div>
                     <div id="transcript-ch1-4" class="transcript hidden">
                        <h4>Transcript</h4>
                        <p><strong>John:</strong> ...And what did you think about the lectures there?<br><strong>Laura:</strong> <span class="highlight">They were excellent. I found all of them very informative and insightful.</span><br><strong>John:</strong> And the lecturers themselves?<br><strong>Laura:</strong> <span class="highlight">They are all experts in their areas. A few of them are even published authors.</span> Especially the professor of my psychometrics course...<br>
                        <strong>John:</strong> Oh, that sounds rather challenging.<br><strong>Laura:</strong> Not at all. I was intimidated by the subject at first, but <span class="highlight">I didn't find it overly complicated as it was just an introductory course.</span><br>
                        <strong>John:</strong> I see. Which other courses do you recommend?<br><strong>Laura:</strong> <span class="highlight">I know that you're focusing your studies on counselling, so you should take the adult counselling course</span> that is offered as well.<br>
                        <strong>John:</strong> Are there many differences between studying there and in the UK?<br><strong>Laura:</strong> Definitely. The type of psychology they teach is very similar to statistics. Lots of numbers, data and stuff like that. <span class="highlight">Far less of the theory and discussion we had in the UK</span>, and more science-based work.</p>
                    </div>
                </div>

                 <!-- Test Section 3, 11-20 -->
                 <div class="question-group bg-white p-6 rounded-lg shadow-md mb-6">
                    <h3 class="text-xl font-bold mb-3">Hackers Test: Section 3, Questions 11-20</h3>
                    <audio controls class="w-full mb-4" src="CH1_HT11-20.mp3" title="Chapter 1 Test 11-20 Audio"></audio>
                    <div class="question mb-6">
                        <strong class="block mb-2">Questions 11-12:</strong> Choose <strong>TWO</strong> letters, A-E.
                        <p class="mb-2">Which <strong>TWO</strong> tasks have the students already completed?</p>
                        <div class="space-y-1">
                            <div><input type="checkbox" name="ch1_tq11_12" value="A"> <label>A. an outline for the assignment's structure</label></div>
                            <div><input type="checkbox" name="ch1_tq11_12" value="B"> <label>B. the central part of the document</label></div>
                            <div><input type="checkbox" name="ch1_tq11_12" value="C"> <label>C. the introduction to their report</label></div>
                            <div><input type="checkbox" name="ch1_tq11_12" value="D"> <label>D. data gathering on globalised businesses</label></div>
                            <div><input type="checkbox" name="ch1_tq11_12" value="E"> <label>E. a summary of their research methodology</label></div>
                        </div>
                    </div>
                    <div class="question mb-6">
                         <strong class="block mb-2">Questions 13-14:</strong> Choose <strong>TWO</strong> letters, A-E.
                        <p class="mb-2">Which <strong>TWO</strong> effects did Burger King's approach have when it launched restaurants in India?</p>
                        <div class="space-y-1">
                            <div><input type="checkbox" name="ch1_tq13_14" value="A"> <label>A. positive opinion of the brand around India</label></div>
                            <div><input type="checkbox" name="ch1_tq13_14" value="B"> <label>B. stores spread throughout the region</label></div>
                            <div><input type="checkbox" name="ch1_tq13_14" value="C"> <label>C. certain products put off consumers</label></div>
                            <div><input type="checkbox" name="ch1_tq13_14" value="D"> <label>D. enhanced image in neighbouring countries</label></div>
                            <div><input type="checkbox" name="ch1_tq13_14" value="E"> <label>E. its menu was seen as inappropriate</label></div>
                        </div>
                    </div>
                    <div class="question mb-6">
                         <strong class="block mb-2">Questions 15-16:</strong> Choose <strong>TWO</strong> letters, A-E.
                        <p class="mb-2">Which <strong>TWO</strong> elements of its ads did a Swedish vodka company change for each region?</p>
                        <div class="space-y-1">
                            <div><input type="checkbox" name="ch1_tq15_16" value="A"> <label>A. the type of graphics used</label></div>
                            <div><input type="checkbox" name="ch1_tq15_16" value="B"> <label>B. the language of promotional material</label></div>
                            <div><input type="checkbox" name="ch1_tq15_16" value="C"> <label>C. the size of printed advertisements</label></div>
                            <div><input type="checkbox" name="ch1_tq15_16" value="D"> <label>D. the colours used in materials</label></div>
                            <div><input type="checkbox" name="ch1_tq15_16" value="E"> <label>E. the brand names of products</label></div>
                        </div>
                    </div>
                    <div class="question">
                         <strong class="block mb-2">Questions 17-20:</strong> Choose the correct letter, A, B or C.
                        <div class="space-y-4">
                           <div>
                                <p><strong>17.</strong> The advertisements shown for Calvin Klein caused problems because</p>
                                <div class="space-y-1 pl-4">
                                  <div><input type="radio" name="ch1_tq17" value="A"> <label>A. they were considered not contemporary enough.</label></div>
                                  <div><input type="radio" name="ch1_tq17" value="B"> <label>B. they focused too much on younger consumers.</label></div>
                                  <div><input type="radio" name="ch1_tq17" value="C"> <label>C. they were deemed inappropriate by some consumers.</label></div>
                                </div>
                            </div>
                           <div>
                                <p><strong>18.</strong> A design feature that Calvin Klein introduced in its 2013 line was</p>
                                <div class="space-y-1 pl-4">
                                  <div><input type="radio" name="ch1_tq18" value="A"> <label>A. new and brighter colours.</label></div>
                                  <div><input type="radio" name="ch1_tq18" value="B"> <label>B. clothes tailored to each age group.</label></div>
                                  <div><input type="radio" name="ch1_tq18" value="C"> <label>C. aspects of traditional outfits.</label></div>
                                </div>
                            </div>
                           <div>
                                <p><strong>19.</strong> How will the students include graphs in their report?</p>
                                <div class="space-y-1 pl-4">
                                  <div><input type="radio" name="ch1_tq19" value="A"> <label>A. in an appendix at the end</label></div>
                                  <div><input type="radio" name="ch1_tq19" value="B"> <label>B. in a separate printed leaflet</label></div>
                                  <div><input type="radio" name="ch1_tq19" value="C"> <label>C. inserted throughout the text</label></div>
                                </div>
                            </div>
                            <div>
                                <p><strong>20.</strong> What will the students probably do next?</p>
                                <div class="space-y-1 pl-4">
                                  <div><input type="radio" name="ch1_tq20" value="A"> <label>A. find images to use for their assignment</label></div>
                                  <div><input type="radio" name="ch1_tq20" value="B"> <label>B. go to a library to check out reference books</label></div>
                                  <div><input type="radio" name="ch1_tq20" value="C"> <label>C. create their own marketing plan</label></div>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="mt-4 space-x-2">
                        <button onclick="checkAnswers('ch1_test2')" class="px-4 py-2 bg-blue-600 text-white rounded-lg hover:bg-blue-700 transition">Check Answers</button>
                        <button onclick="toggleTranscript('transcript-ch1-test2')" class="px-4 py-2 bg-gray-600 text-white rounded-lg hover:bg-gray-700 transition">Show/Hide Transcript</button>
                    </div>
                    <div id="feedback-ch1_test2" class="feedback mt-4 space-y-2"></div>
                    <div id="transcript-ch1-test2" class="transcript hidden">
                        <h4>Transcript</h4>
                        <p><strong>Matthew:</strong> I think everything's going smoothly so far. <span class="highlight">We have finished our outline for the structure of the report, and I've just finished our introduction.</span><br>
                        <strong>Catherine:</strong> And I've been doing the research for the main body.<br>
                        ...<br>
                        <strong>Catherine:</strong> ...By giving attention to the concerns of individual consumers in India, <span class="highlight">consumers' perceptions of Burger King's products improved there significantly.</span> ... <span class="highlight">The company started to become more highly regarded in surrounding countries in South East Asia too.</span><br>
                        ...<br>
                        <strong>Catherine:</strong> I also did some research on the promotion aspect for print advertising for the Swedish vodka company, Absolute. This company decided to choose different ads for different regions, and <span class="highlight">incorporate cultural slang into each area's advertisements</span>. ...other than language... what else varied in the ads? ...other elements in print ads, such as <span class="highlight">color, also varied in different regions.</span><br>
                        ...<br>
                        <strong>Matthew:</strong> ...US clothing retail chain Calvin Klein had some trouble when it ran commercials for a new clothing line, and <span class="highlight">many consumers in foreign markets found them highly inappropriate.</span> ...the general consumer response there was that the clothes were too revealing.<br>
                        <strong>Matthew:</strong> ...the company turned things around by <span class="highlight">designing a new line in spring 2013 that featured elements of traditional clothing from various countries</span>, while maintaining the muted and simple color scheme of their general clothing.<br>
                        <strong>Professor:</strong> Good. How did the marketing team decide on adjusting prices for each foreign market?<br>
                        <strong>Catherine:</strong> They naturally had to consider the break-even point...<br>
                        <strong>Professor:</strong> Good. I'd like you to integrate those details into your report. ...How could you tell me what you have in mind for the structure of the report?<br>
                        <strong>Matthew:</strong> ...all of the formulas and graphics will be printed in an appendix at the end of the report.<br>
                        <strong>Professor:</strong> Ah, actually, <span class="highlight">you should mix the visual materials in with the text.</span> Just add footnotes for each graphic.<br>
                        ...<br>
                        <strong>Catherine:</strong> We're going to head to the library now to <span class="highlight">find some visual examples of globalized advertising.</span> We thought it might be a good idea to include pictures of actual ads in the report.</p>
                    </div>
                </div>

            </section>
        </main>
    </div>

    <script>
        const answerKey = {
            ch1_1: {
                ch1_q1: "A", ch1_q2: "B", ch1_q3: "B", ch1_q4: "A"
            },
            ch1_2: {
                ch1_q5_7: ["A", "C", "F"]
            },
            ch1_3: {
                ch1_q8: "B", ch1_q9: "C", ch1_q10: "A", ch1_q11: "B"
            },
            ch1_4: {
                ch1_q12_13: ["B", "D"],
                ch1_q14: "B", ch1_q15: "A", ch1_q16: "B"
            },
            ch1_test1: {
                ch1_tq1_2: ["C", "E"],
                ch1_tq3: "fast food", ch1_tq4: "local", ch1_tq5: "ground",
                ch1_tq6: "A", ch1_tq7: "C", ch1_tq8: "B", ch1_tq9: "A", ch1_tq10: "B"
            },
            ch1_test2: {
                ch1_tq11_12: ["A", "C"],
                ch1_tq13_14: ["A", "D"],
                ch1_tq15_16: ["B", "D"],
                ch1_tq17: "C", ch1_tq18: "C", ch1_tq19: "C", ch1_tq20: "A"
            }
        };

        function toggleTranscript(id) {
            const transcriptEl = document.getElementById(id);
            if (transcriptEl) {
                transcriptEl.classList.toggle('hidden');
            }
        }

        function checkAnswers(sectionId) {
            const feedbackContainer = document.getElementById(`feedback-${sectionId}`);
            feedbackContainer.innerHTML = '';
            let allCorrect = true;
            const sectionAnswers = answerKey[sectionId];

            for (const key in sectionAnswers) {
                const correctAnswer = sectionAnswers[key];
                const questionNum = key.split('_q')[1].replace('tq','').replace('_', '-');
                let isCorrect = false;
                let userAnswerDisplay = '';

                if (Array.isArray(correctAnswer)) {
                    const userCheckboxes = Array.from(document.querySelectorAll(`input[name="${key}"]:checked`)).map(cb => cb.value);
                    userAnswerDisplay = userCheckboxes.join(', ') || 'No answer';
                    if (userCheckboxes.length === correctAnswer.length && userCheckboxes.every(val => correctAnswer.includes(val))) {
                        isCorrect = true;
                    }
                } else if (document.querySelector(`input[name="${key}"]`)) {
                     const userAnswerNode = document.querySelector(`input[name="${key}"]:checked`);
                     if(userAnswerNode){
                        isCorrect = (userAnswerNode.value.toLowerCase() === correctAnswer.toLowerCase());
                        userAnswerDisplay = userAnswerNode.value;
                     } else {
                        userAnswerDisplay = 'No answer';
                     }
                } else {
                    const userInput = document.getElementById(key);
                    userAnswerDisplay = userInput.value.trim();
                    const correctOptions = String(correctAnswer).toLowerCase().split('/');
                    isCorrect = correctOptions.includes(userAnswerDisplay.toLowerCase());
                }

                const feedbackElement = document.createElement('p');
                if (isCorrect) {
                    feedbackElement.className = 'correct';
                    feedbackElement.textContent = `Question ${questionNum}: Correct!`;
                } else {
                    feedbackElement.className = 'incorrect';
                    feedbackElement.textContent = `Question ${questionNum}: Incorrect. Your answer: "${userAnswerDisplay}". Correct answer: "${Array.isArray(correctAnswer) ? correctAnswer.join(', ') : correctAnswer}".`;
                    allCorrect = false;
                }
                feedbackContainer.appendChild(feedbackElement);
            }

            const summaryElement = document.createElement('p');
            summaryElement.className = 'font-bold mt-4 text-lg';
            if (allCorrect) {
                summaryElement.className += ' text-green-700';
                summaryElement.textContent = 'Congratulations! All answers in this section are correct!';
            } else {
                 summaryElement.className += ' text-red-700';
                summaryElement.textContent = 'Some answers are incorrect. Please review the feedback above.';
            }
            feedbackContainer.prepend(summaryElement);
        }
    </script>
</body>
</html>

