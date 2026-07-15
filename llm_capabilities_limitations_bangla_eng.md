# Lesson 3B: Capabilities ও Limitations কী? 🇧🇩 বাংলা + English

> এই নোটটা [Generative AI Fundamentals নোট](generative_ai_fundamentals_bangla_eng.md), [4D Framework নোট](ai_fluency_4d_framework_bangla_eng.md) এবং [Vocabulary Sheet](ai_fluency_vocab_simple.md) এর সাথে link করা। এখানে জানব Claude-এর মতো LLM **কী পারে (capabilities)** আর **কী পারে না (limitations)** — যেন AI-কে নতুন একজন সহকর্মী (colleague) হিসেবে ভাবা যায়, যার strength ও weakness বুঝে কাজ করতে হয়।

Course: *AI Fluency: Framework & Foundations*

---

## ✅ LLM যা খুব ভালো পারে (What LLMs Do Well)

| ক্ষমতা (Capability) | সহজ বাংলা ব্যাখ্যা |
|---|---|
| **ভাষার দক্ষতা** | Email লেখা, বড় report কে ছোট summary করা, translation, জটিল বিষয় সহজভাবে বোঝানো |
| **Task shift করা** | Extra training ছাড়াই একই model কবিতা লিখতে পারে, আবার quantum computing-ও বোঝাতে পারে |
| **কথোপকথন মনে রাখা** | কথোপকথনের মধ্যে আগে বলা জিনিস (যেমন তোমার deadline) মনে রেখে পরে reference করতে পারে |
| **External tool ব্যবহার** | Web search, file process করা, অন্য app ব্যবহার করে নিজের ক্ষমতা বাড়াতে পারে |

💡 এক কথায়: LLM একসাথে অনেক ধরনের কাজে **flexible**।

---

## ⚠️ LLM-এর সীমাবদ্ধতা (Limitations)

### 1. Knowledge Cutoff (জ্ঞানের সীমা)
**সহজ কথায়:** Model শুধু তার **knowledge cutoff date** পর্যন্ত তথ্য জানে। এরপরের কিছু জানে না, যতক্ষণ না web search-এর মতো tool ব্যবহার করে।

> 🗣️ উদাহরণ: কেউ যদি ইন্টারনেট ছাড়া একটা retreat-এ চলে যায়, সে এরপরের কোনো খবর জানবে না — LLM-ও ঠিক তেমন।

### 2. Hallucination (ভুল তথ্য আত্মবিশ্বাসের সাথে বলা)
| Term (English) | সহজ বাংলা অর্থ |
|---|---|
| **Hallucination** | AI খুব আত্মবিশ্বাসের সাথে এমন কিছু বলে যেটা শুনতে ঠিক মনে হয়, কিন্তু আসলে ভুল |

> 🗣️ উদাহরণ: এমন একজন বন্ধুর কথা ভাবো, যে পুরো আত্মবিশ্বাসের সাথে একটা গল্প বলছে, কিন্তু detail গুলো পুরোপুরি ভুল। LLM সার্চ ইঞ্জিনের মতো ready তথ্য বের করে না — সে **pattern দিয়ে নতুন উত্তর তৈরি করে**, তাই ভুল হতে পারে।

### 3. Context Window সীমা
**সহজ কথায়:** একসাথে কতটুকু তথ্য মনে রাখতে/process করতে পারবে তার একটা সীমা আছে। এই সীমা পার হলে পুরনো তথ্য (usually first-in-first-out ভিত্তিতে) ভুলে যায়।

### 4. Non-deterministic (একই প্রশ্নে ভিন্ন উত্তর)
| Term (English) | সহজ বাংলা অর্থ |
|---|---|
| **Non-deterministic** | একই প্রশ্ন দুইবার করলে সামান্য ভিন্ন উত্তর আসতে পারে |
| **Temperature** | Randomness নিয়ন্ত্রণ করার setting — brainstorm-এর জন্য ভালো, কিন্তু accuracy লাগলে সতর্ক থাকতে হয় |

### 5. জটিল Reasoning-এ দুর্বলতা
**সহজ কথায়:** বহু-ধাপের (multi-step) math বা logic problem-এ ঐতিহাসিকভাবে LLM দুর্বল ছিল। তবে নতুন **reasoning/extended thinking models** এতে অনেক উন্নতি করছে।

### 6. Tool/Data Access-এর সীমা
> 🗣️ উদাহরণ: একজন brilliant সহকর্মী থাকলেও, যদি তার তোমার company-র internal database access না থাকে, সে সাহায্য করতে পারবে না — তেমনি LLM-এরও যদি প্রয়োজনীয় tool বা data access না থাকে, সে সাহায্য করতে পারবে না।

---

## 🔬 এই সমস্যাগুলো ঠিক করতে কী করা হচ্ছে

| Term (English) | সহজ বাংলা অর্থ |
|---|---|
| **RAG (Retrieval Augmented Generation)** | Model কে external জ্ঞান/data source-এর সাথে যুক্ত করে দেওয়া, যাতে ভুল কমে |

গবেষকরা tool-ব্যবহার ক্ষমতা এবং reasoning ক্ষমতা বাড়ানোর চেষ্টা করছেন। তবে কিছু limitation ভবিষ্যতেও থেকে যেতে পারে — যদিও সেগুলো ঠিক কী হবে তা এখনই বলা যাচ্ছে না।

---

## 🤝 মানুষ + AI: Complementary Strengths (একে অপরের পরিপূরক শক্তি)

| কার শক্তি | কী নিয়ে আসে |
|---|---|
| **মানুষ** | Critical thinking, judgment, creativity, ethical oversight |
| **AI** | গতি (speed), scale, pattern recognition, বিশাল তথ্য process করা |

💡 সবচেয়ে কার্যকর ব্যবহার হয় তখনই, যখন মানুষ ও AI-এর শক্তি একসাথে মিলিয়ে কাজ করা হয়।

---

## 📝 সংক্ষেপে (Recap)

**LLM যা পারে:** ভাষার কাজ, task shift, conversation মনে রাখা, tool ব্যবহার
**LLM যা পারে না (ভালোভাবে):** নির্দিষ্ট cutoff-এর পরের তথ্য জানা, সবসময় সঠিক থাকা (hallucination হতে পারে), সীমাহীন তথ্য মনে রাখা, প্রতিবার একই উত্তর দেওয়া, জটিল multi-step reasoning (উন্নতি হচ্ছে), যেসব tool/data access নেই সেগুলো ব্যবহার করা

---

## 🔗 সম্পর্কিত নোট (Linked Notes)
- [ai_fluency_vocab_simple.md](ai_fluency_vocab_simple.md)
- [ai_fluency_4d_framework_bangla_eng.md](ai_fluency_4d_framework_bangla_eng.md)
- [generative_ai_fundamentals_bangla_eng.md](generative_ai_fundamentals_bangla_eng.md)

### 🎯 Self-Test
নিজেকে জিজ্ঞাসা করো:
- Hallucination কী, এবং কেন হয়?
- Context window সীমা পার হলে কী হয়?
- Non-deterministic মানে কী?
- মানুষ ও AI-এর complementary strength কী কী?
