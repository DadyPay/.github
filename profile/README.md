# DadyPay — Crypto & Mobile Payment Gateway

![DadyPay](https://img.shields.io/badge/DadyPay-Payment%20Gateway-purple)
![Version](https://img.shields.io/badge/Version-1.4.0-blue)
![Cryptos](https://img.shields.io/badge/Cryptos-250+-green)
![Status](https://img.shields.io/badge/Status-Live-brightgreen)

**DadyPay** is a SaaS payment gateway that lets any business accept **250+ cryptocurrencies** and local mobile payments — no crypto expertise required. Integrate in minutes, get paid globally.

**🌐 Live:** [pay.dadycoin.com](https://pay.dadycoin.com)

> **Non-custodial:** DadyPay never holds customer funds. Crypto payments are processed through secure third-party providers. Local mobile payments are merchant-operated P2P transfers.

---

## What is DadyPay?

- **250+ Cryptocurrencies** — BTC, ETH, USDT, SOL, TON, DOGE, XRP, LTC, DadyCoin (DDC), and many more
- **Local Mobile Payments** — Accept payments via merchant-operated mobile money methods
- **Merchant Store** — Built-in public storefront to sell products directly
- **DadyCoin Wallet** — Internal DDC wallet with transfers, deposits, and withdrawals
- **Webhooks & API** — Real-time payment notifications and a full REST API
- **Demo Mode** — Test the entire payment flow without real transactions
- **Edge-Deployed** — Globally distributed for fast response times

### Perfect For

- E-commerce stores & marketplaces
- Digital product sellers & SaaS businesses
- Freelancers & agencies accepting international payments
- App & game developers
- Any business looking to accept cryptocurrency

---

## Supported Cryptocurrencies

| Currency | Networks |
|----------|----------|
| **Bitcoin (BTC)** | Bitcoin, Lightning |
| **Ethereum (ETH)** | ERC-20, Arbitrum, Optimism |
| **USDT** | TRC-20, ERC-20, BEP-20, Solana |
| **USDC** | TRC-20, ERC-20, Solana |
| **Solana (SOL)** | Solana |
| **TON** | TON Network |
| **DOGE, LTC, XRP** | Native chains |
| **DadyCoin (DDC)** | USDT/USD pair |
| **250+ More** | Multiple chains & networks |
| **Local Mobile** | Merchant-operated |

---

## Merchant Dashboard

Everything you need to manage payments in one place:

- **Dashboard** — Real-time revenue stats, recent transactions, quick actions
- **Transactions** — Full history with search, filters, and export
- **Pending Approvals** — Verify and approve/reject local mobile payments
- **Payment Links** — Create reusable payment links for products and services
- **Merchant Store** — Public storefront with product management and checkout
- **Analytics** — Revenue charts, payment breakdowns, and trends
- **DadyCoin Wallet** — View balance, send/receive DDC, deposit, and withdraw
- **Webhooks** — Configure real-time payment notifications to your server
- **API Keys** — Generate and manage integration credentials
- **Subscription** — View and upgrade your plan
- **Settings** — Profile, password, business info, and payment methods
- **Demo Mode** — Test the full payment flow risk-free

---

## How It Works

```
┌─────────────────┐      ┌─────────────────┐      ┌─────────────────┐
│   Your Website  │─────▶│    DadyPay      │─────▶│    Customer     │
│                 │◀─────│    Gateway      │◀─────│    Pays         │
└─────────────────┘      └─────────────────┘      └─────────────────┘
```

1. **Create a payment** — Call the DadyPay API from your website or app
2. **Customer chooses** — Redirected to a hosted payment page to pick crypto or mobile
3. **Payment completes** — Customer pays; blockchain confirms or merchant verifies
4. **You get notified** — Webhook fires to your server with payment status
5. **Done** — Customer is redirected to your success page

---

## Quick Start

### 1. Create Your Account

Sign up at [pay.dadycoin.com/merchant/register](https://pay.dadycoin.com/merchant/register).

### 2. Get Your API Key

Navigate to **Settings → API Keys** in the merchant dashboard.

### 3. Create a Payment

```javascript
const response = await fetch("https://pay.dadycoin.com/api/payments", {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
    "X-API-Key": "pk_your_api_key",
  },
  body: JSON.stringify({
    amount: 1000,
    currency: "USD",
    orderId: "ORDER-001",
    customerName: "Jane Doe",
    customerEmail: "jane@example.com",
    successUrl: "https://yoursite.com/success",
    cancelUrl: "https://yoursite.com/cancel",
  }),
});

const { data } = await response.json();
// Redirect customer to: data.paymentUrl
```

### 4. Receive Webhooks

```javascript
app.post("/webhooks/dadypay", (req, res) => {
  const { event, data } = req.body;

  if (event === "payment.completed") {
    // Payment confirmed — deliver the product or service
    console.log("Payment completed:", data.transactionId);
  }

  res.json({ received: true });
});
```

---

## API Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/api/payments` | `POST` | Create a new payment |
| `/api/payments?id=X` | `GET` | Get payment details |
| `/api/payments/methods` | `GET` | List available payment methods |
| `/api/payments/select-method` | `POST` | Select a payment method |
| `/api/payments/submit-trxid` | `POST` | Submit a mobile transaction ID |
| `/api/payments/crypto-currencies` | `GET` | List supported cryptocurrencies |
| `/api/payments/status` | `GET` | Poll payment status |
| `/api/payments/exchange-rate` | `GET` | Get current exchange rate |
| `/api/checkout` | `POST` | Create a hosted checkout session |
| `/api/v1/payments` | `POST` / `GET` | API v1 payment endpoints |

Full documentation: [pay.dadycoin.com/docs](https://pay.dadycoin.com/docs)

---

## Email Notifications

Automated emails for every important event:

- **Merchant:** Welcome, email verification, password reset, new payment alerts, approval notifications, withdrawal updates, transfer confirmations
- **Customer:** Payment received, payment confirmed, payment rejected

---

## Security

DadyPay is built with enterprise-grade security:

- Strong password hashing and secure session management
- Rate limiting on authentication and API endpoints
- CSRF protection, Content Security Policy (CSP), and strict CORS
- Encrypted OTP codes for sensitive operations
- Input validation on all endpoints
- Webhook signature verification with retry logic
- Email verification and secure password reset flows
- Full activity audit logging

---

## Subscription Plans

| Plan | Monthly Fee | Payments / Month | Highlights |
|------|-------------|------------------|------------|
| **Free Trial** | Free (14 days) | 500 | Full feature access |
| **Starter** | $499 | 100 | 1 payment method, basic dashboard |
| **Growth** | $999 | 500 | All payment methods, API, webhooks, emails |
| **Business** | $2,499 | Unlimited | Priority support, analytics, custom branding |

---

## Documentation

- [API Docs](https://pay.dadycoin.com/docs) — Interactive API reference
- [Merchant Guide](https://pay.dadycoin.com/merchant-guide) — How to use the dashboard

---

## Support

- **Email:** support@pay.dadycoin.com
- **Docs:** [pay.dadycoin.com/docs](https://pay.dadycoin.com/docs)
- **Dashboard:** [pay.dadycoin.com/merchant/login](https://pay.dadycoin.com/merchant/login)

---

## License

Proprietary — © 2024–2026 DadyPay. All rights reserved.

