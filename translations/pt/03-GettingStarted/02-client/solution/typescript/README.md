<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "fae57a69c2b62cb7d92ff12da65f36c3",
  "translation_date": "2025-05-17T10:08:16+00:00",
  "source_file": "03-GettingStarted/02-client/solution/typescript/README.md",
  "language_code": "pt"
}
-->
# Executando este exemplo

Recomenda-se instalar `uv`, mas não é obrigatório, veja [instruções](https://docs.astral.sh/uv/#highlights)

## -1- Instale as dependências

```bash
npm install
```

## -3- Execute o servidor

```bash
npm run build
```

## -4- Execute o cliente

```sh
npm run client
```

Você deverá ver um resultado similar a:

```text
Prompt:  {
  type: 'text',
  text: 'Please review this code:\n\nconsole.log("hello");'
}
Resource template:  file
Tool result:  { content: [ { type: 'text', text: '9' } ] }
```

**Aviso Legal**:  
Este documento foi traduzido usando o serviço de tradução por IA [Co-op Translator](https://github.com/Azure/co-op-translator). Embora nos esforcemos pela precisão, esteja ciente de que traduções automatizadas podem conter erros ou imprecisões. O documento original em seu idioma nativo deve ser considerado a fonte autorizada. Para informações críticas, recomenda-se a tradução profissional por humanos. Não nos responsabilizamos por quaisquer mal-entendidos ou interpretações errôneas decorrentes do uso desta tradução.