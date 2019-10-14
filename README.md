# :credit_card::fire::heavy_check_mark: ccc.js

Card Credit Checker _ for studies _

---

### UsageExample

```javascript
const ccc = require("./ccc");

// Payment Gateway Request Config
ccc.config({
  url: "http://localhost:3333/pay",
  method: "post",
  //  Variables = <CARD>, <MONTH>, <YEAR>, <CVV>
  data: `{"card": "<CARD>","month": "<MONTH>","year": "<YEAR>","cvv": "<CVV>"}`,
  headers: { "Content-Type": "application/json" },
  keywords: {
    declined: "Declined",
    approved: "Approved"
  }
});

const CardNumber = "4444444444444444";
const CardMonth = "01";
const CardYear = "2020";
const CardCVV = "000";

async function example() {
  const Check = await ccc.check(CardNumber, CardMonth, CardYear, CardCVV);

  if (Check.error) {
    return console.log(Check.error);
  }

  if (Check.approved) {
    // approved
  }
  if (Check.declined) {
    // declined
  }
}

example();
```

---

_Old version: https://github.com/br0keh/cc-checker_
