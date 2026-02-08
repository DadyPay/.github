# DadyPay - Crypto & Mobile Payment Gateway 🚀

![DadyPay](https://img.shields.io/badge/DadyPay-Payment%20Gateway-purple)
![Next.js](https://img.shields.io/badge/Next.js-15.5.11-black)
![Cloudflare](https://img.shields.io/badge/Deployed-Cloudflare%20Workers-orange)
![Cryptos](https://img.shields.io/badge/Cryptos-261%2B-green)
![License](https://img.shields.io/badge/License-Proprietary-red)

A complete **crypto payment gateway** supporting **261+ cryptocurrencies** and Bangladesh mobile banking (bKash, Nagad). Built for merchants who want to accept crypto payments without complexity.

**🌐 Live:** https://pay.dadycoin.com

---

## 🎯 What is DadyPay?

DadyPay is a **SaaS payment gateway** that allows any business to:

1. **Accept 261+ Cryptocurrencies** - BTC, ETH, USDT, SOL, TON, DOGE, and more
2. **Accept Mobile Banking** - bKash, Nagad (Bangladesh)
3. **Get Paid Instantly** - Real-time notifications and webhooks
4. **No Crypto Knowledge Required** - Customers pay, merchants receive

### Perfect For:
- 🛒 E-commerce stores
- 🎮 Digital product sellers
- 💼 Freelancers & agencies
- 🌍 International businesses
- 📱 App developers

---

## ✨ Complete Feature List

### 💳 Payment Methods

| Method | Type | Networks | Status |
|--------|------|----------|--------|
| **Bitcoin (BTC)** | Crypto | Bitcoin, Lightning | ✅ Live |
| **Ethereum (ETH)** | Crypto | ERC20, Arbitrum, Optimism | ✅ Live |
| **USDT** | Crypto | TRC20, ERC20, BEP20, SOL | ✅ Live |
| **USDC** | Crypto | TRC20, ERC20, SOL | ✅ Live |
| **Solana (SOL)** | Crypto | Solana | ✅ Live |
| **TON** | Crypto | TON Network | ✅ Live |
| **DOGE, LTC, XRP** | Crypto | Native chains | ✅ Live |
| **250+ More** | Crypto | Various | ✅ Live |
| **bKash Personal** | Mobile | Bangladesh | ✅ Live |
| **Nagad Personal** | Mobile | Bangladesh | ✅ Live |

### 🏪 Merchant Dashboard

| Feature | Description |
|---------|-------------|
| **Dashboard Overview** | Real-time stats, recent transactions, quick actions |
| **Transaction History** | Full list with filters, search, export |
| **Pending Approvals** | Manual payment verification queue (bKash/Nagad) |
| **Payment Methods** | Configure which methods to accept |
| **Create Payment** | Generate payment links manually |
| **Payment Links** | Reusable payment links for products |
| **API Keys** | Generate/regenerate API credentials |
| **Webhooks** | Configure callback URLs for notifications |
| **Settings** | Profile, password, business info |

### 🔐 Security Features

| Feature | Implementation |
|---------|----------------|
| **Password Hashing** | PBKDF2 with 100K iterations |
| **Session Management** | Secure HttpOnly cookies, 7-day expiry |
| **Rate Limiting** | Auth: 5/15min, API: 60/min, Register: 3/hour |
| **API Authentication** | Unique API keys per merchant |
| **Webhook Signatures** | HMAC-SHA256 verification |
| **IP Blocking** | Block malicious IPs |
| **Activity Logging** | Full audit trail |

### 📧 Email Notifications

| Event | Recipient | Status |
|-------|-----------|--------|
| Payment Received | Customer | ✅ Live |
| Payment Confirmed | Customer | ✅ Live |
| Payment Rejected | Customer | ✅ Live |
| New Payment Alert | Merchant | ✅ Live |
| New Merchant Registration | Admin | ✅ Live |
| Merchant Approved | Merchant | ✅ Ready |

### 🔌 Developer API

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/api/payments` | POST | Create payment |
| `/api/payments?id=X` | GET | Get payment status |
| `/api/payments/methods` | GET | Available payment methods |
| `/api/payments/select-method` | POST | Select payment method |
| `/api/payments/submit-trxid` | POST | Submit TrxID (mobile) |
| `/api/payments/crypto-currencies` | GET | List 261+ cryptos |
| `/api/payments/status` | GET | Poll payment status |
| `/api/v1/payments` | POST/GET | API v1 endpoints |

---

## 🚀 How It Works

### Payment Flow

```
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│   Your Website  │────▶│    DadyPay      │────▶│    Customer     │
│                 │◀────│    Gateway      │◀────│    Pays         │
└─────────────────┘     └─────────────────┘     └─────────────────┘

1. Merchant creates payment via API
2. Customer redirected to payment page
3. Customer selects payment method (Crypto or Mobile)
4. Customer completes payment
5. DadyPay verifies and notifies merchant
6. Customer redirected to success page
```

### Crypto Payment Flow

```
Customer selects crypto → DadyPay generates address → Customer sends crypto
         → NOWPayments detects payment → Webhook confirms → Merchant notified
```

### Mobile Payment Flow (bKash/Nagad)

```
Customer sees merchant number → Sends money via bKash/Nagad app
         → Submits TrxID → Merchant verifies in dashboard → Approve/Reject
```

---

## 📋 Quick Start

### 1. Register as Merchant

```
https://pay.dadycoin.com/merchant/register
```

### 2. Get API Keys

Navigate to **Settings → API Keys** in your dashboard.

### 3. Create Your First Payment

```javascript
const response = await fetch('https://pay.dadycoin.com/api/payments', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
    'X-API-Key': 'pk_your_api_key'
  },
  body: JSON.stringify({
    amount: 1000,
    currency: 'BDT',
    orderId: 'ORDER-001',
    customerName: 'John Doe',
    customerEmail: 'john@example.com',
    successUrl: 'https://yoursite.com/success',
    cancelUrl: 'https://yoursite.com/cancel'
  })
});

const data = await response.json();
// Redirect customer to: data.data.paymentUrl
```

### 4. Handle Webhook

```javascript
// Your webhook endpoint
app.post('/api/dadypay-webhook', (req, res) => {
  const { event, data } = req.body;
  
  if (event === 'payment.completed') {
    // Payment confirmed! Deliver product/service
    console.log('Payment completed:', data.transactionId);
  }
  
  res.json({ received: true });
});
```

---

## 💰 Pricing Plans

| Plan | Monthly Fee | Transaction Fee | Payments/Month |
|------|-------------|-----------------|----------------|
| **Trial** | Free | 0% | 500 |
| **Starter** | ৳999 | 1% | 2,000 |
| **Growth** | ৳2,499 | 0.5% | 10,000 |
| **Business** | ৳4,999 | 0.25% | Unlimited |

---

## 🛠️ Tech Stack

| Component | Technology |
|-----------|------------|
| Framework | Next.js 15.5.11 (App Router) |
| Runtime | Cloudflare Workers (Edge) |
| Database | Cloudflare D1 (SQLite) |
| ORM | Drizzle ORM |
| Styling | Tailwind CSS |
| Language | TypeScript |
| Crypto Payments | NOWPayments API |
| Email | Resend API |
| Validation | Zod |

---

## 📁 Project Structure

```
dadypay/
├── migrations/          # D1 SQL migrations
├── public/images/       # Static assets & crypto icons
├── scripts/             # Utility scripts
├── src/
│   ├── app/
│   │   ├── api/         # API routes
│   │   │   ├── payments/    # Payment endpoints
│   │   │   ├── merchant/    # Merchant endpoints
│   │   │   ├── admin/       # Admin endpoints
│   │   │   └── webhooks/    # Webhook handlers
│   │   ├── merchant/    # Merchant dashboard pages
│   │   ├── pay/         # Customer payment pages
│   │   ├── admin/       # Admin dashboard
│   │   └── docs/        # API documentation
│   └── lib/
│       ├── auth/        # Authentication logic
│       ├── db/          # Database schema & queries
│       ├── email/       # Email templates
│       ├── payment/     # Payment processors
│       └── security/    # Rate limiting, CORS
├── docs/                # Documentation
├── wrangler.toml        # Cloudflare config
└── drizzle.config.ts    # ORM config
```

---

## 🔒 Environment Variables

```bash
# Required
RESEND_API_KEY=re_xxxx           # Email service
NOWPAYMENTS_API_KEY=xxxx         # Crypto payments

# Optional
ADMIN_API_KEY=xxxx               # Test endpoint security
ADMIN_EMAIL=support@domain.com   # Admin notifications
```

---

## 📚 Documentation

- [Developer Guide](docs/DEVELOPER_GUIDE.md) - Full API documentation
- [Merchant Guide](https://pay.dadycoin.com/merchant-guide) - How to use the dashboard
- [API Docs](https://pay.dadycoin.com/docs) - Interactive API reference

---

## 🤝 Support

- **Email:** support@dadycoin.com
- **Documentation:** https://pay.dadycoin.com/docs
- **Merchant Dashboard:** https://pay.dadycoin.com/merchant/login

---

## 📝 License

Proprietary - DadyPay © 2024-2026

---

## 🙏 Powered By

- [NOWPayments](https://nowpayments.io) - Crypto payment processing
- [Cloudflare](https://cloudflare.com) - Edge computing & database
- [Resend](https://resend.com) - Transactional emails
- [Next.js](https://nextjs.org) - React framework

