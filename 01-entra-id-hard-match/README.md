# 🔄 Microsoft Entra ID Hard Match

## Overview

This case study covers a real-world identity synchronization scenario involving an existing Microsoft 365 cloud identity and an on-premises Active Directory user.

The objective was to correctly associate the on-premises AD object with the existing Microsoft Entra ID object through Microsoft Entra Connect synchronization.

---

## 🧩 Scenario

An organization had an existing user account in Microsoft Entra ID while the corresponding user object was also present in the on-premises Active Directory environment.

During synchronization, the identities needed to be correctly associated rather than creating or maintaining a separate cloud identity.

### Environment

- On-premises Active Directory
- Microsoft Entra ID
- Microsoft Entra Connect
- Microsoft 365
- Password Hash Synchronization
- Hybrid Identity

---

## 🎯 Challenge

The primary challenge was establishing the correct relationship between:

**On-Premises AD User**

and

**Existing Microsoft Entra ID User**

Incorrect identity matching can result in duplicate objects, unexpected synchronization behavior, or disruption to the user's Microsoft 365 identity.

---

## 🔍 Investigation

Before performing any identity matching operation, the following areas were validated:

- On-premises AD user object
- User Principal Name (UPN)
- Existing cloud user object
- Microsoft Entra Connect synchronization scope
- Source Anchor / Immutable ID
- Existing synchronization relationship
- Potential duplicate or conflicting objects

The objective was to understand the current identity state before making any changes.

---

## 🔗 Identity Matching Concept

Microsoft Entra Connect uses an identity anchor to associate an on-premises object with its corresponding cloud object.

Conceptually:

```text
On-Premises Active Directory
            │
            ▼
     Microsoft Entra Connect
            │
            ▼
     Source Anchor
            │
            ▼
       Immutable ID
            │
            ▼
Existing Microsoft Entra ID Object
