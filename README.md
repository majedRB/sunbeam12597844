# دليل نشر ZK Relay على Render.com

## 📋 ما تحتاجه
- حساب GitHub (مجاني) — https://github.com/signup
- حساب Render (مجاني) — https://render.com/

---

## 🚀 خطوات النشر (10 دقائق)

### 1️⃣ إنشاء مستودع GitHub
1. ادخل على https://github.com/new
2. اسم المستودع: `zk-relay`
3. اختر **Public**
4. اضغط **Create repository**

### 2️⃣ رفع الملفات
- اضغط **uploading an existing file**
- اسحب الملفات الثلاثة (`relay.js`, `package.json`, `README.md`)
- اضغط **Commit changes**

### 3️⃣ النشر على Render
1. ادخل على https://dashboard.render.com/
2. اضغط **New +** → **Web Service**
3. اربط حساب GitHub واختر مستودع `zk-relay`
4. املأ الحقول:
   - **Name**: `zk-relay`
   - **Region**: `Frankfurt` (الأقرب للسعودية)
   - **Branch**: `main`
   - **Runtime**: `Node`
   - **Build Command**: (اتركه فارغ)
   - **Start Command**: `node relay.js`
   - **Instance Type**: **Free**
5. اضغط **Create Web Service**
6. انتظر 2-3 دقائق حتى تظهر كلمة **Live** بالأخضر

### 4️⃣ نسخ رابط الـ Relay
سيظهر لك رابط مثل:
```
https://zk-relay-xxxx.onrender.com
```
انسخه ✅

---

## ⚙️ إعدادات الجهاز ZKTeco MB2000

من قائمة الجهاز:
```
Menu → Comm → Cloud Server Setting
```

| الإعداد | القيمة |
|---------|--------|
| **Domain Name** | `ON` ✅ |
| **Server Address** | `zk-relay-xxxx.onrender.com` (بدون https://) |
| **Server Port** | `80` |
| **Enable Proxy Server** | `OFF` |
| **HTTPS** | `OFF` |

> ⚠️ **مهم**: ضع رابط Render بدون `https://` وبدون `/` في النهاية

### إعادة تشغيل الجهاز
1. أطفئ الجهاز 30 ثانية
2. شغّله مرة أخرى
3. ✅ علامة الـ X الحمراء تختفي = الاتصال نجح

---

## ⚠️ ملاحظة مهمة عن خطة Render المجانية

الخطة المجانية تنام بعد **15 دقيقة** من عدم النشاط. هذا يعني أول طلب بعد النوم قد يتأخر 30-60 ثانية.

**الحل**: استخدم خدمة مجانية مثل **UptimeRobot** (https://uptimerobot.com/) لإرسال طلب كل 5 دقائق على:
```
https://zk-relay-xxxx.onrender.com/health
```

هذا يبقي السيرفر مستيقظاً دائماً، ومجاني تماماً.

---

## 🧪 اختبار التشغيل

افتح في المتصفح:
```
https://zk-relay-xxxx.onrender.com/health
```
يجب أن تظهر كلمة `OK` ✅

---

## 📊 مراقبة السجلات
من لوحة Render → **Logs** ترى كل طلب يصل من الجهاز فوراً.
