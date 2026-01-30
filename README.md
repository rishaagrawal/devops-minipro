# devops-minipro

Perfect 👍 these features divide **very cleanly** among 4 people.
Below is a **clear, logical team split** that also makes your **Git branches + JUnit tests look professional**.

---

## ✅ 4-Person Division for Content Moderation Engine

### 👤 **Person 1 – Core Moderation & Severity Engine**

**Features owned:**

* **Word Severity Levels**

  * LOW / MEDIUM / HIGH classification
  * Map severity → action (ALLOW / FLAG / BLOCK)

**Responsibilities:**

* Define `Severity` enum
* Implement rule evaluation logic
* Return moderation result based on severity

**JUnit focus:**

* HIGH → BLOCK
* MEDIUM → FLAG
* LOW → ALLOW with warning

**Suggested branch:**
`feature-severity-engine`

---

### 👤 **Person 2 – Text Matching & Normalization**

**Features owned:**

* **Case-insensitive matching**
* **Partial / symbol-stripped matching**

**Responsibilities:**

* Normalize text (lowercase, remove symbols)
* Detect disguised words (`b@dword`, `bad-word`)
* Provide reusable text-matching utility

**JUnit focus:**

* Case-insensitive detection
* Symbol removal logic
* Partial match detection

**Suggested branch:**
`feature-text-matching`

---

### 👤 **Person 3 – Strike & Context Rule Manager**

**Features owned:**

* **Strike / Warning System**
* **Context-Based Rules**

**Responsibilities:**

* Track user strikes
* Enforce escalation:

  * 1st → warning
  * 2nd → temporary block
  * 3rd → permanent block
* Apply context overrides (educational vs general)

**JUnit focus:**

* Strike count increment
* Correct action per strike level
* Context allows / blocks content correctly

**Suggested branch:**
`feature-strikes-context`

---

### 👤 **Person 4 – Audit Logs & Testing**

**Features owned:**

* **Audit / Moderation Logs**
* Cross-module **JUnit tests**

**Responsibilities:**

* Create log entries:

  * user
  * word/rule triggered
  * action
  * timestamp
* Maintain moderation history
* Write integration-style unit tests

**JUnit focus:**

* Log created on moderation action
* Correct log count
* Log content accuracy

**Suggested branch:**
`feature-audit-logs`

---

## 🔹 How Everything Connects (Simple Flow)

1. **Text Matching** → finds offending word
2. **Severity Engine** → decides action
3. **Context + Strikes** → may override or escalate
4. **Audit Logs** → record final decision

Each part is **independent**, so:

* minimal merge conflicts
* clean commits
* easy explanation in demo/viva

---

## ⭐ One-Line Team Summary (Very Useful)

> *The system is modular: text normalization detects violations, severity rules decide actions, strike and context logic handle escalation, and audit logs track all moderation decisions.*

If you want, I can next:

* give a **simple class diagram**
* write **sample JUnit test cases per person**
* or help you **simplify further** if time is short
