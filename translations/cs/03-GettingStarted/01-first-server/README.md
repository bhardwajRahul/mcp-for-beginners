<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "262e6e510f0c3fe1e36180eadcd67c33",
  "translation_date": "2025-06-02T17:44:59+00:00",
  "source_file": "03-GettingStarted/01-first-server/README.md",
  "language_code": "cs"
}
-->
### -2- Vytvoření projektu

Nyní, když máte SDK nainstalované, pojďme pokračovat vytvořením projektu:

### -3- Vytvoření souborů projektu

### -4- Vytvoření kódu serveru

### -5- Přidání nástroje a zdroje

Přidejte nástroj a zdroj přidáním následujícího kódu:

### -6- Konečný kód

Přidejme poslední kód, který server potřebuje ke spuštění:

### -7- Testování serveru

Server spusťte následujícím příkazem:

### -8- Spuštění pomocí inspektoru

Inspektor je skvělý nástroj, který dokáže spustit váš server a umožní vám s ním interagovat, abyste mohli otestovat jeho funkčnost. Spusťme ho:

> [!NOTE]
> V poli "command" může být příkaz odlišný, protože obsahuje příkaz pro spuštění serveru s vaším konkrétním runtime.

Měli byste vidět následující uživatelské rozhraní:

![Connect](../../../../translated_images/connect.141db0b2bd05f096fb1dd91273771fd8b2469d6507656c3b0c9df4b3c5473929.cs.png)

1. Připojte se k serveru kliknutím na tlačítko Connect.  
   Po připojení byste měli vidět toto:

   ![Connected](../../../../translated_images/connected.73d1e042c24075d386cacdd4ee7cd748c16364c277d814e646ff2f7b5eefde85.cs.png)

2. Vyberte "Tools" a poté "listTools", měli byste vidět tlačítko "Add", klikněte na něj a vyplňte hodnoty parametrů.

   Měli byste obdržet následující odpověď, tedy výsledek z nástroje "add":

   ![Result of running add](../../../../translated_images/ran-tool.a5a6ee878c1369ec1e379b81053395252a441799dbf23416c36ddf288faf8249.cs.png)

Gratulujeme, podařilo se vám vytvořit a spustit váš první server!

### Oficiální SDK

MCP nabízí oficiální SDK pro několik jazyků:
- [C# SDK](https://github.com/modelcontextprotocol/csharp-sdk) – udržováno ve spolupráci s Microsoftem
- [Java SDK](https://github.com/modelcontextprotocol/java-sdk) – udržováno ve spolupráci se Spring AI
- [TypeScript SDK](https://github.com/modelcontextprotocol/typescript-sdk) – oficiální implementace v TypeScriptu
- [Python SDK](https://github.com/modelcontextprotocol/python-sdk) – oficiální implementace v Pythonu
- [Kotlin SDK](https://github.com/modelcontextprotocol/kotlin-sdk) – oficiální implementace v Kotlinu
- [Swift SDK](https://github.com/modelcontextprotocol/swift-sdk) – udržováno ve spolupráci s Loopwork AI
- [Rust SDK](https://github.com/modelcontextprotocol/rust-sdk) – oficiální implementace v Rustu

## Hlavní poznatky

- Nastavení vývojového prostředí MCP je jednoduché díky SDK specifickým pro jednotlivé jazyky
- Vytváření MCP serverů zahrnuje tvorbu a registraci nástrojů s jasně definovanými schématy
- Testování a ladění jsou nezbytné pro spolehlivé MCP implementace

## Ukázky

- [Java Calculator](../samples/java/calculator/README.md)
- [.Net Calculator](../../../../03-GettingStarted/samples/csharp)
- [JavaScript Calculator](../samples/javascript/README.md)
- [TypeScript Calculator](../samples/typescript/README.md)
- [Python Calculator](../../../../03-GettingStarted/samples/python)

## Zadání

Vytvořte jednoduchý MCP server s nástrojem dle vašeho výběru:
1. Implementujte nástroj ve vámi preferovaném jazyce (.NET, Java, Python nebo JavaScript).
2. Definujte vstupní parametry a návratové hodnoty.
3. Spusťte inspektor, abyste ověřili, že server funguje správně.
4. Otestujte implementaci s různými vstupy.

## Řešení

[Řešení](./solution/README.md)

## Další zdroje

- [Build Agents using Model Context Protocol on Azure](https://learn.microsoft.com/azure/developer/ai/intro-agents-mcp)
- [Remote MCP with Azure Container Apps (Node.js/TypeScript/JavaScript)](https://learn.microsoft.com/samples/azure-samples/mcp-container-ts/mcp-container-ts/)
- [.NET OpenAI MCP Agent](https://learn.microsoft.com/samples/azure-samples/openai-mcp-agent-dotnet/openai-mcp-agent-dotnet/)

## Co dál

Další krok: [Getting Started with MCP Clients](/03-GettingStarted/02-client/README.md)

**Prohlášení o vyloučení odpovědnosti**:  
Tento dokument byl přeložen pomocí AI překladatelské služby [Co-op Translator](https://github.com/Azure/co-op-translator). I když usilujeme o přesnost, mějte prosím na paměti, že automatizované překlady mohou obsahovat chyby nebo nepřesnosti. Původní dokument v jeho mateřském jazyce by měl být považován za závazný zdroj. Pro důležité informace se doporučuje profesionální lidský překlad. Nejsme odpovědní za jakékoli nedorozumění nebo nesprávné výklady vyplývající z použití tohoto překladu.