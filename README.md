=========================================================
شرح لاب IOLI Crackme  (من خالد)
الهدف: نخلي كل crackme يقبل أي password (نعمل patch للملف)
=========================================================

[0] أول أمر: نشوف الملفات اللي في الفولدر
    cd IOLI-crackme
    tree /f /a
    (في CMD السويتش بيبقى بسلاش /f مش شرطة -f)

[1] استخدم فولدر bin-win32 بس (ملفات exe 32-bit)
    bin-linux لـ Linux، و bin-pocketPC لأجهزة ARM قديمة. تجاهلهم.

[2] الأمان (الأول، حوالي 5 دقايق)
    - اشتغل جوه الـ Flare VM بس
    - خد Snapshot واقفل النت أو خليه Host-Only
    - ماتشغلش الملفات دي على جهازك الأصلي

[3] الأدوات (حمّلها من المواقع الرسمية بس)
    strings / BinText (10 دقايق)  - بيطلّع النصوص المقروءة (مستوى 0x00)
    IDA Free (ساعة لساعتين)      - hex-rays.com/ida-free
    x32dbg (ساعة لساعتين)        - x64dbg.com (استخدم x32dbg للـ 32-bit)
    Ghidra (اختياري)             - ghidra-sre.org (محتاج Java JDK)

[4] المستويات
    0x00 strings                0x01 رقم ثابت (IDA)
    0x02 قيمة بتتحسب            0x03 نص متشفّر
    0x04 loop بيجمع الأرقام     0x05 زي 4 + شرط زيادة
    0x06 بيقرا environment variable   0x07-0x09 أصعب

[5] الخطوات لكل مستوى
    شغّل الملف ← اقرا الرسالة ← strings ← IDA (دور على main/strcmp/cmp)
    ← x32dbg breakpoint ← غيّر jz/jnz لـ jmp ← احفظ ← جرّب

[6] دوّر على يوتيوب
    "IOLI crackme 0x00 IDA walkthrough"
    "x32dbg tutorial for beginners breakpoint cmp"
    "IDA Free beginner tutorial graph view"
    "Ghidra beginner reverse engineering tutorial"
=========================================================

لو محتاج أي حاجة كلمني: khalidmahran2002@gmail.com