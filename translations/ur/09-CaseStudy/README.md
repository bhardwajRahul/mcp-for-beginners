<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "4d3415b9d2bf58bc69be07f945a69e07",
  "translation_date": "2025-05-20T23:33:30+00:00",
  "source_file": "09-CaseStudy/README.md",
  "language_code": "ur"
}
-->
# کیس اسٹڈی: Azure AI Travel Agents – حوالہ جاتی نفاذ

## جائزہ

[Azure AI Travel Agents](https://github.com/Azure-Samples/azure-ai-travel-agents) مائیکروسافٹ کی طرف سے تیار کردہ ایک جامع حوالہ جاتی حل ہے جو دکھاتا ہے کہ کس طرح Model Context Protocol (MCP)، Azure OpenAI، اور Azure AI Search کا استعمال کرتے ہوئے ایک کثیر ایجنٹ، AI سے چلنے والی سفر کی منصوبہ بندی کی ایپلیکیشن بنائی جا سکتی ہے۔ یہ پروجیکٹ متعدد AI ایجنٹس کی تنظیم، انٹرپرائز ڈیٹا کے انضمام، اور حقیقی دنیا کے منظرناموں کے لیے ایک محفوظ، توسیع پذیر پلیٹ فارم فراہم کرنے کی بہترین عملی مثالیں پیش کرتا ہے۔

## اہم خصوصیات
- **کثیر ایجنٹ تنظیم:** MCP کا استعمال کرتے ہوئے خصوصی ایجنٹس (مثلاً فلائٹ، ہوٹل، اور سفرنامہ ایجنٹس) کو مربوط کرتا ہے جو پیچیدہ سفر کی منصوبہ بندی کے کاموں کو پورا کرنے کے لیے تعاون کرتے ہیں۔
- **انٹرپرائز ڈیٹا انضمام:** Azure AI Search اور دیگر انٹرپرائز ڈیٹا ذرائع سے جڑتا ہے تاکہ سفر کی سفارشات کے لیے تازہ ترین اور متعلقہ معلومات فراہم کی جا سکیں۔
- **محفوظ، توسیع پذیر فن تعمیر:** تصدیق، اجازت، اور توسیع پذیر تعیناتی کے لیے Azure خدمات کا فائدہ اٹھاتا ہے، انٹرپرائز سیکیورٹی کی بہترین مشقوں کی پیروی کرتے ہوئے۔
- **توسیع پذیر ٹولنگ:** دوبارہ قابل استعمال MCP ٹولز اور پرامپٹ ٹیمپلیٹس کا نفاذ کرتا ہے، جو نئے شعبوں یا کاروباری ضروریات کے لیے تیز تر موافقت کو ممکن بناتا ہے۔
- **صارف کا تجربہ:** صارفین کو سفر کے ایجنٹس کے ساتھ بات چیت کرنے کے لیے ایک مکالماتی انٹرفیس فراہم کرتا ہے، جو Azure OpenAI اور MCP سے چلتا ہے۔

## فن تعمیر
![Architecture](https://raw.githubusercontent.com/Azure-Samples/azure-ai-travel-agents/main/docs/ai-travel-agents-architecture-diagram.png)

### فن تعمیر کے خاکے کی وضاحت

Azure AI Travel Agents حل کو ماڈیولر، توسیع پذیر، اور متعدد AI ایجنٹس اور انٹرپرائز ڈیٹا ذرائع کے محفوظ انضمام کے لیے ڈیزائن کیا گیا ہے۔ مرکزی اجزاء اور ڈیٹا کا بہاؤ درج ذیل ہے:

- **صارف انٹرفیس:** صارفین نظام کے ساتھ ایک مکالماتی UI (جیسے ویب چیٹ یا Teams بوٹ) کے ذریعے بات چیت کرتے ہیں، جو صارف کی درخواستیں بھیجتا اور سفر کی سفارشات وصول کرتا ہے۔
- **MCP سرور:** مرکزی منتظم کے طور پر کام کرتا ہے، صارف کی ان پٹ وصول کرتا ہے، سیاق و سباق کو منظم کرتا ہے، اور Model Context Protocol کے ذریعے خصوصی ایجنٹس (مثلاً FlightAgent، HotelAgent، ItineraryAgent) کے اقدامات کو مربوط کرتا ہے۔
- **AI ایجنٹس:** ہر ایجنٹ مخصوص شعبے (فلائٹس، ہوٹلز، سفرنامے) کا ذمہ دار ہوتا ہے اور MCP ٹول کے طور پر نافذ کیا جاتا ہے۔ ایجنٹس پرامپٹ ٹیمپلیٹس اور منطق کا استعمال کرتے ہوئے درخواستوں کو پروسیس کرتے اور جوابات تیار کرتے ہیں۔
- **Azure OpenAI سروس:** جدید قدرتی زبان کی تفہیم اور تخلیق فراہم کرتی ہے، ایجنٹس کو صارف کی نیت کو سمجھنے اور مکالماتی جوابات تیار کرنے کے قابل بناتی ہے۔
- **Azure AI Search اور انٹرپرائز ڈیٹا:** ایجنٹس تازہ ترین معلومات حاصل کرنے کے لیے Azure AI Search اور دیگر انٹرپرائز ڈیٹا ذرائع سے سوالات کرتے ہیں۔
- **تصدیق اور سیکیورٹی:** Microsoft Entra ID کے ساتھ مربوط ہوتی ہے تاکہ محفوظ تصدیق فراہم کی جا سکے اور تمام وسائل پر کم از کم مراعات والے رسائی کنٹرولز لاگو کیے جائیں۔
- **تعیناتی:** Azure Container Apps پر تعیناتی کے لیے ڈیزائن کیا گیا ہے، جو توسیع پذیری، نگرانی، اور آپریشنل کارکردگی کو یقینی بناتا ہے۔

یہ فن تعمیر متعدد AI ایجنٹس کی ہموار تنظیم، انٹرپرائز ڈیٹا کے محفوظ انضمام، اور شعبہ مخصوص AI حل بنانے کے لیے ایک مضبوط، توسیع پذیر پلیٹ فارم کو ممکن بناتا ہے۔

## فن تعمیر کے خاکے کی مرحلہ وار وضاحت
تصور کریں کہ آپ ایک بڑی سفر کی منصوبہ بندی کر رہے ہیں اور آپ کے پاس ماہر معاونین کی ایک ٹیم ہے جو ہر تفصیل میں آپ کی مدد کر رہی ہے۔ Azure AI Travel Agents نظام اسی طرح کام کرتا ہے، مختلف حصوں (جیسے ٹیم کے ارکان) کو استعمال کرتے ہوئے جن کا ہر ایک خاص کام ہوتا ہے۔ یہ ہے کہ یہ سب کیسے مل کر کام کرتے ہیں:

### صارف انٹرفیس (UI):
اسے اپنے سفر کے ایجنٹ کے فرنٹ ڈیسک کے طور پر سوچیں۔ یہ وہ جگہ ہے جہاں آپ (صارف) سوالات کرتے یا درخواستیں دیتے ہیں، جیسے "پیرس کے لیے فلائٹ تلاش کریں۔" یہ ویب سائٹ پر چیٹ ونڈو یا میسجنگ ایپ ہو سکتی ہے۔

### MCP سرور (منتظم):
MCP سرور اس مینیجر کی طرح ہے جو فرنٹ ڈیسک پر آپ کی درخواست سنتا ہے اور فیصلہ کرتا ہے کہ کون سا ماہر کس حصے کو سنبھالے گا۔ یہ آپ کی گفتگو کا ریکارڈ رکھتا ہے اور یقینی بناتا ہے کہ سب کچھ بخوبی چل رہا ہے۔

### AI ایجنٹس (ماہر معاونین):
ہر ایجنٹ ایک مخصوص شعبے کا ماہر ہوتا ہے—ایک فلائٹس کے بارے میں جانتا ہے، دوسرا ہوٹلز کے بارے میں، اور تیسرا آپ کے سفرنامے کی منصوبہ بندی کے بارے میں۔ جب آپ سفر کی درخواست کرتے ہیں، MCP سرور آپ کی درخواست متعلقہ ایجنٹ(ز) کو بھیجتا ہے۔ یہ ایجنٹس اپنی معلومات اور ٹولز کا استعمال کرتے ہوئے آپ کے لیے بہترین اختیارات تلاش کرتے ہیں۔

### Azure OpenAI سروس (زبان کا ماہر):
یہ ایسے ہے جیسے ایک زبان کا ماہر جو بالکل سمجھتا ہے کہ آپ کیا پوچھ رہے ہیں، چاہے آپ اسے کیسے بھی کہیں۔ یہ ایجنٹس کو آپ کی درخواستوں کو سمجھنے اور قدرتی، مکالماتی زبان میں جواب دینے میں مدد دیتا ہے۔

### Azure AI Search اور انٹرپرائز ڈیٹا (معلومات کی لائبریری):
تصور کریں کہ ایک بہت بڑی، تازہ ترین معلومات کی لائبریری ہے جس میں تمام جدید سفر کی معلومات—فلائٹ شیڈولز، ہوٹل کی دستیابی، اور مزید شامل ہیں۔ ایجنٹس اس لائبریری میں تلاش کرتے ہیں تاکہ آپ کو سب سے درست جواب ملے۔

### تصدیق اور سیکیورٹی (سیکیورٹی گارڈ):
جیسے سیکیورٹی گارڈ چیک کرتا ہے کہ کون مخصوص علاقوں میں داخل ہو سکتا ہے، یہ حصہ یقینی بناتا ہے کہ صرف مجاز افراد اور ایجنٹس حساس معلومات تک رسائی حاصل کر سکیں۔ یہ آپ کے ڈیٹا کو محفوظ اور نجی رکھتا ہے۔

### Azure Container Apps پر تعیناتی (عمارت):
یہ تمام معاونین اور ٹولز ایک محفوظ، توسیع پذیر عمارت (کلاؤڈ) کے اندر مل کر کام کرتے ہیں۔ اس کا مطلب ہے کہ نظام بیک وقت بہت سے صارفین کو سنبھال سکتا ہے اور جب بھی آپ کو ضرورت ہو ہمیشہ دستیاب رہتا ہے۔

## یہ سب کیسے مل کر کام کرتے ہیں:

آپ فرنٹ ڈیسک (UI) پر سوال پوچھ کر شروع کرتے ہیں۔  
مینجر (MCP سرور) فیصلہ کرتا ہے کہ کون سا ماہر (ایجنٹ) آپ کی مدد کرے گا۔  
ماہر زبان کے ماہر (OpenAI) کا استعمال کرتے ہوئے آپ کی درخواست کو سمجھتا ہے اور معلومات کی لائبریری (AI Search) سے بہترین جواب تلاش کرتا ہے۔  
سیکیورٹی گارڈ (تصدیق) یقینی بناتا ہے کہ سب کچھ محفوظ ہے۔  
یہ سب ایک قابل اعتماد، توسیع پذیر عمارت (Azure Container Apps) کے اندر ہوتا ہے، تاکہ آپ کا تجربہ ہموار اور محفوظ رہے۔  
یہ ٹیم ورک نظام کو تیزی اور حفاظت کے ساتھ آپ کا سفر منصوبہ بنانے میں مدد دیتا ہے، بالکل ایسے جیسے ماہر سفر کے ایجنٹس کی ایک ٹیم جدید دفتر میں مل کر کام کر رہی ہو!

## تکنیکی نفاذ
- **MCP سرور:** بنیادی تنظیمی منطق کی میزبانی کرتا ہے، ایجنٹ ٹولز کو ظاہر کرتا ہے، اور کثیر مرحلہ سفر کی منصوبہ بندی کے ورک فلو کے لیے سیاق و سباق کا انتظام کرتا ہے۔
- **ایجنٹس:** ہر ایجنٹ (مثلاً FlightAgent، HotelAgent) اپنے پرامپٹ ٹیمپلیٹس اور منطق کے ساتھ MCP ٹول کے طور پر نافذ کیا جاتا ہے۔
- **Azure انضمام:** قدرتی زبان کی تفہیم کے لیے Azure OpenAI اور ڈیٹا بازیافت کے لیے Azure AI Search کا استعمال کرتا ہے۔
- **سیکیورٹی:** Microsoft Entra ID کے ساتھ تصدیق کے لیے مربوط ہوتا ہے اور تمام وسائل پر کم از کم مراعات والے رسائی کنٹرولز لاگو کرتا ہے۔
- **تعیناتی:** توسیع پذیری اور آپریشنل کارکردگی کے لیے Azure Container Apps پر تعیناتی کی حمایت کرتا ہے۔

## نتائج اور اثرات
- ظاہر کرتا ہے کہ MCP کو حقیقی دنیا کے، پروڈکشن گریڈ منظرنامے میں متعدد AI ایجنٹس کی تنظیم کے لیے کیسے استعمال کیا جا سکتا ہے۔
- ایجنٹ کی ہم آہنگی، ڈیٹا انضمام، اور محفوظ تعیناتی کے لیے دوبارہ قابل استعمال نمونوں کو فراہم کر کے حل کی ترقی کو تیز کرتا ہے۔
- MCP اور Azure خدمات کا استعمال کرتے ہوئے شعبہ مخصوص، AI سے چلنے والی ایپلیکیشنز بنانے کے لیے ایک خاکہ کے طور پر کام کرتا ہے۔

## حوالہ جات
- [Azure AI Travel Agents GitHub Repository](https://github.com/Azure-Samples/azure-ai-travel-agents)  
- [Azure OpenAI Service](https://azure.microsoft.com/en-us/products/ai-services/openai-service/)  
- [Azure AI Search](https://azure.microsoft.com/en-us/products/ai-services/ai-search/)  
- [Model Context Protocol (MCP)](https://modelcontextprotocol.io/)

**ڈسکلیمر**:  
اس دستاویز کا ترجمہ AI ترجمہ سروس [Co-op Translator](https://github.com/Azure/co-op-translator) کے ذریعے کیا گیا ہے۔ اگرچہ ہم درستگی کے لیے کوشاں ہیں، براہ کرم نوٹ کریں کہ خودکار ترجمے میں غلطیاں یا عدم درستیاں ہو سکتی ہیں۔ اصل دستاویز اپنی مادری زبان میں ہی معتبر ماخذ سمجھی جانی چاہیے۔ اہم معلومات کے لیے پیشہ ور انسانی ترجمہ کی سفارش کی جاتی ہے۔ ہم اس ترجمے کے استعمال سے پیدا ہونے والی کسی بھی غلط فہمی یا غلط تشریح کے ذمہ دار نہیں ہیں۔