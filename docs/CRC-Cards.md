
# CRC CARDS
## Medical Stock and Queue Management System for Rural Health Units (RHU)

---

## 1. Resident

**Responsibilities:**
- Store resident information.
- Provide personal details during registration.
- Maintain resident records.

**Collaborators:**
- QueueTicket
- Consultation
- Prescription

---

## 2. QueueTicket

**Responsibilities:**
- Store the assigned queue number.
- Record the selected service.
- Track the resident's queue status.
- Store priority information.

**Collaborators:**
- Resident
- QueueManager
- ServiceType

---

## 3. QueueManager

**Responsibilities:**
- Register residents in the queue.
- Generate queue numbers.
- Manage queue order and priority.
- Call the next resident.

**Collaborators:**
- Resident
- QueueTicket
- ServiceType

---

## 4. ServiceType

**Responsibilities:**
- Identify the type of service requested.
- Provide available service categories.
- Classify residents according to their requested service.

**Collaborators:**
- QueueTicket
- QueueManager

---

## 5. Consultation

**Responsibilities:**
- Record consultation information.
- Connect the resident to the consultation record.
- Record prescribed medicines.

**Collaborators:**
- Resident
- QueueTicket
- Prescription

---

## 6. Prescription

**Responsibilities:**
- Store prescribed medicine details.
- Record prescribed quantities.
- Provide prescription information to the pharmacy.

**Collaborators:**
- Resident
- Consultation
- Medicine

---

## 7. Medicine

**Responsibilities:**
- Store medicine information.
- Identify medicine names and units.
- Provide medicine details for inventory monitoring.

**Collaborators:**
- Inventory
- MedicineBatch
- Prescription

---

## 8. MedicineBatch

**Responsibilities:**
- Store medicine batch numbers.
- Track medicine quantities per batch.
- Monitor medicine expiration dates.
- Identify batches that expire first.

**Collaborators:**
- Medicine
- Inventory
- StockAlert

---

## 9. Inventory

**Responsibilities:**
- Manage medicine and supply records.
- Monitor available stock quantities.
- Check medicine availability.
- Update stock balances.

**Collaborators:**
- Medicine
- MedicineBatch
- StockTransaction
- StockAlert

---

## 10. StockTransaction

**Responsibilities:**
- Record incoming supplies (stock-in).
- Record dispensed medicines (stock-out).
- Update inventory transaction records.

**Collaborators:**
- Inventory
- MedicineBatch
- UserAccount

---

## 11. StockAlert

**Responsibilities:**
- Detect low-stock items.
- Identify medicines nearing expiration.
- Notify staff about inventory problems.

**Collaborators:**
- Inventory
- MedicineBatch
- UserAccount

---

## 12. Report

**Responsibilities:**
- Generate monthly inventory reports.
- Generate medicine consumption reports.
- Generate resident-count reports.
- Export reports as PDF or Excel.

**Collaborators:**
- Inventory
- StockTransaction
- Resident
- QueueTicket
- UserAccount

---

## 13. UserAccount

**Responsibilities:**
- Store user account information.
- Authenticate system users.
- Manage user access according to assigned roles.

**Collaborators:**
- QueueManager
- StockTransaction
- StockAlert
- Report

---

# EXTENSION POINTS
## Possible New Types and Rules

| Class | Extension Point |
|---|---|
| QueueTicket | New priority categories such as senior citizens, pregnant women, PWDs, and emergency cases. |
| ServiceType | Add new services such as laboratory or dental services. |
| Medicine | Add new medicine categories. |
| MedicineBatch | Add new expiration and batch-monitoring rules. |
| Inventory | Add minimum stock-level rules. |
| StockAlert | Add new alert types and notification methods. |
| Report | Add new report formats or report categories. |
| UserAccount | Add new user roles and permissions. |

---


