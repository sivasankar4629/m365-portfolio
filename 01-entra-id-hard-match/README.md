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

When the correct anchor relationship is established, Entra Connect can recognize that the on-premises and cloud objects represent the same identity.

🛠️ Resolution

A Hard Match approach was used to establish the correct relationship between the on-premises AD object and the existing Microsoft Entra ID object.

The process involved:

Identifying the correct on-premises user object.
Validating the user's UPN and synchronization scope.
Reviewing the existing cloud identity.
Determining the appropriate source anchor relationship.
Establishing the Hard Match.
Triggering synchronization.
Validating the resulting identity association.

All changes were performed with identity and synchronization impact in mind.

✅ Validation

Following synchronization, the identity relationship was validated by checking:

Correct Entra ID object association
Synchronization status
User attributes
Sign-in behavior
Microsoft 365 service access
Absence of unintended duplicate objects
⚠️ Key Considerations

Hard Match should not be treated as a routine fix.

Before performing a Hard Match, it is important to understand:

Which AD object should be synchronized
Which cloud object should be retained
The current source anchor / Immutable ID
Whether duplicate objects exist
The synchronization scope
Potential impact on the user's Microsoft 365 identity

A wrong identity association can create additional synchronization and access issues.

💡 Key Takeaways

This scenario reinforced the importance of understanding identity synchronization rather than treating Entra Connect as simply a tool that copies users from Active Directory to Microsoft Entra ID.

The key areas are:

Identity → Source Anchor → Synchronization → Cloud Object → Access

Understanding these relationships is essential when troubleshooting hybrid identity environments.

🧠 Skills Demonstrated
Microsoft Entra ID
Microsoft Entra Connect
Active Directory
Hybrid Identity
Identity Synchronization
Hard Match
Immutable ID / Source Anchor
Microsoft 365 Troubleshooting
Identity Troubleshooting

Note: This case study is based on practical Microsoft 365 / hybrid identity experience. All customer names, domains, usernames, tenant identifiers and other sensitive information have been intentionally excluded.
