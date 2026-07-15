# Lesson 7: Effective Prompting Techniques (Deep Dive) 
> এই নোটটা [Description Deep Dive নোট](description_deep_dive_bangla_eng.md) এবং বাকি সিরিজের সাথে link করা। এখানে জানব **Description** skill-টা বাস্তবে কীভাবে প্রয়োগ (apply) করতে হয় — অর্থাৎ effective prompting-এর ৬টা মূল technique।

Course: *AI Fluency: Framework & Foundations*

---

## 🧠 মূল কথা

**Prompting** আসলে **Description** competency-টাই practice-এ প্রয়োগ করা — অর্থাৎ স্পষ্টভাবে বলা: কী চাই, কীভাবে চাই, আর পুরো process জুড়ে AI-এর সাথে কীভাবে interact করতে চাই।

> 🗣️ চিন্তা করো একজন নতুন, আগ্রহী সহকর্মীকে (colleague) কাজ বোঝানোর মতো — যে সাহায্য করতে চায়, কিন্তু ভালো কাজের জন্য তার স্পষ্ট নির্দেশনা দরকার।

| Term (English) | সহজ বাংলা অর্থ |
|---|---|
| **Prompt Engineering** | Claude-এর মতো AI-এর জন্য কার্যকর instruction ডিজাইন করার practice |

💡 ভালো prompting = **মানুষের সাথে ভালো communication-এর নিয়ম** (clear হওয়া, context দেওয়া, উদাহরণ দেওয়া) + **AI-specific কিছু বিষয়** (মানুষ যা এমনিতেই বুঝে নেয়, তা explicit করে বলা, limited context window মাথায় রাখা)।

---

## ✨ ৬টা Foundational Prompting Technique

### 1️⃣ Context দাও (Give Context)
**সহজ কথায়:** কী চাও, কেন চাও, এবং তুমি কে — এসব স্পষ্টভাবে বলো।

> ❌ Vague: "Tell me about climate change."

> ✅ Better: "Explain three major impacts of climate change on agriculture in tropical regions with examples from the past decade."

> ✅✅ Best: "Explain three major impacts of climate change on agriculture in tropical regions with examples from the past decade. I'm preparing for a job interview at an agricultural research lab in Indonesia. I have a degree in ecology, but no specific knowledge on climate change. Write a summary of key concepts that would help me speak intelligently in the interview."

💡 Context দিলে Claude-এর উত্তর তোমার নির্দিষ্ট পরিস্থিতি ও জ্ঞানস্তরের (knowledge level) সাথে মানানসই হয়।

### 2️⃣ Example দেখাও (Show Examples)
**সহজ কথায়:** যেমন output চাও, তার উদাহরণ দেখানো — একে **few-shot / n-shot prompting**-ও বলা হয়।

| Term (English) | সহজ বাংলা অর্থ |
|---|---|
| **Few-shot / N-shot Prompting** | Output pattern বোঝাতে কয়েকটা উদাহরণ দেওয়া (n = উদাহরণ সংখ্যা) |

> 🗣️ উদাহরণ: "Here are two examples of how to convert technical jargon into plain language. Original: 'The quantum algorithm exhibits quadratic speed up.' Plain: 'The new method solves problems roughly twice as fast as previous methods.' Original: 'The interface leverages intuitive design paradigms.' Plain: 'The design is easy to understand and use.' Now, please convert this complex technical manual to plain language."

💡 প্রথমে example ছাড়া try করাই ভালো, কিন্তু যদি খুব নির্দিষ্ট style চাও যেটা বলার চেয়ে দেখানো সহজ, তখন example দাও। বিভিন্ন ধরনের case cover করা উদাহরণ দিলে Claude pattern-টা ভালো বুঝবে।

### 3️⃣ Constraint স্পষ্ট করো (Specify Constraints)
**সহজ কথায়:** Output-এর format, length, ভাষা (programming language), color ইত্যাদি নির্দিষ্ট করে বলা।

> 🗣️ উদাহরণ: "Create a clean, modern, single page art portfolio website. Include these main sections: hero, about me, skills, portfolio, projects, experience, and contact. Make the navigation menu sticky and responsive with hamburger menu on mobile. Use a sunset color palette and add a dark/light mode toggle in the navigation."

### 4️⃣ জটিল Task-কে ধাপে ভাগ করো (Break Complex Tasks into Steps)
**সহজ কথায়:** কঠিন request-কে ছোট ছোট step-এ ভাগ করে দেওয়া, যাতে Claude তোমার চিন্তা follow করতে পারে।

| Term (English) | সহজ বাংলা অর্থ |
|---|---|
| **Chain-of-Thought Prompting** | Task-কে ধাপে ধাপে ভাগ করে বলা, যাতে AI সঠিক process অনুসরণ করে |

> 🗣️ উদাহরণ: "I'd like to analyze this quarterly sales data. Please approach this by looking through our sales records to identify the top performing products, comparing current quarter results to the previous quarter, highlighting any unusual trends or patterns, and then suggesting possible reasons for these trends."

💡 তোমার domain expertise যত বেশি নির্দিষ্ট এবং execution-এর উপায় যত বেশি ভিন্ন হতে পারে, ততই এই ধাপে ধাপে বলাটা গুরুত্বপূর্ণ। নতুন **reasoning/extended thinking model**-গুলো এমনিতেই step-by-step reasoning করতে পারে, তবুও তুমি সেটা guide করতে পারো।

### 5️⃣ আগে চিন্তা করতে বলো (Ask Claude to Think First)
**সহজ কথায়:** Answer দেওয়ার আগে Claude-কে চিন্তা করার জায়গা (space) দাও।

> 🗣️ উদাহরণ prompt: "Before answering, please think through this problem carefully. Consider the different factors involved, potential constraints, and various approaches before recommending the best solution."

💡 এটা কাজের **আগে** চিন্তা করার সুযোগ দেয় (পরে ব্যাখ্যা চাওয়ার চেয়ে ভিন্ন) — এতে output-এর quality ভালো হয়, এবং AI কোথায় ভুল পথে যাচ্ছে সেটাও তুমি বুঝতে পারো।

### 6️⃣ Role/Style/Tone নির্ধারণ করো (Define Claude's Role, Style, or Tone)
**সহজ কথায়:** Claude কে কী "হিসেবে" কথা বলতে বলবে — এতে interaction ও final output দুটোই বদলে যায়।

> 🗣️ উদাহরণ: "Please explain how rainbows form from the perspective of an experienced science teacher speaking to a bright 10-year-old who's interested in science."

> আরেকটা উদাহরণ: "As a UX design expert, review this website wireframe and suggest three improvements focusing on user navigation and accessibility."

---

## 🔑 গোপন অস্ত্র (The Secret Weapon)

**সবচেয়ে শক্তিশালী technique:** যখন কীভাবে prompt লিখবে বুঝতে পারছো না, তখন **Claude-কেই জিজ্ঞাসা করো** prompt টা ভালো করতে সাহায্য করতে!

> 🗣️ উদাহরণ: "I'm trying to get you, Claude, to help me with [goal]. I'm not sure how to phrase my request to get the best results. Can you help me craft an effective prompt for this?"

---

## 🔁 Prompting একটা Iterative Process

**সহজ কথায়:** প্রথমবারেই perfect result আসবে না — এটাই স্বাভাবিক। উত্তর ঠিক না হলে:

- আরও specificity/context যোগ করো
- Example দাও
- Task-কে ছোট ধাপে ভাগ করো
- অন্য technique try করো
- Variation চাও (যেমন: "Can you give me three different versions of this?")
- Format বদলাতে বলো (যেমন: "Instead of a paragraph, could you present this in an interactive artifact?")
- Confidence যাচাই করো (যেমন: "How confident are you about this answer?")
- একদম নতুন করে conversation শুরু করো (মাঝে মাঝে এটাই সবচেয়ে ভালো)

---

## ✅ যা করবে, ❌ যা এড়াবে

| ✅ ভালো Pattern | ❌ সাধারণ ভুল |
|---|---|
| স্পষ্ট task overview দিয়ে শুরু করা | Claude মন পড়তে পারবে ধরে নেওয়া |
| Format specification ও example দেওয়া | একটা prompt-এ অনেক অসম্পর্কিত task গুলিয়ে ফেলা |
| Explicit constraint/requirement দেওয়া | Success কেমন দেখতে হবে তা নিয়ে অস্পষ্ট থাকা |
| প্রাসঙ্গিক background তথ্য দেওয়া | আগের response নিয়ে feedback না দেওয়া |

---

## 📝 সংক্ষেপে (Recap)

| # | Technique (English) | সহজ বাংলা |
|---|---|---|
| 1 | Give context | কী, কেন, কে — বলা |
| 2 | Show examples | উদাহরণ দিয়ে দেখানো |
| 3 | Specify constraints | Format/length ইত্যাদি নির্দিষ্ট করা |
| 4 | Break into steps | ধাপে ধাপে ভাগ করা |
| 5 | Ask to think first | আগে চিন্তা করার সুযোগ দেওয়া |
| 6 | Define role/tone | কী "হিসেবে" কথা বলবে বলা |

+ 🔑 Secret weapon: prompt লিখতেই Claude-এর সাহায্য নাও!

💬 Effective prompting = timeless human communication principle + AI-specific technique। এটা **iterative** এবং কখনো কখনো Claude-এর সাথে **collaborative**-ও বটে।

---

## ➡️ পরবর্তী Lesson
পরের lesson-এ আমরা তৃতীয় core competency **Discernment** নিয়ে explore করব — AI যা তৈরি করে, সেটা চিন্তা করে যাচাই করার দক্ষতা। Description ছিল কথোপকথনের এক অর্ধেক (কীভাবে বলবে); Discernment হলো বাকি অর্ধেক (কীভাবে যাচাই করবে)।

💡 চাইলে আগের lesson-এর **Bad Prompt Makeover** exercise আবার revisit করে এই ৬টা principle দিয়ে practice করতে পারো।

---

## 🔗 সম্পর্কিত নোট (Linked Notes)
- [ai_fluency_vocab_simple.md](ai_fluency_vocab_simple.md)
- [ai_fluency_4d_framework_bangla_eng.md](ai_fluency_4d_framework_bangla_eng.md)
- [generative_ai_fundamentals_bangla_eng.md](generative_ai_fundamentals_bangla_eng.md)
- [llm_capabilities_limitations_bangla_eng.md](llm_capabilities_limitations_bangla_eng.md)
- [delegation_deep_dive_bangla_eng.md](delegation_deep_dive_bangla_eng.md)
- [delegation_exercise_bangla_eng.md](delegation_exercise_bangla_eng.md)
- [description_deep_dive_bangla_eng.md](description_deep_dive_bangla_eng.md)

### 🎯 Self-Test
নিজেকে জিজ্ঞাসা করো:
- ৬টা technique-এর নাম মনে করার চেষ্টা করো, উদাহরণ ছাড়াই
- Chain-of-thought prompting কী?
- "Secret weapon" technique-টা কী?
- Prompting কেন iterative একটা process?
