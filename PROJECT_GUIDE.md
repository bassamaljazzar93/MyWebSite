# 🚀 AI Portfolio Builder - دليل المشروع

## نظرة عامة

موقع متكامل لإنشاء وتخصيص مواقع البورتفوليو باستخدام الذكاء الصناعي. يتميز المشروع بمحرر كود مباشر، معاينة فورية، ودعم Groq API مع نموذج Llama 3.3 70B.

## 📁 هيكل الملفات

```
MyWebSite/
├── index.html              # الصفحة الرئيسية - بورتفوليو بسام الجزار
├── ai-customizer.html      # محرر البورتفوليو بالذكاء الصناعي (جديد)
├── auth.html              # صفحة التسجيل وتسجيل الدخول (جديد)
├── ai-playground.html     # ملعب الذكاء الصناعي
└── README.md              # معلومات المستودع
```

## ✨ المميزات الجديدة

### 1. صفحة AI Customizer (ai-customizer.html)

#### المكونات الرئيسية:
- **محرر الكود المباشر**: محرر CodeMirror مع syntax highlighting
- **المعاينة الفورية**: iframe يعرض التغييرات مباشرة
- **مساعد الذكاء الصناعي**: دردشة مع AI مدعوم بـ Groq API
- **أزرار سريعة**: تخصيص سريع للألوان، الخطوط، الأقسام، والحركات

#### التقنيات المستخدمة:
- **CodeMirror 5.65.2**: محرر كود احترافي
- **Groq API**: Llama 3.3 70B للذكاء الصناعي
- **HTML/CSS/JavaScript**: تطوير frontend خالص

#### الوظائف الرئيسية:

```javascript
// دالة إرسال الرسائل للذكاء الصناعي
async function sendMessage() {
    // جلب مفتاح API من المستخدم
    // إرسال الطلب لـ Groq API
    // تطبيق التعديلات على الكود
    // تحديث المعاينة المباشرة
}

// دالة استدعاء Groq API
async function callGroqAPI(apiKey, userMessage, currentCode) {
    // استخدام نموذج llama-3.3-70b-versatile
    // إرجاع الكود المعدل والشرح
}
```

#### الأزرار السريعة:
1. **🎨 Change Colors**: تغيير نظام الألوان
2. **✍️ Change Font**: تغيير الخطوط
3. **➕ Add Section**: إضافة أقسام جديدة
4. **✨ Add Animation**: إضافة حركات

### 2. صفحة المصادقة (auth.html)

#### المميزات:
- **تسجيل الدخول**: نظام login مع Remember Me
- **إنشاء حساب**: نموذج signup مع التحقق من كلمة المرور
- **تسجيل اجتماعي**: أزرار Google و GitHub (قريباً)
- **حفظ الجلسة**: localStorage و sessionStorage

#### نظام المصادقة:

```javascript
// تسجيل الدخول
function handleLogin(event) {
    // التحقق من البيانات
    // حفظ الجلسة
    // التحويل إلى ai-customizer.html
}

// إنشاء حساب
function handleSignup(event) {
    // التحقق من تطابق كلمات المرور
    // حفظ المستخدم في localStorage
    // التحويل لصفحة تسجيل الدخول
}
```

#### التخزين:
```javascript
// بيانات المستخدمين
localStorage.setItem('users', JSON.stringify([
    { name, email, password, createdAt }
]));

// بيانات الجلسة
localStorage.setItem('session', JSON.stringify({
    email, name, loggedIn: true, timestamp
}));
```

## 🔧 كيفية الاستخدام

### 1. الحصول على Groq API Key

1. اذهب إلى [console.groq.com](https://console.groq.com/keys)
2. أنشئ حساب مجاني
3. احصل على API key
4. أدخله في صفحة AI Customizer

### 2. تشغيل الموقع محلياً

```bash
# استنساخ المستودع
git clone https://github.com/bassamaljazzar93/MyWebSite.git

# فتح الملفات في المتصفح
# يمكنك فتح index.html مباشرة
# أو استخدام خادم محلي:

# باستخدام Python
python -m http.server 8000

# باستخدام Node.js
npx http-server

# ثم افتح http://localhost:8000
```

### 3. سير العمل

1. **الصفحة الرئيسية** (index.html)
   - عرض البورتفوليو
   - روابط للأدوات

2. **التسجيل** (auth.html)
   - إنشاء حساب أو تسجيل الدخول
   - حفظ بيانات المستخدم

3. **التخصيص** (ai-customizer.html)
   - إدخال Groq API key
   - استخدام AI لتخصيص البورتفوليو
   - معاينة مباشرة
   - تحميل الكود

## 🌐 دعم اللغات

الموقع يدعم **العربية** و **الإنجليزية** بشكل كامل:

```javascript
function toggleLanguage() {
    currentLanguage = currentLanguage === 'en' ? 'ar' : 'en';
    document.documentElement.dir = currentLanguage === 'ar' ? 'rtl' : 'ltr';
    
    // تحديث جميع النصوص
    document.querySelectorAll('[data-en]').forEach(el => {
        el.textContent = el.getAttribute(`data-${currentLanguage}`);
    });
}
```

## 🎨 التصميم

### نظام الألوان:
```css
:root {
    --primary: #00d9ff;      /* أزرق سماوي */
    --secondary: #7c3aed;    /* بنفسجي */
    --accent: #f59e0b;       /* برتقالي */
    --bg-dark: #0a0e27;      /* خلفية داكنة */
    --bg-darker: #050816;    /* خلفية أغمق */
}
```

### الخطوط:
- **Inter**: للإنجليزية
- **Cairo**: للعربية

### المؤثرات:
- تدرجات لونية
- ظلال متحركة
- انتقالات سلسة
- خلفية متحركة بنقاط

## 📱 التوافق

- ✅ متوافق مع جميع المتصفحات الحديثة
- ✅ تصميم متجاوب (Responsive)
- ✅ دعم الأجهزة المحمولة
- ✅ RTL/LTR support

## 🔒 الأمان

### ملاحظات مهمة:
1. **API Keys**: يتم حفظها في localStorage (للتطوير فقط)
2. **كلمات المرور**: يتم حفظها بنص عادي في localStorage (للتطوير فقط)
3. **للإنتاج**: يجب استخدام:
   - Backend API لحفظ البيانات
   - تشفير كلمات المرور (bcrypt)
   - JWT للمصادقة
   - HTTPS

## 🚀 التطوير المستقبلي

### المخطط:
- [ ] Backend API (Node.js/Express)
- [ ] قاعدة بيانات (MongoDB/PostgreSQL)
- [ ] تشفير كلمات المرور
- [ ] OAuth (Google, GitHub)
- [ ] حفظ البورتفوليوات في السحابة
- [ ] معرض للقوالب الجاهزة
- [ ] تصدير PDF
- [ ] مشاركة البورتفوليو
- [ ] نظام الاشتراكات

## 📊 إحصائيات الكود

- **ai-customizer.html**: ~850 سطر
- **auth.html**: ~550 سطر
- **index.html**: ~1965 سطر (محدث)
- **إجمالي الإضافات**: +1650 سطر

## 🤝 المساهمة

للمساهمة في المشروع:

1. Fork المستودع
2. أنشئ branch جديد
3. قم بالتعديلات
4. أرسل Pull Request

## 📞 التواصل

- **المطور**: بسام وليد الجزار
- **GitHub**: [bassamaljazzar93](https://github.com/bassamaljazzar93)
- **الموقع**: [MyWebSite](https://github.com/bassamaljazzar93/MyWebSite)

## 📝 الترخيص

هذا المشروع مفتوح المصدر ومتاح للاستخدام الحر.

---

**تم التطوير بواسطة**: بسام الجزار  
**التاريخ**: 2025  
**التقنيات**: HTML, CSS, JavaScript, Groq API, CodeMirror

