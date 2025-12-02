# Peer2Loan_Team33

SSD Final Project

A transparent, secure, and rule-based system for month-on-month pooled lending groups.

Peer2Loan modernizes informal community lending (friends, colleagues, relatives, SHGs) by offering a **digital, transparent, dispute-free alternative** to traditional chit funds.

- **No auctions**
- **No dividends**
- **Equal monthly contribution**
- **Every member receives one payout**
- **Turn order decided upfront or via rule-based logic**

The system provides transparency, accountability, auditability, and ease of use for organizers and members.

---

## 📌 Solution Diagram

```
+-------------------+         +-------------------+         +-------------------+
|     Frontend      | <-----> |      Backend      | <-----> |     Database      |
|   (React.js)      |  REST   | (Node.js/Express) | Mongoose|     (MongoDB)     |
+-------------------+         +-------------------+         +-------------------+
        |                            |                               |
        |  Dashboards, UI, Flows     |  Rules, Cycles, Logic, Auth   |  Groups, Members,
        |                            |                               |  Cycles, Ledgers
```

---

## 📌 Design Assumptions

- No dividends or auctions — fixed contribution and one payout per member.
- Turn order can be **fixed**, **randomized**, or **rule-based**.
- Organizer manages group creation, member approval, proof verification, and rules.
- Members upload monthly payment proof.
- System enforces late fees, arrears, dispute resolution, and replacement rules.
- End-of-cycle **audit pack (CSV/PDF)** generated automatically.
- Every action is tracked in ledgers for transparency.

---

## 📌 Implementation Details

### **Backend**

- **Node.js + Express.js**
- **MongoDB (Mongoose ODM)**
- Business logic includes:
  - Group creation & turn order
  - Monthly cycle management
  - Penalties, arrears, replacements
  - Dispute resolution
  - Payout tracking
  - Notifications & audit logs

### **Frontend**

- **React.js** for modular UI
- Dashboards, forms, and calendar views
- Status tracking (Paid / Pending / Late)

### **Database Collections**

- Groups
- Members
- Cycles
- Payments
- Payouts
- Penalties
- Notifications
- Audit Logs

---

## 📌 Features

### **1. Group Setup**

Organizers configure:

- Group name, currency, monthly contribution
- Number of members & duration
- Grace period, penalties, payment windows
- Turn order logic

A complete payout calendar is auto-generated.

---

### **2. Member Management**

- Join via invite link
- Provide identity & payout details
- Add emergency contact
- Organizer approves or rejects

---

### **3. Contribution Tracking**

- Automatic reminders
- Members upload proof (e.g., UPI screenshot)
- System tracks **Paid / Pending / Late**

---

### **4. Cycle Management**

- Pot becomes ready when all contributions are received
- System confirms monthly payout recipient
- Organizer disburses payout & uploads proof
- All members see confirmation

---

### **5. Exception Handling**

- **Late fees** auto-applied
- **Missed payments** → arrears
- **Soft locks** prevent future payouts
- **Member replacement** supported
- **Disputes** reviewed by organizer

---

### **6. Dashboards**

#### Cycle Dashboard

- Pot total
- Paid vs pending
- Payout recipient
- Cutoff timers

#### Member Dashboard

- Contributions history
- Penalties & arrears
- Payout status

#### Group Dashboard

- Month-wise collections
- Overall progress

---

### **7. Ledgers**

- **Member Ledger:** contributions, penalties, payout status
- **Group Ledger:** pool summary, payouts, timeline

---

### **8. Notifications & Alerts**

Automatic alerts for:

- Due dates
- Late fees
- Payout confirmations
- Disputes

---

### **9. Reports & Audit**

- Monthly summaries
- Final **Audit Pack (CSV/PDF)** with:
  - Contributions
  - Payouts
  - Penalties
  - Exceptions
  - Disputes

---

## 📌 Setup Instructions

### **Prerequisites**

- Node.js (v16+)
- MongoDB Atlas/local
- npm or yarn

---

## 🔧 Backend Setup

```bash
cd peer2loan/backend
npm install
```

Create `.env`:

```
MONGO_URI=your_mongodb_uri
JWT_SECRET=your_jwt_secret
```

Start backend:

```bash
npm start
```

---

## 🎨 Frontend Setup

```bash
cd peer2loan/frontend
npm install
npm start
```

Visit:  
**http://localhost:3000**

```

# End of File
```
