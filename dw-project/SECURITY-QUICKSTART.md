# 🚀 دليل البدء السريع - الأمان

<div align="center">

![Security](https://img.shields.io/badge/Setup-5%20Minutes-brightgreen?style=for-the-badge)
![Protection](https://img.shields.io/badge/Protection-Maximum-red?style=for-the-badge)
![Automated](https://img.shields.io/badge/Scanning-Hourly-blue?style=for-the-badge)

**🔒 إعداد كامل في 5 دقائق فقط!**

</div>

---

## ⚡ البدء السريع

### الخطوة 1️⃣: تشغيل سكريبت الإعداد

```bash
# منح الصلاحيات
chmod +x setup-security.sh

# تشغيل الإعداد
./setup-security.sh
```

### الخطوة 2️⃣: إضافة Secrets في GitHub

انتقل إلى: `Settings` → `Secrets and variables` → `Actions`

أضف هذه الـ Secrets:

```
SNYK_TOKEN          # من snyk.io
GITHUB_TOKEN        # تلقائي (موجود)
```

### الخطوة 3️⃣: تفعيل GitHub Actions

```bash
# ارفع الملفات
git add .
git commit -m "🛡️ Enable security scanning"
git push origin main
```

✅ **تم! نظام الحماية يعمل الآن** 🎉

---

## 🔍 ماذا تم تفعيله؟

<table>
<tr>
<td width="50%">

### 🛡️ الحماية التلقائية

- ✅ فحص كل ساعة
- ✅ كشف الأسرار
- ✅ فحص التبعيات
- ✅ تحليل الكود
- ✅ كشف البرمجيات الخبيثة

</td>
<td width="50%">

### 🚨 التنبيهات الفورية

- ✅ إشعارات GitHub
- ✅ إنشاء Issues تلقائي
- ✅ تقارير مفصلة
- ✅ سجل كامل
- ✅ رسائل بريد إلكتروني

</td>
</tr>
</table>

---

## 📋 أوامر مفيدة

### فحص يدوي سريع

```bash
# فحص الأسرار
gitleaks detect --verbose

# فحص التبعيات (Node.js)
npm audit

# فحص التبعيات (Python)
pip install safety && safety check

# فحص Docker
trivy image your-image:tag
```

### اختبار الحماية

```bash
# محاولة commit بيانات حساسة (سيتم منعه)
echo "API_KEY=secret123" > .env
git add .env
git commit -m "test"  # ❌ سيفشل!

# الطريقة الصحيحة
cp .env.example .env
# عدّل القيم في .env
# .env محمي في .gitignore ✅
```

---

## 🎯 أسئلة شائعة

<details>
<summary><b>❓ كيف أعطل الفحص مؤقتاً؟</b></summary>

في `.github/workflows/security-scan.yml`:

```yaml
# علّق السطر:
# - cron: '0 * * * *'
```

</details>

<details>
<summary><b>❓ ماذا لو ظهرت False Positives؟</b></summary>

أضف استثناءات في `.gitignore` أو في تكوين الأداة المحددة.

</details>

<details>
<summary><b>❓ كيف أضيف المزيد من الفحوصات؟</b></summary>

عدّل `.github/workflows/security-scan.yml` وأضف jobs جديدة.

</details>

---

## 🚨 إذا اكتشفت ثغرة

```
1. ❌ لا تنشرها علناً
2. 📧 راسل: security@dwproject.io
3. ⏱️ انتظر 24 ساعة للرد
4. 🔒 ستحصل على مكافأة!
```

---

## 📊 التحقق من الحالة

### في GitHub

```
Actions → Security Scan → آخر تشغيل
```

### محلياً

```bash
# حالة Git Hooks
ls -la .git/hooks/pre-commit

# آخر فحص
cat security-setup-report.txt
```

---

<div align="center">

## ✅ قائمة التحقق النهائية

- [ ] تم تشغيل `setup-security.sh`
- [ ] تمت إضافة GitHub Secrets
- [ ] تم رفع الملفات إلى GitHub
- [ ] تم تشغيل أول Workflow بنجاح
- [ ] تمت مراجعة `SECURITY.md`
- [ ] تم اختبار pre-commit hook

---

### 🎉 مبروك! مشروعك محمي الآن

```ascii
    ╔═══════════════════════════════════════╗
    ║                                       ║
    ║   🧞‍♂️  المارد الرقمي يحرسك  🧞‍♂️      ║
    ║                                       ║
    ║      🛡️  حماية 24/7 نشطة  🛡️         ║
    ║                                       ║
    ╚═══════════════════════════════════════╝
```

[![View Security](https://img.shields.io/badge/View-Security%20Dashboard-success?style=for-the-badge)](https://github.com/asrar-mared/dw-project/security)

</div>
