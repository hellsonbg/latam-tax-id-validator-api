# 🌎 LATAM Tax ID & Document Validator API

Stop writing complex Regex and modulo-11 mathematical equations for every country in Latin America. 

This is the documentation and usage guide for the **LATAM Tax ID Validator API**. With a single endpoint, you can validate individual and corporate tax identification numbers for the 7 biggest economies in Latin America.

### 🚀 Get your API Key here:
👉 **[Subscribe on RapidAPI (Free Tier Available)](https://rapidapi.com/helsonbg/api/latam-tax-id-document-validator)**

---

## Supported Countries

- 🇧🇷 **Brazil**: CPF (Individual) & CNPJ (Corporate)
- 🇲🇽 **Mexico**: RFC (Individual & Corporate)
- 🇦🇷 **Argentina**: CUIT / CUIL
- 🇨🇱 **Chile**: RUT / RUN
- 🇨🇴 **Colombia**: NIT
- 🇵🇪 **Peru**: RUC
- 🇺🇾 **Uruguay**: CI

---

## Why use this API instead of local libraries?
1. **Zero Dependencies**: Don't bloat your Node.js or Python projects with heavy validation libraries.
2. **Auto-Sanitization**: Send the data with dots, dashes, or spaces. The API cleans it automatically.
3. **Unified Response**: Whether it's a Brazilian CNPJ or an Argentine CUIT, the JSON response is always strictly typed and easy to read.
4. **Metadata Extraction**: Discover if a Brazilian CNPJ is a Branch or Headquarters instantly.

---

## Code Example (Node.js / Axios)

```javascript
const axios = require('axios');

const options = {
  method: 'POST',
  url: 'https://latam-tax-id-document-validator.p.rapidapi.com/validate',
  headers: {
    'content-type': 'application/json',
    'X-RapidAPI-Key': 'YOUR_RAPIDAPI_KEY', 
    'X-RapidAPI-Host': 'latam-tax-id-document-validator.p.rapidapi.com'
  },
  data: {
    country: 'BR', // Change to MX, AR, CL, CO, PE, UY
    doc_type: 'CNPJ',
    document: '11.222.333/0001-81'
  }
};

const response = await axios.request(options);
console.log(response.data);
```

### JSON Response:
```json
{
  "is_valid": true,
  "formatted": "11.222.333/0001-81",
  "metadata": {
    "type": "Corporate",
    "is_branch": false,
    "length": 14
  }
}
```

## Support & Integration
All endpoint definitions, schemas, and usage plans are hosted and managed securely via RapidAPI. 

👉 **[View Full Documentation & Pricing](https://rapidapi.com/helsonbg/api/latam-tax-id-document-validator)**
