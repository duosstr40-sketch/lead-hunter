# رفع صياد العملاء على Vercel (أبسط طريقة)

المشروع جاهز بالكامل. هتعمل 3 حاجات بس:

## 1) ارفع الملفات (مرة واحدة)
1. افتح github.com وسجّل دخول (حساب مجاني) ← **New repository** ← اكتب اسم `lead-hunter` ← **Create**.
2. اضغط **uploading an existing file** واسحب كل محتوى المجلد (بعد فك الـ zip) ← **Commit changes**.
3. افتح vercel.com ← **Add New → Project** ← اختر `lead-hunter` ← **Deploy**.
   (اعمله مشروع جديد منفصل عن موقعك عشان ما يتأثرش)

## 2) جهّز الحسابات وانسخ القيم
- **Serper.dev:** سجّل وانسخ الـ API Key.
- **Firebase:** console.firebase.google.com ← مشروع جديد ← Build ← **Firestore Database** ← Create database.
  بعدين ⚙️ Project settings ← Service accounts ← **Generate new private key** (بينزل ملف).

## 3) حط القيم في Vercel
Vercel ← مشروعك ← **Settings → Environment Variables**، وأضف:

| الاسم | القيمة |
|---|---|
| SEARCH_API_KEY | مفتاح Serper |
| FIREBASE_PROJECT_ID | `project_id` من الملف |
| FIREBASE_CLIENT_EMAIL | `client_email` من الملف |
| FIREBASE_PRIVATE_KEY | `private_key` من الملف (كله بالبداية والنهاية) |
| CRON_SECRET | أي كلمة طويلة (20 حرف مثلاً) |
| ADMIN_API_KEY | كلمة سر تدخلها في صفحة الـ CRM |

بعدها **Deployments ← ⋯ ← Redeploy**.

## الاستخدام
افتح `https://اسم-مشروعك.vercel.app` ← هيطلب كلمة السر (ADMIN_API_KEY) ← اضغط **صيد الآن**.
بعد كده الصياد بيشتغل لوحده كل يوم 8 الصبح تقريباً.
