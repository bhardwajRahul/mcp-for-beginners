<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "a0acf3093691b1cfcc008a8c6648ea26",
  "translation_date": "2025-06-13T06:41:45+00:00",
  "source_file": "03-GettingStarted/02-client/README.md",
  "language_code": "mr"
}
-->
मागील कोडमध्ये आपण:

- लायब्ररी इम्पोर्ट केल्या
- क्लायंटची एक उदाहरण तयार केली आणि stdio वापरून ट्रान्सपोर्टसाठी कनेक्ट केलं.
- प्रॉम्प्ट्स, रिसोर्सेस आणि टूल्सची यादी केली आणि सर्वांना invoke केलं.

इतकंच, एक असा क्लायंट तयार केला जो MCP Server शी संवाद साधू शकतो.

आता पुढील व्यायाम विभागात आपण प्रत्येक कोडचा भाग नीट समजून घेऊ आणि काय चाललंय ते स्पष्ट करू.

## व्यायाम: क्लायंट लिहिणे

जसं वर सांगितलं, आपण कोड नीट समजून घेऊ आणि हव्यास असल्यास एकत्र कोडही करू शकता.

### -1- लायब्ररी इम्पोर्ट करणे

आपल्याला आवश्यक लायब्ररी इम्पोर्ट करूया, आपल्याला client आणि निवडलेल्या ट्रान्सपोर्ट प्रोटोकॉल stdio यांचे संदर्भ हवेत. stdio ही प्रोटोकॉल आहे जी स्थानिक मशीनवर चालणाऱ्या गोष्टींसाठी आहे. SSE हा आणखी एक ट्रान्सपोर्ट प्रोटोकॉल आहे जो पुढील अध्यायांमध्ये दाखवू, पण सध्या stdio सोबतच पुढे जाऊया.

चला, आता उदाहरण तयार करण्याकडे वळूया.

### -2- क्लायंट आणि ट्रान्सपोर्टचे उदाहरण तयार करणे

आपल्याला ट्रान्सपोर्टचे आणि क्लायंटचे उदाहरण तयार करावे लागेल:

### -3- सर्व्हरच्या फिचर्सची यादी करणे

आता आपल्याकडे असा क्लायंट आहे जो प्रोग्राम चालवल्यावर कनेक्ट होऊ शकतो. मात्र, तो त्याच्या फिचर्सची यादी करत नाही, त्यामुळे ती पुढे करूया:

आता आपण सर्व फिचर्स कॅप्चर केले आहेत. प्रश्न असा की आपण त्यांचा वापर कधी करणार? हा क्लायंट सोपा आहे, म्हणजे आपल्याला जेव्हा हवं तेव्हा स्पष्टपणे फिचर्स कॉल कराव्या लागतील. पुढील अध्यायात आपण अधिक प्रगत क्लायंट तयार करू जो स्वतःच्या मोठ्या भाषा मॉडेल (LLM) शी जोडलेला असेल. सध्या तरी, पाहूया सर्व्हरवरील फिचर्स कसे invoke करायचे:

### -4- फिचर्स invoke करणे

फिचर्स invoke करण्यासाठी योग्य अर्ग्युमेंट्स देणे गरजेचे आहे आणि काही वेळा आपण जे invoke करायचं आहे त्याचं नाव देखील दिलं पाहिजे.

### -5- क्लायंट चालवणे

क्लायंट चालवण्यासाठी, टर्मिनलमध्ये खालील कमांड टाइप करा:

## असाइनमेंट

या असाइनमेंटमध्ये, आपण जे काही क्लायंट तयार करण्यात शिकलात ते वापरून स्वतःचा क्लायंट तयार कराल.

खाली एक सर्व्हर आहे ज्याला आपण आपल्या क्लायंट कोडद्वारे कॉल करणार आहात, पाहा काय करता येईल त्यात अधिक फिचर्स जोडून त्याला अधिक मनोरंजक बनवता येईल का.

## समाधान

[Solution](./solution/README.md)

## मुख्य मुद्दे

या अध्यायातील मुख्य मुद्दे क्लायंटबद्दल:

- क्लायंटचा वापर सर्व्हरवरील फिचर्स शोधण्यासाठी आणि invoke करण्यासाठी केला जातो.
- क्लायंट स्वतः सुरू होऊ शकतो (जसे या अध्यायात), पण चालू असलेल्या सर्व्हरशी देखील कनेक्ट होऊ शकतो.
- सर्व्हरच्या क्षमतांची चाचणी करण्याचा उत्तम मार्ग आहे, Inspector सारख्या पर्यायांबरोबर.

## अतिरिक्त संसाधने

- [MCP मध्ये क्लायंट तयार करणे](https://modelcontextprotocol.io/quickstart/client)

## नमुने

- [Java Calculator](../samples/java/calculator/README.md)
- [.Net Calculator](../../../../03-GettingStarted/samples/csharp)
- [JavaScript Calculator](../samples/javascript/README.md)
- [TypeScript Calculator](../samples/typescript/README.md)
- [Python Calculator](../../../../03-GettingStarted/samples/python)

## पुढे काय

- पुढे: [LLM सह क्लायंट तयार करणे](/03-GettingStarted/03-llm-client/README.md)

**अस्वीकरण**:  
हा दस्तऐवज AI अनुवाद सेवा [Co-op Translator](https://github.com/Azure/co-op-translator) चा वापर करून अनुवादित केला आहे. आम्ही अचूकतेसाठी प्रयत्न करतो, तरी कृपया लक्षात ठेवा की स्वयंचलित अनुवादांमध्ये चुका किंवा अचूकतेत फरक असू शकतो. मूळ दस्तऐवज त्याच्या स्थानिक भाषेत अधिकृत स्रोत मानला जावा. महत्त्वाच्या माहितीसाठी व्यावसायिक मानवी अनुवादाची शिफारस केली जाते. या अनुवादाच्या वापरामुळे होणाऱ्या कोणत्याही गैरसमजुती किंवा चुकीच्या अर्थलाभाबद्दल आम्ही जबाबदार नाही.