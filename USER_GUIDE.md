# GRF Treasury FX Operations Portal — User Guide

## Overview

The **FX Matching & Settlement System (FX-SSO)** is an automated foreign exchange platform that helps GRF Treasury optimize currency conversions through internal netting. Instead of going directly to the bank, departments can submit FX needs and match with each other — saving on spreads and improving efficiency.

**Key Benefits:**
- ✅ Lower FX costs through internal matching
- ✅ Real-time visibility on matching opportunities
- ✅ Automated settlement workflow
- ✅ Full audit trail of all transactions
- ✅ Multi-currency support (EUR/USD, USD/ZAR, ZAR/USD)

---

## Getting Started

### Login
1. Navigate to the FX-SSO portal
2. Enter your **Email** and **6-digit PIN**
3. Click **Sign In**

**Forgot PIN?** Contact your Treasury Administrator

### Your Dashboard
After login, you'll see:
- **Buy Exposure**: Amount waiting to buy (pending)
- **Sell Exposure**: Amount waiting to sell (pending)
- **Matched Volume**: Already matched internally
- **Total Savings**: Cost saved vs bank rates
- **Today's Rate**: In-house exchange rate set by admin

---

## Core Workflows

### 1️⃣ Submit an FX Request (Buy or Sell)

**When:** You need to exchange currency

**Steps:**
1. Click **New FX Request** in the sidebar
2. Select your **Company** from the dropdown
3. Select **Account Number** (auto-filled with your accounts)
4. **Group** and **IBAN** auto-populate (read-only)
5. Choose **Transaction Type**:
   - Buy EUR (get Euros, pay USD)
   - Sell EUR (give Euros, get USD)
   - Buy USD (get Dollars, pay ZAR)
   - Sell USD (give Dollars, get ZAR)
   - Buy ZAR (get Rands, pay USD)
   - Sell ZAR (give Rands, get USD)
6. Enter **Amount** (minimum 1,000 units)
7. Optional: Add **Remarks** (e.g., "Project X payment")
8. Click **Submit Request**

**Status Flow:**
- 🟡 **Pending** → Waiting for a matching counterparty
- 🟢 **Matched** → Found a match, awaiting acceptance
- ✅ **Settled** → Complete, funds transferred

### 2️⃣ Monitor & Accept Matches (Seller Role)

**When:** You posted a SELL request and found a matching BUY

**Steps:**
1. Go to **Settlements** in the sidebar
2. Look for **⏳ Awaiting Seller Acceptance** section
3. Review the match details:
   - Match number, buyer, seller, currency pair
   - Amount and savings amount
   - Time remaining (must accept within time limit)
4. Choose:
   - **Accept** → Move to settlement (funds will transfer)
   - **Reject** → Decline the match; buyer goes to bank

**⚠️ Important:** If you don't accept within the deadline, the match expires and the buyer must use bank settlement.

### 3️⃣ Settle Accepted Matches (Admin Role)

**When:** Seller has accepted a match and it's ready to finalize

**Steps:**
1. Go to **Settlements**
2. Find **⏱ Accepted — Pending Settlement** section
3. Click **Settle** on the match
4. Add optional **Settlement Notes** (e.g., "Settled on time")
5. Click **Confirm Settlement**
6. Match moves to ✅ **Settled** section

**Workflow Stages:**
```
pending → (auto-match) → pending_acceptance → (seller accepts) → 
pending_settlement → (admin settles) → settled
```

### 4️⃣ Handle Rejected Matches

**When:** Seller rejects a match

**Result:**
- Buy request returns to **pending** status
- Moves to **Bank Exposure** (must settle with external bank)
- Savings opportunity is lost

---

## Matching Page (Real-time Overview)

**Access:** Click **Live Matching** in sidebar

**Displays:**
- **All pending requests** by currency pair
- Buy and sell volumes waiting to match
- **Run Auto-Match** button (admin-only)

**Filters:** Click tabs (All, EUR, USD, ZAR) to filter by currency

**How Auto-Match Works:**
1. Admin clicks **Run Auto-Match**
2. System scans all pending buy/sell requests
3. Matches largest orders first within each currency pair
4. Creates matches with **pending_acceptance** status
5. Sellers receive notification to accept/reject

---

## Rate Management (Admin Only)

**Access:** Click **Daily Rate Management** in sidebar

**Purpose:** Set the in-house exchange rates used for all matching

**Steps:**
1. Select **Currency Pair** from dropdown
   - EUR / USD
   - USD / ZAR
   - ZAR / USD
2. Enter **Internal Rate** (your rate, e.g., 1.17250)
3. Enter **Bank Mid Reference** (bank's mid-rate, e.g., 1.17300)
4. Click **Set Rate** → enter password → confirm
5. Rate is now active for all matching

**Rate Ranges:**
- EUR/USD: 0.5 – 3.0
- USD/ZAR: 10 – 25
- ZAR/USD: 0.04 – 0.12

**Impact:** The spread (difference between internal & bank mid) determines savings

---

## Savings Dashboard

**Access:** Click **💰 Savings** in sidebar

**Shows:**
- **Total Savings**: Sum of all matched deals
- **Today's Savings**: Just today
- **Last 7/30 Days**: Rolling period savings
- **Breakdowns by:**
  - Company
  - Currency Pair
  - Group
  - Day, Week, Month

**Use Case:** Track FX optimization impact over time

---

## FX Deal Page (Dealers)

**Access:** Click **FX Deal Page** in sidebar (requires permission)

**Purpose:** Full-width standalone page for high-volume FX dealing

**Includes:**
- Real-time rate charts
- Quick deal entry
- Settlement tracking
- Link to **FX Street** for live market data

---

## User Management (Super Admin Only)

**Access:** Click **User Management** in sidebar

**Create New User:**
1. Click **+ Add User**
2. Enter:
   - Full Name
   - Email
   - Role (User, FX Trader, Admin, Super Admin)
   - Company (optional)
   - **FX Deal Page Access** (Yes/No)
   - 6-Digit PIN (share securely)
3. Click **Create User**

**User Roles:**
- 👤 **User**: Submit/view own requests only
- 💼 **FX Trader**: Can submit and accept matches
- 🔧 **Admin**: Can settle matches, set rates, manage users
- 👨‍💼 **Super Admin**: Full system access

---

## Reports & Audit

**Access:** Click **Audit Trail** in sidebar

**Shows:**
- All system actions (requests, matches, settlements)
- Who did what and when
- Full transaction history

**Use Case:** Compliance, reconciliation, troubleshooting

---

## My Requests

**Access:** Click **My Requests** in sidebar

**View:**
- All requests you've submitted
- Current status of each
- Remaining unmatched amount
- Request date and details

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Can't log in | Check PIN (6 digits). Contact admin if forgotten. |
| Rate says "No rate set today" | Admin must set today's rate before matching can run. Go to Daily Rate Management. |
| Match expired without acceptance | Deadline passed. Buyer must resubmit or use bank settlement. |
| No matches created after running Auto-Match | Check that you have matching buy/sell pairs in same currency and sufficient amount. |
| Settlement button missing | You don't have admin role. Only admins can settle. |
| Permission denied on FX Deal Page | Ask super admin to enable FX Deal Page Access in User Management. |

---

## Best Practices

✅ **DO:**
- Submit requests early to maximize matching opportunities
- Check **Live Matching** before market close
- Accept matches promptly to avoid deadline expiry
- Review **Savings Dashboard** monthly
- Keep audit trail for compliance

❌ **DON'T:**
- Submit requests below minimum (1,000 units)
- Reject matches without good reason (saves cost)
- Delay settlements past deadline
- Share your PIN with anyone
- Ignore matched deals — they require action

---

## Support

**Questions?** Contact your Treasury Administrator or email treasury@grfholdings.com

**System Status:** Check alerts at top of dashboard

**New Features:** Check back monthly for updates

---

**Last Updated:** May 2026 | Version 1.0
