<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "b547c992c056d4296d641ed8ec2cc4cb",
  "translation_date": "2025-06-02T17:17:12+00:00",
  "source_file": "03-GettingStarted/README.md",
  "language_code": "ru"
}
-->
## Начало работы  

Этот раздел состоит из нескольких уроков:

- **-1- Ваш первый сервер**, в этом первом уроке вы научитесь создавать свой первый сервер и исследовать его с помощью инструмента инспектора — ценного способа тестирования и отладки вашего сервера, [к уроку](/03-GettingStarted/01-first-server/README.md)

- **-2- Клиент**, в этом уроке вы узнаете, как написать клиента, который сможет подключаться к вашему серверу, [к уроку](/03-GettingStarted/02-client/README.md)

- **-3- Клиент с LLM**, ещё более продвинутый способ написания клиента — добавить в него LLM, чтобы он мог "договариваться" с вашим сервером о дальнейших действиях, [к уроку](/03-GettingStarted/03-llm-client/README.md)

- **-4- Использование режима агента GitHub Copilot сервера в Visual Studio Code**. Здесь мы рассмотрим запуск нашего MCP сервера из Visual Studio Code, [к уроку](/03-GettingStarted/04-vscode/README.md)

- **-5- Использование SSE (Server Sent Events)**. SSE — это стандарт для потоковой передачи данных от сервера к клиенту, позволяющий серверам отправлять обновления в реальном времени по HTTP, [к уроку](/03-GettingStarted/05-sse-server/README.md)

- **-6- Использование AI Toolkit для VSCode** для потребления и тестирования ваших MCP клиентов и серверов, [к уроку](/03-GettingStarted/06-aitk/README.md)

- **-7 Тестирование**. Здесь мы особенно сосредоточимся на различных способах тестирования нашего сервера и клиента, [к уроку](/03-GettingStarted/07-testing/README.md)

- **-8- Развертывание**. В этой главе рассмотрим различные способы развертывания ваших MCP решений, [к уроку](/03-GettingStarted/08-deployment/README.md)


Model Context Protocol (MCP) — это открытый протокол, стандартизирующий способ предоставления контекста LLM приложениями. Представьте MCP как USB-C порт для AI-приложений — он обеспечивает единый способ подключения AI моделей к разным источникам данных и инструментам.

## Цели обучения

К концу этого урока вы сможете:

- Настроить среды разработки MCP на C#, Java, Python, TypeScript и JavaScript
- Создавать и развёртывать базовые MCP серверы с пользовательскими функциями (ресурсы, подсказки и инструменты)
- Создавать хост-приложения, которые подключаются к MCP серверам
- Тестировать и отлаживать реализации MCP
- Понимать распространённые проблемы при настройке и способы их решения
- Подключать свои реализации MCP к популярным LLM сервисам

## Настройка вашей среды MCP

Прежде чем начать работу с MCP, важно подготовить среду разработки и понять базовый рабочий процесс. В этом разделе вы пройдёте начальные шаги настройки для плавного старта с MCP.

### Требования

Перед тем, как приступить к разработке MCP, убедитесь, что у вас есть:

- **Среда разработки**: для выбранного языка (C#, Java, Python, TypeScript или JavaScript)
- **IDE/редактор**: Visual Studio, Visual Studio Code, IntelliJ, Eclipse, PyCharm или любой современный редактор кода
- **Менеджеры пакетов**: NuGet, Maven/Gradle, pip или npm/yarn
- **API ключи**: для любых AI сервисов, которые вы планируете использовать в своих хост-приложениях


### Официальные SDK

В следующих главах вы увидите решения, построенные с использованием Python, TypeScript, Java и .NET. Вот все официально поддерживаемые SDK.

MCP предоставляет официальные SDK для нескольких языков:
- [C# SDK](https://github.com/modelcontextprotocol/csharp-sdk) — поддерживается совместно с Microsoft
- [Java SDK](https://github.com/modelcontextprotocol/java-sdk) — поддерживается совместно со Spring AI
- [TypeScript SDK](https://github.com/modelcontextprotocol/typescript-sdk) — официальная реализация на TypeScript
- [Python SDK](https://github.com/modelcontextprotocol/python-sdk) — официальная реализация на Python
- [Kotlin SDK](https://github.com/modelcontextprotocol/kotlin-sdk) — официальная реализация на Kotlin
- [Swift SDK](https://github.com/modelcontextprotocol/swift-sdk) — поддерживается совместно с Loopwork AI
- [Rust SDK](https://github.com/modelcontextprotocol/rust-sdk) — официальная реализация на Rust

## Основные выводы

- Настройка среды разработки MCP проста с использованием SDK, ориентированных на конкретные языки
- Создание MCP серверов включает создание и регистрацию инструментов с чёткими схемами
- MCP клиенты подключаются к серверам и моделям для расширения функционала
- Тестирование и отладка необходимы для надёжных реализаций MCP
- Варианты развертывания варьируются от локальной разработки до облачных решений

## Практика

У нас есть набор примеров, которые дополняют упражнения, представленные во всех главах этого раздела. Кроме того, у каждой главы есть свои упражнения и задания.

- [Java Калькулятор](./samples/java/calculator/README.md)
- [.Net Калькулятор](../../../03-GettingStarted/samples/csharp)
- [JavaScript Калькулятор](./samples/javascript/README.md)
- [TypeScript Калькулятор](./samples/typescript/README.md)
- [Python Калькулятор](../../../03-GettingStarted/samples/python)

## Дополнительные ресурсы

- [Создание агентов с использованием Model Context Protocol на Azure](https://learn.microsoft.com/azure/developer/ai/intro-agents-mcp)
- [Удалённый MCP с Azure Container Apps (Node.js/TypeScript/JavaScript)](https://learn.microsoft.com/samples/azure-samples/mcp-container-ts/mcp-container-ts/)
- [.NET OpenAI MCP агент](https://learn.microsoft.com/samples/azure-samples/openai-mcp-agent-dotnet/openai-mcp-agent-dotnet/)

## Что дальше

Далее: [Создание вашего первого MCP сервера](/03-GettingStarted/01-first-server/README.md)

**Отказ от ответственности**:  
Этот документ был переведен с помощью сервиса автоматического перевода [Co-op Translator](https://github.com/Azure/co-op-translator). Несмотря на наши усилия обеспечить точность, пожалуйста, имейте в виду, что автоматические переводы могут содержать ошибки или неточности. Оригинальный документ на его исходном языке следует считать авторитетным источником. Для получения критически важной информации рекомендуется использовать профессиональный перевод, выполненный человеком. Мы не несем ответственности за любые недоразумения или неправильные толкования, возникшие в результате использования данного перевода.