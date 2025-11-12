# User Requirements Specification (URS)
## Rehabilitation Management Platform - Mobile Application

**Document Version:** 1.0  
**Date:** November 4, 2025  
**Client:** Marilu  
**Project Type:** Mobile Application (iOS & Android)  
**Technology:** Flutter

---

## 1. EXECUTIVE SUMMARY

This document outlines the requirements for the mobile application component of the rehabilitation management platform. The mobile app is designed primarily for **patients** to access their exercise programs, complete assessments, and communicate with their practitioners. It also includes **quality-of-life features for practitioners** to stay connected on the go.

**Primary Users:**
- Patients (Primary focus - 80% of functionality)
- Practitioners (Secondary - 20% quality-of-life features)

**Technology Stack:**
- Framework: Flutter (iOS & Android)
- Backend: Firebase (Authentication, Firestore, Storage, Cloud Messaging)

---

## 2. PATIENT FEATURES (PRIMARY FOCUS)

### 2.1 Authentication & Onboarding
- Patient registration with invitation code from practitioner
- Email/password login
- Biometric login (fingerprint, Face ID)
- Password reset
- Onboarding tutorial for first-time users

### 2.2 Patient Dashboard
- Welcome screen with patient name
- Today's exercise programs
- Quick stats (exercises completed, streak, weekly %)
- Upcoming appointments
- Unread messages
- Pending assessments
- Quick action buttons

### 2.3 Exercise Programs
**Program Overview:**
- List of active programs by condition
- Program details (name, practitioner, dates, progress)
- Program schedule

**Exercise List:**
- All exercises in prescribed order
- Exercise thumbnails
- Sets x Reps display
- Completion checkboxes
- Practitioner notes

**Video Player:**
- Full-screen video playback
- Play/pause controls
- Slow motion (0.5x, 0.75x)
- Written instructions
- Key points and tips
- Offline video caching

**Exercise Timer & Counter:**
- Built-in timer for hold exercises
- Rep counter with tap button
- Rest timer between sets
- Audio and vibration cues
- Auto-advance option

**Exercise Logging:**
- Mark exercises complete
- Log actual sets/reps performed
- Add notes and rate difficulty
- Report pain/discomfort
- Session summary

### 2.4 Progress Tracking
- Calendar view with completed days
- Streak counter
- Weekly/monthly completion percentage
- Progress charts and graphs
- Milestone badges
- Before/after assessment comparisons
- Progress photo uploads

### 2.5 Assessments & Questionnaires
- Push notifications for pending assessments
- Mobile-optimized questionnaire interface
- All assessment types:
  - VAS Pain Scale (slider)
  - STarT Back Questionnaire
  - Hip, Knee, Shoulder, Ankle Assessments
- Progress indicator
- Save and continue later
- View previous results
- Quick pain logging tool with body diagram

### 2.6 Communication
**Messaging:**
- Direct messaging with practitioner
- Send text, photos, videos
- Message history
- Read receipts
- Push notifications
- Quick replies
- Voice messages (optional)

**Notifications:**
- New programs assigned
- Messages from practitioner
- Assessment reminders
- Daily exercise reminders
- Appointment reminders
- Milestone achievements
- Customizable notification preferences

### 2.7 Appointments (Optional)
- View upcoming appointments
- Appointment details
- Add to device calendar
- Reminders
- Directions to clinic
- Appointment history

### 2.8 Profile & Settings
- View/edit profile information
- Profile photo
- Contact details
- Emergency contact
- Medical aid info
- Notification preferences
- Exercise reminder time
- Biometric login toggle
- Dark mode
- Video quality settings
- Download for offline use
- Privacy policy
- Logout

### 2.9 Offline Functionality
- Download exercise programs
- Cached exercise videos
- Log exercises offline (sync later)
- Offline mode indicator
- Automatic sync when online

---

## 3. PRACTITIONER FEATURES (QUALITY-OF-LIFE)

### 3.1 Authentication
- Login with web app credentials
- Biometric login
- Automatic logout for security

### 3.2 Practitioner Dashboard
- Number of active patients
- Patients who completed exercises today
- Pending assessments
- Unread patient messages
- Today's appointments
- Quick access to patient list
- Notifications summary

### 3.3 Patient Management (View-Only)
**Patient List:**
- Searchable patient list
- Patient name and photo
- Last activity date
- Compliance indicator
- Filter by condition/status

**Patient Profile View:**
- Patient demographics
- Active conditions
- Current programs
- Compliance statistics
- Recent assessment results
- Exercise completion history
- Recent messages
- View-only (no editing)

### 3.4 Messaging
- View and respond to patient messages
- Send quick messages
- Attach photos/documents
- Message notifications

### 3.5 Quick Actions
- View patient progress
- Check assessment results
- Review exercise compliance
- Send encouragement messages

### 3.6 Notifications
- Patient messages
- Completed assessments
- Low compliance alerts
- Urgent patient flags
- Customizable alert preferences

---

## 4. NON-FUNCTIONAL REQUIREMENTS

### 4.1 Performance
- App launch time: < 3 seconds
- Video streaming: Smooth on 4G/5G/Wi-Fi
- Offline mode: Full functionality for downloaded content
- Battery efficient

### 4.2 Security
- End-to-end encryption for messages
- Secure token storage
- Biometric authentication
- Auto-logout after 15 minutes inactivity
- HIPAA/POPIA compliant

### 4.3 Usability
- Intuitive, patient-friendly interface
- Large buttons and text for accessibility
- Simple navigation
- Minimal steps to start exercises
- Clear visual feedback

### 4.4 Compatibility
- iOS 13.0 and above
- Android 8.0 (API level 26) and above
- Support for tablets and phones
- Portrait and landscape orientation

### 4.5 Accessibility
- Screen reader support
- High contrast mode
- Adjustable font sizes
- Color-blind friendly design

### 4.6 Data Management
- Efficient data syncing
- Minimal data usage option
- Cache management
- Background sync

---

## 5. USER INTERFACE REQUIREMENTS

### 5.1 Design Principles
- Clean, modern, patient-friendly design
- Calming colors (blues, greens)
- Large, readable fonts
- Clear icons and buttons
- Consistent navigation
- Motivational and encouraging tone

### 5.2 Key Screens (Patient)
1. Login/Registration
2. Patient Dashboard
3. Program List
4. Exercise List
5. Video Player
6. Exercise Timer
7. Progress Dashboard
8. Assessment Forms
9. Messaging
10. Profile & Settings

### 5.3 Key Screens (Practitioner)
1. Login
2. Practitioner Dashboard
3. Patient List
4. Patient Profile View
5. Messaging
6. Notifications

---

## 6. INTEGRATION REQUIREMENTS

### 6.1 Firebase Services
- Firebase Authentication
- Cloud Firestore (real-time sync)
- Firebase Storage (videos, images)
- Cloud Messaging (push notifications)
- Firebase Analytics

### 6.2 Device Integration
- Camera (for photos/videos)
- Photo library
- Calendar
- Biometric sensors
- Push notifications
- Background tasks

### 6.3 Third-Party Services
- Video player (optimized for mobile)
- Maps integration (for directions)
- Analytics (user behavior)

---

## 7. SUCCESS CRITERIA

The mobile application will be considered successful when:
1. ✅ Patients can log in and view their exercise programs
2. ✅ Video playback is smooth and reliable
3. ✅ Patients can log completed exercises
4. ✅ Assessments can be completed on mobile
5. ✅ Messaging works reliably between patients and practitioners
6. ✅ Offline mode allows viewing downloaded programs
7. ✅ Practitioners can view patient progress on the go
8. ✅ Push notifications are delivered reliably
9. ✅ App is intuitive and requires minimal training
10. ✅ App performs well on both iOS and Android

---

## 8. FUTURE ENHANCEMENTS (Phase 2)

- Wearable device integration (Apple Watch, Fitbit)
- Video call consultations
- Social features (patient community)
- AI form checker using phone camera
- Voice-guided exercises
- Integration with health apps (Apple Health, Google Fit)
- Multi-language support
- Augmented reality exercise demonstrations
- Personalized exercise recommendations

---

## 9. GLOSSARY

- **Program:** Collection of exercises assigned to patient
- **Session:** One complete round of all exercises in a program
- **Streak:** Consecutive days of completing exercises
- **Assessment:** Standardized questionnaire
- **Compliance:** Percentage of prescribed exercises completed
- **Offline Mode:** Using app without internet connection

---

## DOCUMENT APPROVAL

**Prepared by:** QuantumX Software  
**Client Review Required:** Yes  
**Approval Status:** Pending Client Review

---

*This document is subject to change based on client feedback and technical discoveries during development.*
