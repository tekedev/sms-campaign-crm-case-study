# SMS Campaign & CRM Mobile App — Architectural Case Study

> **Notice:** This repository is an **Architectural Case Study**. Production source code and carrier integration keys remain private.

---

## 🏛️ Executive Summary

**SMS Campaign & CRM Mobile App** is a full-featured cross-platform Flutter application engineered for small and medium businesses to manage customer contact lists, segment target audiences, and execute automated bulk SMS campaigns directly from mobile devices.

---

## ⚡ Key Engineering Highlights

- **Flutter Mobile Architecture:** Clean BLoC/Provider state management pattern providing smooth 60fps UI performance across Android devices.
- **Dynamic Audience Filtering & CRM Tags:** Instant contact search, group tagging, and custom metadata filtering over 10,000+ local contacts.
- **CSV & Excel Contact Ingestion:** Async worker threads parsing large contact lists without blocking the main UI thread.
- **Telephony API Integration:** Dual-SIM card detection and native Android SMS dispatch queue management.

---

## 📐 Application Architecture

```
   ┌────────────────────────────────────────────────────────┐
   │                Flutter UI Layer (Dart)                 │
   │      (Dashboard, Contact List, Campaign Composer)      │
   └───────────────────────────┬────────────────────────────┘
                               │
                               ▼
   ┌────────────────────────────────────────────────────────┐
   │               BLoC / State Management                  │
   └───────────────────────────┬────────────────────────────┘
                               │
             ┌─────────────────┴─────────────────┐
             ▼                                   ▼
  ┌──────────────────────┐            ┌─────────────────────┐
  │ Local SQLite Engine  │            │ Native Android SMS  │
  │ (Contact & Log Store)│            │ Direct Telephony    │
  └──────────────────────┘            └─────────────────────┘
```

---

## 🛠️ Tech Stack & Tooling

- **Mobile Framework:** Flutter 3.x, Dart
- **State Management:** Flutter BLoC / Provider
- **Storage:** SQLite (sqflite plugin), Shared Preferences
- **Platform Binding:** Android Native Telephony Channel

---
*Architected and engineered by **Enes Teke (tekedev)**.*
