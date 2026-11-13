# Dallas

Dallas is an offline-first business finance and accounting companion built with Expo and React Native. It uses Kenyan shillings (KES) by default and stores business records locally on the device.

## Business operations

- Business profile with contact details and optional KRA PIN reference
- Product and service catalogue with SKU, selling price, unit cost, stock quantity and low-stock threshold
- Stock purchase recording that increases inventory and records the purchase expense
- Sales invoices that deduct stock, record collections and create customer receivables for credit sales
- Customer and supplier directories
- Manual stock adjustments and low-stock indicators
- Customer receivables and supplier/payable tracking through the debt ledger
- Monthly sales, cash movement, estimated gross profit, estimated net profit and inventory valuation summaries

## Finance tools

- Income and expense records with dates, descriptions, categories and optional references
- Daily hotel sales tracker with room/table, service, payment method and M-Pesa reference fields
- Daily, weekly and monthly category budgets
- Savings goals and contributions
- Debt tracking, partial payments and payment history; recorded debt payments are posted to the cash ledger
- Recurring income and expense reminders with manual posting of due items
- PDF and CSV-style exports
- Custom categories
- Optional 4–6 digit PIN and device biometric unlock

## Data, integrations and accounting limitations

- Business and finance records are stored locally using AsyncStorage. The optional PIN is stored using Expo SecureStore.
- Dallas does not currently provide cloud synchronisation, multi-user access, automatic Safaricom Daraja payments, automatic M-Pesa statement import, bank feeds, KRA eTIMS submission, or certified tax invoices.
- M-Pesa references and payment methods are captured manually.
- Credit sales create receivables; debt payments update the cash ledger. Stock purchases increase inventory and record a cash expense.
- Profit figures are estimates based on the unit cost saved on each invoice and recorded operating expenses. They are not audited financial statements and do not replace professional bookkeeping or tax advice.
- Export important records regularly before changing or resetting phones.

## Development

Requirements: Node.js 22, Java 17 and Android build tools (the GitHub Actions workflow installs the CI requirements).

```bash
npm install
npx expo start
```

The GitHub Actions workflow validates the Expo Android bundle, generates the native Android project, builds the release APK and uploads it as the `Dallas-Android-APK` artifact.

## Quality notes

CI verifies that the JavaScript bundle exports and that the Android release build completes. This is not a substitute for testing on a physical Android device. Before production use, verify stock deductions, invoice and debt balances, data retention, exports, date handling and all finance calculations on the target phone.
