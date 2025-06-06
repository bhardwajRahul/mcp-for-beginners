<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "e5ea5e7582f70008ea9bec3b3820f20a",
  "translation_date": "2025-05-17T14:21:46+00:00",
  "source_file": "04-PracticalImplementation/samples/java/containerapp/README.md",
  "language_code": "ar"
}
-->
## بنية النظام

يستعرض هذا المشروع تطبيق ويب يستخدم فحص سلامة المحتوى قبل إرسال طلبات المستخدم إلى خدمة الحاسبة عبر بروتوكول سياق النموذج (MCP).

### كيفية العمل

1. **إدخال المستخدم**: يقوم المستخدم بإدخال طلب حسابي في واجهة الويب
2. **فحص سلامة المحتوى (الإدخال)**: يتم تحليل الطلب بواسطة واجهة برمجة تطبيقات سلامة المحتوى من Azure
3. **قرار السلامة (الإدخال)**:
   - إذا كان المحتوى آمنًا (شدة < 2 في جميع الفئات)، يتم إرساله إلى الحاسبة
   - إذا تم اعتبار المحتوى ضارًا، تتوقف العملية وتُرجع تحذيرًا
4. **تكامل الحاسبة**: يتم معالجة المحتوى الآمن بواسطة LangChain4j، الذي يتواصل مع خادم الحاسبة MCP
5. **فحص سلامة المحتوى (الإخراج)**: يتم تحليل استجابة الروبوت بواسطة واجهة برمجة تطبيقات سلامة المحتوى من Azure
6. **قرار السلامة (الإخراج)**:
   - إذا كانت استجابة الروبوت آمنة، تُعرض للمستخدم
   - إذا كانت استجابة الروبوت تعتبر ضارة، يتم استبدالها بتحذير
7. **الاستجابة**: تُعرض النتائج (إذا كانت آمنة) للمستخدم مع كلا تحليلي السلامة

## استخدام بروتوكول سياق النموذج (MCP) مع خدمات الحاسبة

يستعرض هذا المشروع كيفية استخدام بروتوكول سياق النموذج (MCP) لاستدعاء خدمات الحاسبة MCP من LangChain4j. يستخدم التنفيذ خادم MCP محلي يعمل على المنفذ 8080 لتوفير عمليات الحاسبة.

### إعداد خدمة سلامة المحتوى من Azure

قبل استخدام ميزات سلامة المحتوى، تحتاج إلى إنشاء مورد خدمة سلامة المحتوى من Azure:

1. تسجيل الدخول إلى [بوابة Azure](https://portal.azure.com)
2. انقر على "إنشاء مورد" وابحث عن "سلامة المحتوى"
3. اختر "سلامة المحتوى" وانقر على "إنشاء"
4. أدخل اسمًا فريدًا لموردك
5. اختر اشتراكك ومجموعة الموارد الخاصة بك (أو أنشئ واحدة جديدة)
6. اختر منطقة مدعومة (تحقق من [توفر المنطقة](https://azure.microsoft.com/en-us/global-infrastructure/services/?products=cognitive-services) للحصول على التفاصيل)
7. اختر مستوى التسعير المناسب
8. انقر على "إنشاء" لنشر المورد
9. بمجرد اكتمال النشر، انقر على "الانتقال إلى المورد"
10. في اللوحة اليسرى، ضمن "إدارة الموارد"، اختر "المفاتيح ونقطة النهاية"
11. انسخ أحد المفاتيح وعنوان URL لنقطة النهاية للاستخدام في الخطوة التالية

### إعداد متغيرات البيئة

قم بتعيين متغير البيئة `GITHUB_TOKEN` لمصادقة نماذج GitHub:
```sh
export GITHUB_TOKEN=<your_github_token>
```

لميزات سلامة المحتوى، قم بتعيين:
```sh
export CONTENT_SAFETY_ENDPOINT=<your_content_safety_endpoint>
export CONTENT_SAFETY_KEY=<your_content_safety_key>
```

تُستخدم هذه المتغيرات البيئية بواسطة التطبيق للمصادقة مع خدمة سلامة المحتوى من Azure. إذا لم يتم تعيين هذه المتغيرات، سيستخدم التطبيق قيمًا افتراضية لأغراض العرض، لكن ميزات سلامة المحتوى لن تعمل بشكل صحيح.

### بدء تشغيل خادم الحاسبة MCP

قبل تشغيل العميل، تحتاج إلى بدء تشغيل خادم الحاسبة MCP في وضع SSE على localhost:8080.

## وصف المشروع

يستعرض هذا المشروع تكامل بروتوكول سياق النموذج (MCP) مع LangChain4j لاستدعاء خدمات الحاسبة. تشمل الميزات الرئيسية:

- استخدام MCP للاتصال بخدمة الحاسبة للعمليات الرياضية الأساسية
- فحص سلامة المحتوى ذو الطبقتين على كل من طلبات المستخدم واستجابات الروبوت
- تكامل مع نموذج gpt-4.1-nano من GitHub عبر LangChain4j
- استخدام أحداث الخادم المرسلة (SSE) لنقل MCP

## تكامل سلامة المحتوى

يشمل المشروع ميزات سلامة المحتوى الشاملة لضمان أن تكون كل من إدخالات المستخدم واستجابات النظام خالية من المحتوى الضار:

1. **فحص الإدخال**: يتم تحليل جميع طلبات المستخدم لفئات المحتوى الضار مثل خطاب الكراهية والعنف وإيذاء الذات والمحتوى الجنسي قبل المعالجة.

2. **فحص الإخراج**: حتى عند استخدام نماذج غير مراقبة، يقوم النظام بفحص جميع الاستجابات المولدة من خلال نفس فلاتر سلامة المحتوى قبل عرضها على المستخدم.

يضمن هذا النهج ذو الطبقتين أن يظل النظام آمنًا بغض النظر عن النموذج الذكائي المستخدم، مما يحمي المستخدمين من كل من الإدخالات الضارة والنتائج المحتملة التي يولدها الذكاء الاصطناعي.

## العميل الويب

يشمل التطبيق واجهة ويب سهلة الاستخدام تتيح للمستخدمين التفاعل مع نظام الحاسبة لسلامة المحتوى:

### ميزات واجهة الويب

- نموذج بسيط وسهل لإدخال طلبات الحساب
- تحقق سلامة المحتوى ذو الطبقتين (الإدخال والإخراج)
- ردود فعل فورية على سلامة الطلب والاستجابة
- مؤشرات سلامة مرمزة بالألوان لسهولة التفسير
- تصميم نظيف ومتجاوب يعمل على مختلف الأجهزة
- أمثلة على الطلبات الآمنة لإرشاد المستخدمين

### استخدام العميل الويب

1. ابدأ التطبيق:
   ```sh
   mvn spring-boot:run
   ```

2. افتح المتصفح وانتقل إلى `http://localhost:8087`

3. أدخل طلب حساب في منطقة النص المخصصة (مثل "احسب مجموع 24.5 و17.3")

4. انقر على "إرسال" لمعالجة الطلب

5. عرض النتائج، والتي ستشمل:
   - تحليل سلامة المحتوى لطلبك
   - النتيجة المحسوبة (إذا كان الطلب آمنًا)
   - تحليل سلامة المحتوى لاستجابة الروبوت
   - أي تحذيرات سلامة إذا تم اعتبار الإدخال أو الإخراج ضارًا

يتولى العميل الويب تلقائيًا كلا عمليتي التحقق من سلامة المحتوى، مما يضمن أن تكون جميع التفاعلات آمنة ومناسبة بغض النظر عن النموذج الذكائي المستخدم.

**إخلاء المسؤولية**:  
تمت ترجمة هذه الوثيقة باستخدام خدمة الترجمة بالذكاء الاصطناعي [Co-op Translator](https://github.com/Azure/co-op-translator). بينما نسعى لتحقيق الدقة، يرجى العلم أن الترجمات الآلية قد تحتوي على أخطاء أو عدم دقة. يجب اعتبار الوثيقة الأصلية بلغتها الأم هي المصدر الرسمي. للمعلومات الهامة، يوصى بالترجمة البشرية الاحترافية. نحن غير مسؤولين عن أي سوء فهم أو تفسير خاطئ ينشأ عن استخدام هذه الترجمة.