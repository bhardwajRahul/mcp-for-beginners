<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "4bf553c18e7e226c3d76ab0cde627d26",
  "translation_date": "2025-05-20T21:02:50+00:00",
  "source_file": "01-CoreConcepts/README.md",
  "language_code": "mr"
}
-->
# 📖 MCP कोर संकल्पना: AI इंटिग्रेशनसाठी मॉडेल कॉन्टेक्स्ट प्रोटोकॉलमध्ये पारंगत होणे

Model Context Protocol (MCP) हा एक शक्तिशाली, मानकीकृत फ्रेमवर्क आहे जो Large Language Models (LLMs) आणि बाह्य साधने, अ‍ॅप्लिकेशन्स, आणि डेटा स्रोत यांच्यातील संवाद अधिक प्रभावी करतो. हा SEO-अनुकूल मार्गदर्शक तुम्हाला MCP च्या मुख्य संकल्पना समजावून सांगेल, ज्यामुळे तुम्हाला त्याची क्लायंट-सर्व्हर आर्किटेक्चर, आवश्यक घटक, संवाद प्रक्रिया आणि अंमलबजावणीतील सर्वोत्तम पद्धती समजतील.

## आढावा

या धड्यात Model Context Protocol (MCP) च्या मूलभूत आर्किटेक्चर आणि घटकांचा अभ्यास केला जाईल. तुम्हाला क्लायंट-सर्व्हर आर्किटेक्चर, मुख्य घटक, आणि संवाद यंत्रणा याबद्दल शिकायला मिळेल ज्या MCP च्या संवादासाठी आधारभूत आहेत.

## 👩‍🎓 मुख्य शिक्षण उद्दिष्टे

या धड्याच्या शेवटी तुम्ही:

- MCP च्या क्लायंट-सर्व्हर आर्किटेक्चरची समज प्राप्त कराल.
- Hosts, Clients, आणि Servers यांची भूमिका आणि जबाबदाऱ्या ओळखाल.
- MCP ला लवचिक इंटिग्रेशन लेयर बनवणाऱ्या मुख्य वैशिष्ट्यांचा अभ्यास कराल.
- MCP इकोसिस्टममध्ये माहिती कशी वाहते ते शिकाल.
- .NET, Java, Python, आणि JavaScript मध्ये कोड उदाहरणांद्वारे व्यावहारिक माहिती मिळवाल.

## 🔎 MCP आर्किटेक्चर: सखोल पाहणी

MCP इकोसिस्टम क्लायंट-सर्व्हर मॉडेलवर आधारित आहे. हा मॉड्युलर स्ट्रक्चर AI अ‍ॅप्लिकेशन्सना साधने, डेटाबेस, API, आणि संदर्भात्मक स्रोतांशी प्रभावीपणे संवाद साधण्याची परवानगी देतो. चला या आर्किटेक्चरचे मुख्य घटक तपासूया.

### 1. Hosts

Model Context Protocol (MCP) मध्ये Hosts ही मुख्य भूमिका बजावतात, ज्याद्वारे वापरकर्ते प्रोटोकॉलशी संवाद साधतात. Hosts हे अ‍ॅप्लिकेशन्स किंवा पर्यावरणे असतात जे MCP सर्व्हर्सशी कनेक्शन सुरू करतात आणि डेटा, साधने, आणि प्रॉम्प्ट्स वापरतात. उदाहरणार्थ, Visual Studio Code सारखे IDEs, Claude Desktop सारखी AI साधने, किंवा विशिष्ट कामांसाठी तयार केलेले कस्टम एजंट्स.

**Hosts** हे LLM अ‍ॅप्लिकेशन्स आहेत जे कनेक्शन सुरू करतात. ते:

- AI मॉडेल्सना प्रतिसाद तयार करण्यासाठी चालवतात किंवा संवाद साधतात.
- MCP सर्व्हर्सशी कनेक्शन सुरू करतात.
- संभाषणाचा प्रवाह आणि वापरकर्ता इंटरफेस व्यवस्थापित करतात.
- परवानग्या आणि सुरक्षा निर्बंध नियंत्रित करतात.
- डेटा शेअरिंग आणि साधन चालवण्याबाबत वापरकर्त्यांची संमती हाताळतात.

### 2. Clients

Clients हे महत्त्वाचे घटक आहेत जे Hosts आणि MCP सर्व्हर्समधील संवाद सुलभ करतात. Clients मध्यस्थ म्हणून काम करतात, Hosts ला MCP सर्व्हर्सकडून दिल्या जाणाऱ्या कार्यक्षमतेचा वापर करण्यास मदत करतात. ते MCP आर्किटेक्चरमध्ये संवाद सुरळीत आणि डेटा देवाणघेवाण प्रभावी बनवतात.

**Clients** हे host अ‍ॅप्लिकेशनमधील कनेक्टर्स आहेत. ते:

- सर्व्हर्सना प्रॉम्प्ट्स/सूचना सह विनंत्या पाठवतात.
- सर्व्हर्सशी क्षमता समजुती करतात.
- मॉडेलकडून साधन चालवण्याच्या विनंत्या व्यवस्थापित करतात.
- वापरकर्त्यांना प्रतिसाद प्रक्रिया करून दाखवतात.

### 3. Servers

Servers हे MCP clients कडून येणाऱ्या विनंत्या हाताळतात आणि योग्य प्रतिसाद देतात. ते डेटा पुनर्प्राप्ती, साधन चालवणे, आणि प्रॉम्प्ट तयार करणे यांसारख्या विविध ऑपरेशन्सचे व्यवस्थापन करतात. Servers हे Clients आणि Hosts मधील संवाद प्रभावी आणि विश्वासार्ह ठेवतात, संवाद प्रक्रियेची अखंडता राखतात.

**Servers** हे सेवा आहेत ज्या संदर्भ आणि क्षमता पुरवतात. ते:

- उपलब्ध वैशिष्ट्ये (संसाधने, प्रॉम्प्ट्स, साधने) नोंदवतात.
- क्लायंटकडून साधन कॉल्स प्राप्त करून चालवतात.
- मॉडेल प्रतिसाद सुधारण्यासाठी संदर्भात्मक माहिती पुरवतात.
- आउटपुट क्लायंटकडे परत करतात.
- आवश्यकतेनुसार संवादांमध्ये स्थिती राखतात.

Servers कोणालाही विकसित करता येऊ शकतात जे मॉडेलच्या क्षमतांना विशेष कार्यक्षमता देतात.

### 4. Server Features

Model Context Protocol (MCP) मधील Servers क्लायंट्स, Hosts, आणि भाषा मॉडेल्स यांच्यात समृद्ध संवाद सक्षम करणारे मूलभूत घटक पुरवतात. हे वैशिष्ट्ये MCP च्या क्षमतांना सुधारण्यासाठी रचलेले संदर्भ, साधने, आणि प्रॉम्प्ट्स देतात.

MCP सर्व्हर्स खालीलपैकी कोणतीही वैशिष्ट्ये देऊ शकतात:

#### 📑 Resources 

MCP मधील Resources मध्ये वेगवेगळ्या प्रकारच्या संदर्भ आणि डेटा समाविष्ट आहेत जे वापरकर्ते किंवा AI मॉडेल्स वापरू शकतात. यात समाविष्ट आहेत:

- **संदर्भात्मक डेटा**: माहिती आणि संदर्भ जे वापरकर्ते किंवा AI मॉडेल्स निर्णय घेण्यासाठी आणि कार्ये पार पाडण्यासाठी वापरतात.
- **ज्ञान भांडार आणि दस्तऐवज संच**: संरचित आणि असंरचित डेटा, जसे की लेख, मॅन्युअल्स, संशोधन पेपर्स, जे महत्त्वाची माहिती पुरवतात.
- **स्थानिक फायली आणि डेटाबेस**: उपकरणांवर किंवा डेटाबेसमध्ये साठवलेला डेटा, जो प्रक्रिया आणि विश्लेषणासाठी उपलब्ध आहे.
- **API आणि वेब सेवा**: बाह्य इंटरफेस आणि सेवा ज्या अतिरिक्त डेटा आणि कार्यक्षमता पुरवतात, विविध ऑनलाइन स्रोत आणि साधनांसह इंटिग्रेशन सक्षम करतात.

उदाहरणार्थ, डेटाबेस स्कीमा किंवा फाइल जी खालीलप्रमाणे प्रवेश करता येऊ शकते:

```text
file://log.txt
database://schema
```

### 🤖 Prompts

MCP मधील Prompts मध्ये विविध पूर्व-निर्धारित टेम्पलेट्स आणि संवाद नमुने असतात जे वापरकर्त्यांच्या कामकाजाला सुलभ करतात आणि संवाद सुधारतात. यात समाविष्ट आहेत:

- **टेम्प्लेटेड मेसेजेस आणि वर्कफ्लोज**: पूर्व-रचलेल्या संदेश आणि प्रक्रिया ज्या वापरकर्त्यांना विशिष्ट कार्यांमध्ये मार्गदर्शन करतात.
- **पूर्व-निर्धारित संवाद नमुने**: क्रियांच्या आणि प्रतिसादांच्या मानकीकृत साखळ्या ज्या सातत्यपूर्ण आणि कार्यक्षम संवाद सुलभ करतात.
- **विशिष्ट संभाषण टेम्प्लेट्स**: विशिष्ट प्रकारच्या संभाषणांसाठी सानुकूल टेम्प्लेट्स, जे संदर्भानुसार योग्य संवाद सुनिश्चित करतात.

प्रॉम्प्ट टेम्प्लेट खालीलप्रमाणे दिसू शकते:

```markdown
Generate a product slogan based on the following {{product}} with the following {{keywords}}
```

#### ⛏️ Tools

MCP मधील Tools ही AI मॉडेल्स वापरू शकणाऱ्या फंक्शन्स आहेत ज्याद्वारे विशिष्ट कामे पार पडतात. ही साधने AI मॉडेलच्या क्षमतांना वाढवण्यासाठी रचलेली असतात आणि विश्वासार्ह ऑपरेशन्स पुरवतात. मुख्य वैशिष्ट्ये:

- **AI मॉडेल चालवण्यासाठी फंक्शन्स**: Tools हे executable फंक्शन्स आहेत जे AI मॉडेल विविध कामांसाठी वापरू शकते.
- **विशिष्ट नाव आणि वर्णन**: प्रत्येक साधनाला वेगळं नाव आणि त्याच्या कार्याचे तपशीलवार वर्णन असते.
- **पॅरामीटर्स आणि आउटपुट्स**: Tools विशिष्ट पॅरामीटर्स स्वीकारतात आणि रचलेल्या आउटपुट्स परत करतात, ज्यामुळे परिणाम सातत्यपूर्ण राहतात.
- **स्वतंत्र फंक्शन्स**: Tools वेब शोध, गणना, डेटाबेस क्वेरी सारखी स्वतंत्र कार्ये पार पाडतात.

उदाहरणार्थ एक Tool खालीलप्रमाणे दिसू शकते:

```typescript
server.tool(
  "GetProducts",
  {
    pageSize: z.string().optional(),
    pageCount: z.string().optional()
  }, () => {
    // return results from API
  }
)
```

## Client Features

MCP मध्ये Clients सर्व्हर्सना अनेक मुख्य वैशिष्ट्ये पुरवतात ज्यामुळे प्रोटोकॉलमधील एकूण कार्यक्षमता आणि संवाद सुधारतो. त्यातील एक महत्त्वाचा भाग म्हणजे Sampling.

### 👉 Sampling

- **सर्व्हर-प्रेरित एजंटिक वर्तन**: Clients सर्व्हर्सना स्वयंचलितपणे विशिष्ट क्रिया किंवा वर्तन सुरू करण्याची परवानगी देतात, ज्यामुळे सिस्टमची गतिशील क्षमता वाढते.
- **Recursive LLM संवाद**: हे वैशिष्ट्य मोठ्या भाषा मॉडेल्सशी पुनरावृत्ती संवाद करण्यास परवानगी देते, ज्यामुळे अधिक गुंतागुंतीचे आणि पुनरावृत्ती असलेले कार्य करता येते.
- **अधिक मॉडेल पूर्णता मागवणे**: सर्व्हर्स मॉडेलकडून अधिक प्रतिसाद मागवू शकतात, ज्यामुळे प्रतिसाद अधिक सखोल आणि संदर्भानुसार योग्य होतो.

## MCP मधील माहिती प्रवाह

Model Context Protocol (MCP) मध्ये Hosts, Clients, Servers, आणि मॉडेल्स यांच्यातील माहितीचा संरचित प्रवाह निश्चित केला आहे. हा प्रवाह समजून घेतल्याने वापरकर्त्यांच्या विनंत्या कशा प्रक्रिया केल्या जातात आणि बाह्य साधने व डेटा कसे मॉडेल प्रतिसादांमध्ये समाकलित होतात हे स्पष्ट होते.

- **Host कनेक्शन सुरू करतो**  
  Host अ‍ॅप्लिकेशन (जसे IDE किंवा चॅट इंटरफेस) MCP सर्व्हरशी कनेक्शन स्थापन करतो, सहसा STDIO, WebSocket, किंवा इतर समर्थित ट्रान्सपोर्टद्वारे.

- **क्षमता समजुती करणे**  
  Host मधील client आणि server त्यांच्या समर्थित वैशिष्ट्ये, साधने, संसाधने, आणि प्रोटोकॉल आवृत्त्यांविषयी माहिती देवाणघेवाण करतात. त्यामुळे दोन्ही बाजूंना सत्रासाठी उपलब्ध क्षमता समजतात.

- **वापरकर्ता विनंती**  
  वापरकर्ता Host शी संवाद साधतो (उदा. प्रॉम्प्ट किंवा कमांड टाकतो). Host हा इनपुट घेऊन client कडे पाठवतो.

- **संसाधन किंवा साधन वापर**  
  - Client अधिक संदर्भ किंवा संसाधने मागू शकतो (जसे फाइल्स, डेटाबेस नोंदी, ज्ञान लेख) जेणेकरून मॉडेलची समज वाढेल.
  - जर मॉडेलला साधन वापरण्याची गरज वाटली (उदा. डेटा मिळवणे, गणना करणे, API कॉल करणे), तर client सर्व्हरला साधन वापरण्याची विनंती पाठवतो, ज्यात साधनाचे नाव आणि पॅरामीटर्स दिलेले असतात.

- **सर्व्हर अंमलबजावणी**  
  सर्व्हर संसाधन किंवा साधन विनंती प्राप्त करतो, आवश्यक ऑपरेशन्स (फंक्शन चालवणे, डेटाबेस क्वेरी, फाइल पुनर्प्राप्ती) पार पाडतो, आणि निकाल client कडे संरचित स्वरूपात परत पाठवतो.

- **प्रतिसाद निर्मिती**  
  Client सर्व्हरच्या प्रतिसादांना (संसाधन डेटा, साधन आउटपुट्स) चालू मॉडेल संवादात समाकलित करतो. मॉडेल या माहितीचा वापर करून संपूर्ण आणि संदर्भानुसार योग्य प्रतिसाद तयार करतो.

- **परिणाम सादरीकरण**  
  Host अंतिम आउटपुट client कडून प्राप्त करून वापरकर्त्याला सादर करतो, ज्यामध्ये मॉडेलने तयार केलेला मजकूर आणि साधन चालवण्याचे निकाल दोन्ही असू शकतात.

हा प्रवाह MCP ला प्रगत, संवादात्मक, आणि संदर्भ-जाणणाऱ्या AI अ‍ॅप्लिकेशन्सना सक्षम करतो, ज्यामुळे मॉडेल्सना बाह्य साधने आणि डेटा स्रोतांशी सहज जोडता येते.

## प्रोटोकॉल तपशील

MCP (Model Context Protocol) [JSON-RPC 2.0](https://www.jsonrpc.org/) वर आधारित आहे, जे hosts, clients, आणि servers यांच्यातील संवादासाठी मानकीकृत, भाषा-स्वतंत्र संदेश स्वरूप प्रदान करते. हे आधार विविध प्लॅटफॉर्म्स आणि प्रोग्रामिंग भाषांमध्ये विश्वासार्ह, संरचित, आणि विस्तृत संवाद सक्षम करते.

### मुख्य प्रोटोकॉल वैशिष्ट्ये

MCP JSON-RPC 2.0 मध्ये साधने कॉल करणे, संसाधने प्रवेश करणे, आणि प्रॉम्प्ट व्यवस्थापनासाठी अतिरिक्त नियम जोडते. हे STDIO, WebSocket, SSE यांसारख्या अनेक ट्रान्सपोर्ट लेयर्सना समर्थन देते आणि सुरक्षित, विस्तृत, आणि भाषा-स्वतंत्र संवाद सक्षम करते.

#### 🧢 बेस प्रोटोकॉल

- **JSON-RPC संदेश स्वरूप**: सर्व विनंत्या आणि प्रतिसाद JSON-RPC 2.0 च्या तपशीलांनुसार असतात, ज्यामुळे मेथड कॉल्स, पॅरामीटर्स, निकाल, आणि त्रुटी हाताळणी सुसंगत राहते.
- **स्थितीपूर्ण कनेक्शन**: MCP सत्र अनेक विनंत्यांमध्ये स्थिती राखतात, सतत संभाषणे, संदर्भ संचय, आणि संसाधन व्यवस्थापनासाठी.
- **क्षमता समजुती**: कनेक्शन सेटअप दरम्यान, clients आणि servers त्यांच्या समर्थित वैशिष्ट्ये, प्रोटोकॉल आवृत्त्या, उपलब्ध साधने, आणि संसाधने याबद्दल माहिती देवाणघेवाण करतात. त्यामुळे दोन्ही बाजूंना एकमेकांच्या क्षमतांचा समज येतो आणि ते अनुकूल होऊ शकतात.

#### ➕ अतिरिक्त उपयुक्तता

खाली MCP काही अतिरिक्त उपयुक्तता आणि प्रोटोकॉल विस्तार देतो जे विकासकांचा अनुभव सुधारतात आणि प्रगत परिस्थिती सक्षम करतात:

- **कॉन्फिगरेशन पर्याय**: MCP सत्राच्या पॅरामीटर्सचे डायनॅमिक कॉन्फिगरेशन (जसे साधन परवानग्या, संसाधन प्रवेश, मॉडेल सेटिंग्ज) प्रत्येक संवादासाठी सानुकूल करता येते.
- **प्रगती ट्रॅकिंग**: दीर्घकालीन ऑपरेशन्स प्रगती अद्यतने देऊ शकतात, ज्यामुळे प्रतिसाद देणारे UI आणि वापरकर्ता अनुभव सुधारतो.
- **विनंती रद्द करणे**: Clients चालू असलेल्या विनंत्या रद्द करू शकतात, ज्यामुळे वापरकर्ते अनावश्यक किंवा जास्त वेळ घेणाऱ्या ऑपरेशन्स थांबवू शकतात.
- **त्रुटी अहवाल**: मानकीकृत त्रुटी संदेश आणि कोड्स समस्या ओळखण्यासाठी, अपयश हाताळण्यासाठी, आणि वापरकर्ते व विकासकांना उपयुक्त अभिप्राय देण्यासाठी मदत करतात.
- **लॉगिंग**: Clients आणि Servers दोघेही प्रोटोकॉल संवादासाठी ऑडिटिंग, डीबगिंग, आणि मॉनिटरिंगसाठी संरचित लॉग्स तयार करू शकतात.

या प्रोटोकॉल वैशिष्ट्यांचा वापर करून MCP भाषा मॉडेल्स आणि बाह्य साधने किंवा डेटा स्रोतांमधील संवाद मजबूत, सुरक्षित, आणि लवचिक बनवतो.

### 🔐 सुरक्षा विचार

MCP ची अंमलबजावणी करताना सुरक्षित आणि विश्वासार्ह संवाद सुनिश्चित करण्यासाठी काही महत्त्वाचे सुरक्षा तत्त्वे पाळली पाहिजेत:

- **वापरकर्त्याची संमती आणि नियंत्रण**: कोणताही डेटा वापरण्यापूर्वी वापरकर्त्याची स्पष्ट संमती आवश्यक आहे. वापरकर्त्यांकडे कोणता डेटा शेअर करायचा आहे आणि कोणत्या क्रिया मान्य करायच्या आहेत यावर स्पष्ट नियंत्रण असावे, तसेच पुनरावलोकन आणि मंजुरीसाठी सोपे UI असावे.

- **डेटा गोपनीयता**: वापरकर्त्याचा डेटा फक्त स्पष्ट संमतीनेच उपलब्ध केला जावा आणि योग्य प्रवेश नियंत्रणांनी संरक्षित असावा. MCP अंमलबजावणी अनधिकृत डेटा प्रसारणापासून संरक्षण करावी आणि सर्व संवादांमध्ये गोपनीयता राखावी.

- **साधन सुरक्षा**: कोणतेही साधन वापरण्यापूर्वी वापरकर्त्याची स्पष्ट संमती आवश्यक आहे. वापरकर्त्यांना प्रत्येक साधनाची कार्यक्षमता समजायला हवी आणि अनपेक्षित किंवा असुरक्षित साधन वापर टाळण्यासाठी मजबूत सुरक्षा सीमा लागू कराव्यात.

हे तत्त्व पाळल्याने MCP वापरकर्त्यांचा विश्वास, गोपनीयता, आणि सुरक्षितता सर्व संवादांमध्ये राखतो.

## कोड उदाहरणे: मुख्य घटक

खाली काही लोकप्रिय प्रोग्रामिंग भाषांमध्ये MCP सर्व्हर घटक आणि साधने कशी तयार करायची याची उदाहरणे दिली आहेत.

### .NET उदाहरण: साधे MCP सर्व्हर आणि साधने तयार करणे

हा व्यावहारिक .NET कोड उदाहरण दर्शवतो की कसे साधे MCP सर्व्हर तयार करायचा आणि कस्टम साधने नोंदवायची. हे उदाहरण साधने कशी परिभाषित करायची, विनंत्या कशा हाताळायच्या, आणि Model Context Protocol वापरून सर्व्हरशी कनेक्ट कसा करायचा हे दाखवते.

```csharp
using System;
using System.Threading.Tasks;
using ModelContextProtocol.Server;
using ModelContextProtocol.Server.Transport;
using ModelContextProtocol.Server.Tools;

public class WeatherServer
{
    public static async Task Main(string[] args)
    {
        // Create an MCP server
        var server = new McpServer(
            name: "Weather MCP Server",
            version: "1.0.0"
        );
        
        // Register our custom weather tool
        server.AddTool<string, WeatherData>("weatherTool", 
            description: "Gets current weather for a location",
            execute: async (location) => {
                // Call weather API (simplified)
                var weatherData = await GetWeatherDataAsync(location);
                return weatherData;
            });
        
        // Connect the server using stdio transport
        var transport = new StdioServerTransport();
        await server.ConnectAsync(transport);
        
        Console.WriteLine("Weather MCP Server started");
        
        // Keep the server running until process is terminated
        await Task.Delay(-1);
    }
    
    private static async Task<WeatherData> GetWeatherDataAsync(string location)
    {
        // This would normally call a weather API
        // Simplified for demonstration
        await Task.Delay(100); // Simulate API call
        return new WeatherData { 
            Temperature = 72.5,
            Conditions = "Sunny",
            Location = location
        };
    }
}

public class WeatherData
{
    public double Temperature { get; set; }
    public string Conditions { get; set; }
    public string Location { get; set; }
}
```

### Java उदाहरण: MCP सर्व्हर घटक

.NET उदाहरणाप्रमाणेच MCP सर्व्हर आणि साधन नोंदणीचे Java मध्ये अंमलबजावणीचे उदाहरण.

```java
import io.modelcontextprotocol.server.McpServer;
import io.modelcontextprotocol.server.McpToolDefinition;
import io.modelcontextprotocol.server.transport.StdioServerTransport;
import io.modelcontextprotocol.server.tool.ToolExecutionContext;
import io.modelcontextprotocol.server.tool.ToolResponse;

public class WeatherMcpServer {
    public static void main(String[] args) throws Exception {
        // Create an MCP server
        McpServer server = McpServer.builder()
            .name("Weather MCP Server")
            .version("1.0.0")
            .build();
            
        // Register a weather tool
        server.registerTool(McpToolDefinition.builder("weatherTool")
            .description("Gets current weather for a location")
            .parameter("location", String.class)
            .execute((ToolExecutionContext ctx) -> {
                String location = ctx.getParameter("location", String.class);
                
                // Get weather data (simplified)
                WeatherData data = getWeatherData(location);
                
                // Return formatted response
                return ToolResponse.content(
                    String.format("Temperature: %.1f°F, Conditions: %s, Location: %s", 
                    data.getTemperature(), 
                    data.getConditions(), 
                    data.getLocation())
                );
            })
            .build());
        
        // Connect the server using stdio transport
        try (StdioServerTransport transport = new StdioServerTransport()) {
            server.connect(transport);
            System.out.println("Weather MCP Server started");
            // Keep server running until process is terminated
            Thread.currentThread().join();
        }
    }
    
    private static WeatherData getWeatherData(String location) {
        // Implementation would call a weather API
        // Simplified for example purposes
        return new WeatherData(72.5, "Sunny", location);
    }
}

class WeatherData {
    private double temperature;
    private String conditions;
    private String location;
    
    public WeatherData(double temperature, String conditions, String location) {
        this.temperature = temperature;
        this.conditions = conditions;
        this.location = location;
    }
    
    public double getTemperature() {
        return temperature;
    }
    
    public String getConditions() {
        return conditions;
    }
    
    public String getLocation() {
        return location;
    }
}
```

### Python उदाहरण:

**अस्वीकरण**:  
हा दस्तऐवज AI अनुवाद सेवा [Co-op Translator](https://github.com/Azure/co-op-translator) वापरून अनुवादित केला आहे. आम्ही अचूकतेसाठी प्रयत्नशील असलो तरी, कृपया लक्षात ठेवा की स्वयंचलित अनुवादांमध्ये चुका किंवा अचूकतेचा अभाव असू शकतो. मूळ दस्तऐवज त्याच्या स्थानिक भाषेत अधिकृत स्रोत मानला जावा. महत्त्वाच्या माहितीसाठी व्यावसायिक मानवी अनुवाद शिफारसीय आहे. या अनुवादाच्या वापरामुळे उद्भवलेल्या कोणत्याही गैरसमजुती किंवा चुकीच्या अर्थलागी आम्ही जबाबदार नाही.