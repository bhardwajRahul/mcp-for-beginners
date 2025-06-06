<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "494d87e1c4b9239c70f6a341fcc59a48",
  "translation_date": "2025-06-02T18:24:30+00:00",
  "source_file": "05-AdvancedTopics/README.md",
  "language_code": "fa"
}
-->
# موضوعات پیشرفته در MCP

این فصل به بررسی مجموعه‌ای از موضوعات پیشرفته در پیاده‌سازی پروتکل مدل کانتکست (MCP) می‌پردازد، از جمله ادغام چندرسانه‌ای، مقیاس‌پذیری، بهترین روش‌های امنیتی و ادغام سازمانی. این موضوعات برای ساخت برنامه‌های MCP مقاوم و آماده تولید که بتوانند نیازهای سیستم‌های هوش مصنوعی مدرن را برآورده کنند، بسیار حیاتی هستند.

## مرور کلی

این درس مفاهیم پیشرفته در پیاده‌سازی پروتکل مدل کانتکست را بررسی می‌کند و تمرکز آن بر ادغام چندرسانه‌ای، مقیاس‌پذیری، بهترین روش‌های امنیتی و ادغام سازمانی است. این موضوعات برای ساخت برنامه‌های MCP با کیفیت تولید که بتوانند نیازهای پیچیده در محیط‌های سازمانی را مدیریت کنند، ضروری هستند.

## اهداف یادگیری

تا پایان این درس، شما قادر خواهید بود:

- قابلیت‌های چندرسانه‌ای را در چارچوب‌های MCP پیاده‌سازی کنید
- معماری‌های مقیاس‌پذیر MCP را برای سناریوهای با تقاضای بالا طراحی کنید
- بهترین روش‌های امنیتی منطبق با اصول امنیتی MCP را اعمال کنید
- MCP را با سیستم‌ها و چارچوب‌های هوش مصنوعی سازمانی ادغام کنید
- عملکرد و قابلیت اطمینان را در محیط‌های تولید بهینه‌سازی کنید

## درس‌ها و پروژه‌های نمونه

| لینک | عنوان | توضیحات |
|------|-------|-------------|
| [5.1 Integration with Azure](./mcp-integration/README.md) | ادغام با Azure | یاد بگیرید چگونه MCP Server خود را در Azure ادغام کنید |
| [5.2 Multi modal sample](./mcp-multi-modality/README.md) | نمونه چندرسانه‌ای MCP | نمونه‌هایی برای پاسخ‌های صوتی، تصویری و چندرسانه‌ای |
| [5.3 MCP OAuth2 sample](../../../05-AdvancedTopics/mcp-oauth2-demo) | دمو OAuth2 MCP | برنامه حداقلی Spring Boot که OAuth2 را با MCP به عنوان سرور مجوز و سرور منابع نشان می‌دهد. صدور توکن امن، نقاط انتهایی محافظت شده، استقرار Azure Container Apps و ادغام مدیریت API را نمایش می‌دهد. |
| [5.4 Root Contexts](./mcp-root-contexts/README.md) | کانتکست‌های ریشه‌ای | بیشتر درباره کانتکست ریشه‌ای و نحوه پیاده‌سازی آن‌ها بیاموزید |
| [5.5 Routing](./mcp-routing/README.md) | مسیریابی | انواع مختلف مسیریابی را یاد بگیرید |
| [5.6 Sampling](./mcp-sampling/README.md) | نمونه‌برداری | نحوه کار با نمونه‌برداری را بیاموزید |
| [5.7 Scaling](./mcp-scaling/README.md) | مقیاس‌پذیری | درباره مقیاس‌پذیری بیاموزید |
| [5.8 Security](./mcp-security/README.md) | امنیت | سرور MCP خود را ایمن کنید |
| [5.9 Web Search sample](./web-search-mcp/README.md) | جستجوی وب MCP | سرور و کلاینت Python MCP که با SerpAPI برای جستجوی وب، اخبار، محصولات و پرسش و پاسخ در زمان واقعی ادغام شده‌اند. ارکستراسیون چندابزاری، ادغام API خارجی و مدیریت خطاهای قوی را نشان می‌دهد. |

## منابع اضافی

برای دریافت جدیدترین اطلاعات در مورد موضوعات پیشرفته MCP، به موارد زیر مراجعه کنید:
- [MCP Documentation](https://modelcontextprotocol.io/)
- [MCP Specification](https://spec.modelcontextprotocol.io/)
- [GitHub Repository](https://github.com/modelcontextprotocol)

## نکات کلیدی

- پیاده‌سازی‌های چندرسانه‌ای MCP قابلیت‌های هوش مصنوعی را فراتر از پردازش متن گسترش می‌دهند
- مقیاس‌پذیری برای استقرارهای سازمانی ضروری است و می‌توان آن را از طریق مقیاس‌پذیری افقی و عمودی برطرف کرد
- اقدامات امنیتی جامع از داده‌ها محافظت کرده و کنترل دسترسی مناسب را تضمین می‌کنند
- ادغام سازمانی با پلتفرم‌هایی مانند Azure OpenAI و Microsoft AI Foundry قابلیت‌های MCP را افزایش می‌دهد
- پیاده‌سازی‌های پیشرفته MCP از معماری‌های بهینه‌شده و مدیریت دقیق منابع بهره‌مند می‌شوند

## تمرین

یک پیاده‌سازی MCP با کیفیت سازمانی برای یک مورد استفاده خاص طراحی کنید:

1. نیازهای چندرسانه‌ای مورد استفاده خود را شناسایی کنید
2. کنترل‌های امنیتی لازم برای محافظت از داده‌های حساس را مشخص کنید
3. معماری مقیاس‌پذیری طراحی کنید که بتواند بارهای متغیر را مدیریت کند
4. نقاط ادغام با سیستم‌های هوش مصنوعی سازمانی را برنامه‌ریزی کنید
5. گلوگاه‌های احتمالی عملکرد و راهکارهای کاهش آن‌ها را مستندسازی کنید

## منابع بیشتر

- [مستندات Azure OpenAI](https://learn.microsoft.com/en-us/azure/ai-services/openai/)
- [مستندات Microsoft AI Foundry](https://learn.microsoft.com/en-us/ai-services/)

---

## مرحله بعد

- [5.1 MCP Integration](./mcp-integration/README.md)

**سلب مسئولیت**:  
این سند با استفاده از سرویس ترجمه هوش مصنوعی [Co-op Translator](https://github.com/Azure/co-op-translator) ترجمه شده است. در حالی که ما در تلاش برای دقت هستیم، لطفاً توجه داشته باشید که ترجمه‌های خودکار ممکن است حاوی خطا یا نواقصی باشند. سند اصلی به زبان بومی آن باید به عنوان منبع معتبر در نظر گرفته شود. برای اطلاعات حیاتی، ترجمه حرفه‌ای انسانی توصیه می‌شود. ما در قبال هرگونه سوء تفاهم یا تفسیر نادرست ناشی از استفاده از این ترجمه مسئولیتی نداریم.