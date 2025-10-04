# Icecream Shop

## Assumptions
- The project assumes a simple online ice cream shop where users can browse products and make purchases.  
- User authentication is not implemented; anonymous checkout is allowed.  
- Stripe is used for payment processing.

## Flow Chosen
- **Checkout Session Flow** is used instead of Payment Intents for simplicity.  
- This flow handles one-time payments easily and provides Stripe-hosted checkout pages.  

## Avoiding Double Charge / Inconsistent State
- Orders are created only after successful Stripe payment webhook confirmation.  
- Webhook handler updates order status and prevents multiple charges.  
- Idempotency keys are used in Stripe requests to prevent repeated payment creation.  

## Setup / Run Steps

### 1. Clone the repository
```bash
git clone https://github.com/Rishavkumar720/eccom-strip.git
cd eccom-strip

2. Create and activate virtual environment
python -m venv venv
source venv/Scripts/activate


env.example

SECRET_KEY=your_django_secret_key
DEBUG=True
DB_ENGINE=django.db.backends.postgresql
DB_NAME=icecream_db
DB_USER=postgras
DB_PASSWORD=12345
DB_HOST=localhost
DB_PORT=5432
STRIPE_PUBLIC_KEY=pk_test_51SEBuJDCf7tqmI333x8cHmM4SKzyH4M9PxwTUi2jhbiSCw1cDhaReoWWvybj1zeZGiHlBbyc69eKZfJKKY3rSSYE00pQ1HTuCX
STRIPE_SECRET_KEY=*k_test_51SEBuJDCf7tqmI33Y1mGcmyYc1RxP48hvyjb0uZEDsXD3KV3O8v9poTIq5KgM8dXCHArmWo6P7pDx2XayL2nrpXG00fdnX0cbS



AI Tools Used
- ChatGPT (GPT-5) for generating project guidance, folder structure, `.env` templates, and README content.  
- AI was used to suggest Git workflows, setup instructions, and handling Stripe payment flows.
- and also used to learn about stip and postgral




ime Spent
- Total hours actually spent: 10 hours
- 5 haour i used to code
-5 hour used to understand the concept abou strip and postgral

github link
https://github.com/Rishavkumar720/eccom-strip


