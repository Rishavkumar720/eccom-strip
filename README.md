# eccom-strip
This is a simple Django web app using PostgreSQL and Stripe Checkout (in test mode).
The home page displays three fixed ice cream products. A user can enter quantities, click Buy, complete a Stripe test payment, and then see their paid order listed on the same page.

Project Overview

Built with Django 5 and PostgreSQL.

Uses Stripe Checkout for payments (test mode only).

Displays three fixed products:

Vanilla Ice Cream ($5.00)

Chocolate Ice Cream ($6.00)

Strawberry Ice Cream ($5.50)

After successful payment, the order appears under "My Orders" on the same page.

Prevents double charge or inconsistent state by verifying Stripe session before marking an order as paid.

Assumptions

Each user can view and buy products without authentication.

Products are fixed and manually inserted into the database once.

Stripe Checkout is used for simplicity and reliability (instead of Payment Intents).

Orders are verified through Stripe before being marked as paid.

Flow Description

The home page (/) shows all products and a form to select quantities.

When the user clicks Buy, a Stripe Checkout Session is created.

Stripe handles the payment securely.

Upon success, Stripe redirects the user to /success/ with a session ID.

The app verifies the session with Stripe and marks the order as paid.

The user is redirected back to the home page where their paid order appears.

Why Stripe Checkout

Stripe Checkout was chosen over Payment Intents because:

It provides a prebuilt, secure payment flow.

It reduces frontend complexity.

It automatically handles test cards, errors, and redirects.

Preventing Double Charge

Each order is linked to a unique Stripe session ID.

Before marking an order as paid, the app verifies payment status directly with Stripe.

If a page refresh or double submit occurs, no new session is created if payment is already completed.
