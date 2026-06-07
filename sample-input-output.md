# Sample Input / Output

## Example 1 — Automatic Resolution

### Input

```json
{
  "customer_name": "Riya",
  "email": "riya@gmail.com",
  "message": "I forgot my password. How do I reset it?"
}
```

---

### Workflow Processing

* Ticket received through webhook
* Customer data prepared
* Support response generated
* Response quality reviewed
* Confidence evaluated
* Routed to automatic resolution
* Customer notified

---

### Output

```json
{
  "confidence": 95,
  "escalate": false
}
```

Customer receives:

```text
✅ SUPPORT UPDATE

Issue:
Forgot Password

Resolution:
Please provide your registered email address and follow the password reset instructions.

Status:
Resolved Automatically

Thank you for contacting support.
```

---

# Example 2 — Human Escalation

### Input

```json
{
  "customer_name": "Rahul",
  "email": "rahul@gmail.com",
  "message": "My order never arrived. I want refund immediately and I may file a complaint."
}
```

---

### Workflow Processing

* Ticket received through webhook
* Support response generated
* Quality reviewed
* Confidence lowered
* Escalation triggered
* Support team notified
* Customer informed

---

### Output

```json
{
  "confidence": 20,
  "escalate": true
}
```

Support Team receives:

```text
🚨 SUPPORT ESCALATION ALERT

Customer request requires manual review.

Priority:
HIGH

Status:
Awaiting Human Review
```

Customer receives:

```text
✅ SUPPORT UPDATE

Your request requires additional review.

Status:
Escalated to Human Support

Expected Response Time:
Within 2 business days

Thank you for your patience.
```

---

# Expected Behavior Summary

Low-risk issues
→ Automatically resolved

High-risk issues
→ Escalated to support team

Uncertain outputs
→ Human review fallback
