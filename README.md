# أذكاري | Athkari

نسخة معاد بناؤها من مشروع Flutter **أذكاري** مع Android embedding v2 وGitHub Actions لبناء APK.

## ما تم إصلاحه

- إعادة كتابة مشروع Android باستخدام Flutter الحديث بدل Android v1 embedding.
- `MainActivity` يستخدم `FlutterActivity` من embedding v2.
- إضافة صلاحيات الموقع اللازمة لاتجاه القبلة.
- Workflow يبني APK Release ويرفعه كـ Artifact.
- الحفاظ على وظائف التطبيق الأساسية: الأذكار، التصنيفات، التسبيح، المفضلة، البحث، الوضع الليلي واتجاه القبلة.

## التشغيل محليًا

```bash
flutter pub get
flutter run
```

إذا كان مجلد Android على جهازك قديمًا، نفّذ:

```bash
bash tool/rebuild_android.sh
```

ثم:

```bash
flutter build apk --release
```

الملف الناتج:

`build/app/outputs/flutter-apk/app-release.apk`

## GitHub Actions

كل Push إلى `main` يشغل `.github/workflows/main.yml`.

الـ workflow يعيد إنشاء مضيف Android نظيف بواسطة Flutter، ثم يضيف صلاحيات الموقع، ثم يبني APK Release.

بعد نجاح التشغيل:

**Actions → Build Android APK → Artifacts → athkari-release-apk**

## ملاحظة

مواقيت الصلاة في هذه النسخة واجهة جاهزة للربط بمصدر حساب موثوق؛ لا يتم وضع أوقات مختلقة.
