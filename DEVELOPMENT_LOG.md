# Development Log

## Instructions
Document your development process as you work on the assignment. Add entries showing:
- What you worked on
- Problems you encountered
- How you solved them
- Time spent

**Requirements**: Minimum 5 entries showing progression over time.

---

### Entry 1 - [Mar 27, 2026, 1:31 pm ]

**What I did**: Set up the project and ran the initial code

**Details**:

* Downloaded the project files from the repository
* Opened the project in my IDE
* Checked the code structure and main classes
* Ran the program to make sure everything works

**Challenges**: The program didn’t run at first بسبب خطأ في الإعدادات

**Solution**: عدلت إعدادات المشروع وحددت نسخة الجافا الصحيحة

**Time spent**: 25 minutes

---

### Entry 2 - [Mar 27, 2026, 2:15 pm ]

**What I did**: Started working on thread creation

**Details**:

* تعلمت كيف أنشئ Thread باستخدام Runnable
* كتبت كود بسيط لتشغيل أكثر من Thread
* جربت تشغيلهم مع بعض
* لاحظت ترتيب التنفيذ

**Challenges**: ما فهمت ليش ترتيب الطباعة يتغير كل مرة

**Solution**: قرأت عن concurrent execution وفهمت أنه طبيعي

**Time spent**: 40 minutes

---

### Entry 3 - [Mar 27, 2026, 3:10 pm ]

**What I did**: Implemented shared resource access

**Details**:

* أضفت متغير مشترك بين أكثر من Thread
* خليت Threads تعدل عليه
* راقبت النتائج
* لاحظت اختلاف القيم

**Challenges**: النتائج كانت غير ثابتة (race condition)

**Solution**: استخدمت synchronized لحماية المتغير

**Time spent**: 45 minutes

---

### Entry 4 - [Mar 27, 2026, 4:05 pm ]

**What I did**: Tested thread synchronization

**Details**:

* طبقت synchronized blocks في الكود
* جربت أكثر من سيناريو
* تأكدت أن القيم صارت صحيحة
* قارنت الأداء قبل وبعد

**Challenges**: ما كنت أعرف وين أحط synchronized بالضبط

**Solution**: جربت أكثر من مكان لين ضبطت الطريقة الصحيحة

**Time spent**: 35 minutes

---

### Entry 5 - [Mar 27, 2026, 5:00 pm ]

**What I did**: Debugged multithreading issues

**Details**:

* أضفت print statements لمتابعة التنفيذ
* تابعت كل Thread وش يسوي
* حللت الأخطاء
* عدلت الكود

**Challenges**: صعب تتبع Threads لأنها تشتغل بنفس الوقت

**Solution**: استخدمت تتبع خطوة خطوة وطباعة القيم

**Time spent**: 50 minutes

---

### Entry 6 - [Mar 27, 2026, 6:00 pm ]

**What I did**: Final testing and code cleanup

**Details**:

* شغلت البرنامج أكثر من مرة
* تأكدت أن كل شيء يعمل بدون أخطاء
* رتبت الكود ونظفته
* تأكدت من التعليقات

**Challenges**: بعض النتائج كانت تختلف أحيانًا

**Solution**: راجعت أماكن التزامن وعدلتها

**Time spent**: 30 minutes

## Summary

**Total time spent on assignment**: [4 hours]

**Most challenging part**: the most challenging part was managing shared resources between multiple threads and preventing race conditions. It was tricky to know exactly where to apply synchronization without affecting performance or causing deadlocks. Debugging the program was also difficult because thread execution is unpredictable.

**Most interesting learning**: he most interesting learning was seeing how threads can run concurrently and how the program behavior changes each time they execute. I also found it fascinating to learn how synchronization ensures consistency and prevents conflicts between threads. It was exciting to apply these concepts in practice and see the results in real time.

**What I would do differently next time**: Next time, I would plan the thread interactions more carefully before writing code. I would also write small test cases for each thread functionality first, to avoid big issues later. Additionally, I would spend more time learning advanced concurrency tools and techniques to handle complex multithreading scenarios more efficiently.
