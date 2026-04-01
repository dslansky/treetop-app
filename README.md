# Treetop ABA — Family + Staff App

A native mobile app (iOS + Android) for Treetop ABA families and field staff. One app, two modes.

**Live prototype:** [dslansky.github.io/treetop-app](https://dslansky.github.io/treetop-app)

## What it does

### Parent mode
- View child's session schedule (upcoming + 90-day history)
- Cancel or request reschedule for sessions
- Message care team (BCBA + RBTs) in a continuous chat thread
- View and upload documents
- See assigned care team with credentials
- Sync sessions to phone calendar
- Push notifications for messages, reminders, schedule changes

### Staff mode (BTs + BCBAs)
- View daily and weekly schedule with client addresses
- Cancel individual sessions or call out for the full day — goes to scheduling, not parents
- Participate in parent-facing message threads (BCBA always present)
- Staff-only message thread per child (not visible to families)
- Track scheduled vs delivered vs cancelled hours
- Navigate to sessions via Maps
- Push notifications for client cancellations, schedule changes, new messages

## Architecture
- **App:** React Native (Expo) — single codebase for iOS + Android
- **Backend:** Google Cloud (Cloud Run + Firestore + Firebase Auth + FCM)
- **Auth:** Email/password for parents, phone number + SMS for staff
- **Data:** Salesforce / Lumary via caching middleware
- **HIPAA:** Covered under existing Google BAA

## Phased rollout
- **Phase 1A:** Schedule, session management, documents, care team, calendar sync (no messaging)
- **Phase 1B:** Full messaging system (parent threads + staff-only threads + Salesforce LWC)
- **Phase 2:** Prospect intake flow — lead generation through the app

## Prototype screens

### Role picker
- "I'm a parent" / "I'm a staff member"

### Parent (10 screens)
Login, Sign Up, Home Dashboard, Schedule, Session Detail, Cancel Session, Reschedule, Chat, Documents, Care Team, Settings

### Staff (10 screens)
Phone Login, SMS Verification, Today Dashboard, Session Detail, Cancel Session, Full-Day Callout, Message Inbox, Chat Thread, Week View, Settings

## Status
Planning and prototype phase. No production code yet.

## Repo structure
```
docs/          → GitHub Pages prototype (interactive HTML)
README.md      → This file
```
