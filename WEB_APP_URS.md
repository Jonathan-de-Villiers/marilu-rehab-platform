# User Requirements Specification (URS)
## Rehabilitation Management Platform - Web Application

**Document Version:** 1.0  
**Date:** November 4, 2025  
**Client:** Marilu  
**Project Type:** Web-based Rehabilitation Management System

---

## 1. EXECUTIVE SUMMARY

This document outlines the requirements for a comprehensive web-based rehabilitation management platform designed for physiotherapy and rehabilitation practices. The system will enable practitioners to manage patients, create exercise programs, track progress, and deliver personalized care through a modern, intuitive interface.

**Primary Users:**
- Practice Administrators
- Physiotherapists/Rehabilitation Professionals
- Practice Staff

**Technology Stack:**
- Frontend: React.js
- Backend: Firebase (Authentication, Firestore Database, Storage, Cloud Functions)
- Hosting: Firebase Hosting

---

## 2. SYSTEM OVERVIEW

### 2.1 Purpose
The web application serves as the primary management tool for rehabilitation practices, providing complete functionality for:
- Practice and professional profile management
- Patient management with condition-specific sub-profiles
- Exercise library with video content
- Custom exercise program creation and templates
- Patient assessment through standardized questionnaires
- Progress tracking and reporting
- Communication with patients

### 2.2 Key Benefits
- **Efficiency:** Streamline patient care with reusable templates
- **Customization:** Create practice-specific exercise libraries
- **Organization:** Categorized exercises by body part and movement type
- **Compliance:** Track patient progress with standardized assessments
- **Flexibility:** Support multiple professionals within one practice

---

## 3. FUNCTIONAL REQUIREMENTS

### 3.1 USER MANAGEMENT & AUTHENTICATION

#### 3.1.1 Practice Profile Management
**What it does:** Allows practices to create and manage their main account.

**Features:**
- Practice registration with business details (name, address, contact info, registration numbers)
- Practice logo and branding upload
- Subscription management and billing
- Practice settings and preferences
- Multi-location support (if practice has multiple branches)

**User Story:** *"As a practice owner, I want to create a profile for my practice so that I can manage my team and patients in one place."*

#### 3.1.2 Professional Sub-Profiles
**What it does:** Enables multiple professionals to work under one practice account.

**Features:**
- Create unlimited professional profiles under practice
- Each professional has their own credentials and login
- Professional details (name, qualifications, specializations, photo)
- Individual professional dashboards
- Permission levels (Admin, Professional, View-only)
- Professional can only see their assigned patients (with option for practice-wide visibility)

**User Story:** *"As a practice with 3 physiotherapists, I want each therapist to have their own login and patient list while sharing the exercise library."*

#### 3.1.3 Authentication & Security
**What it does:** Secure access control for all users.

**Features:**
- Email/password authentication via Firebase Auth
- Password reset functionality
- Two-factor authentication (optional)
- Session management
- Role-based access control (RBAC)
- HIPAA/POPIA compliant data handling

---

### 3.2 PATIENT MANAGEMENT

#### 3.2.1 Patient Profiles
**What it does:** Comprehensive patient information management.

**Features:**
- Patient registration (name, contact, ID number, medical aid details)
- Patient demographics and medical history
- Assigned professional(s)
- Patient status (Active, Inactive, Discharged)
- Document upload (medical reports, referral letters)
- Notes and comments section
- Patient timeline/activity log

**User Story:** *"As a physiotherapist, I want to view all my patient information in one place so I can provide better care."*

#### 3.2.2 Condition-Specific Sub-Profiles
**What it does:** Track multiple conditions per patient separately.

**Features:**
- Create multiple condition profiles per patient (e.g., Knee, Hip, Shoulder, Ankle, Back)
- Each condition has:
  - Diagnosis details
  - Date of injury/onset
  - Treatment goals
  - Assigned exercise programs
  - Progress tracking
  - Assessment history
  - Treatment notes
- Condition status (Active treatment, Maintenance, Resolved)
- Visual body map to select affected areas

**User Story:** *"As a physiotherapist treating a patient with both knee and shoulder issues, I want to track each condition separately with different exercise programs."*

---

### 3.3 EXERCISE LIBRARY

#### 3.3.1 Exercise Database
**What it does:** Comprehensive library of rehabilitation exercises.

**Features:**
- Pre-loaded exercise library with 500+ exercises
- Video demonstrations for each exercise
- Written instructions and explanations
- Images/photos of exercises
- Exercise categorization by:
  - Body part (Shoulder, Knee, Hip, Ankle, Back, Neck, Elbow, Wrist, etc.)
  - Movement type (Flexion, Extension, Rotation, Abduction, Adduction, Combined movements)
  - Difficulty level (Beginner, Intermediate, Advanced)
  - Equipment needed (Bodyweight, Resistance band, Weights, Ball, etc.)
  - Exercise type (Strengthening, Stretching, Mobility, Balance, Proprioception)
- Search and filter functionality
- Exercise tags and keywords
- Exercise variations

**User Story:** *"As a physiotherapist, I want to quickly find shoulder external rotation exercises so I can add them to my patient's program."*

#### 3.3.2 Custom Exercise Upload
**What it does:** Allows professionals to add their own exercises.

**Features:**
- Upload custom exercise videos (MP4, MOV formats, max 100MB)
- Add custom exercise images
- Write custom instructions
- Categorize custom exercises using same system
- Custom exercises remain private to the practice
- Option to share custom exercises with other professionals in same practice
- Edit and delete custom exercises
- Version control for exercise updates

**User Story:** *"As a physiotherapist with specialized techniques, I want to video my own exercises and add them to my library for my patients."*

#### 3.3.3 Exercise Request System
**What it does:** Allows professionals to request new exercises to be added to the main library.

**Features:**
- Submit exercise request form (exercise name, description, category)
- Upload reference videos/images
- Track request status (Pending, Approved, Added, Declined)
- Notification when request is processed
- Admin review panel for exercise requests

**User Story:** *"As a physiotherapist, I want to request a specific exercise that's not in the library so it can be added for everyone to use."*

---

### 3.4 EXERCISE PROGRAM MANAGEMENT

#### 3.4.1 Program Builder
**What it does:** Create customized exercise programs for patients.

**Features:**
- Drag-and-drop program builder
- Add exercises from library or custom uploads
- Set exercise parameters for each exercise:
  - Sets
  - Repetitions
  - Hold time
  - Rest periods
  - Frequency (times per day/week)
  - Duration (weeks)
- Add notes/instructions for specific exercises
- Reorder exercises within program
- Program preview before assigning
- Assign program to specific patient condition
- Set program start and end dates
- Schedule program phases (Week 1-2, Week 3-4, etc.)

**User Story:** *"As a physiotherapist, I want to create a 6-week knee rehabilitation program with specific exercises, sets, and reps for my post-surgery patient."*

#### 3.4.2 Program Templates
**What it does:** Save and reuse common exercise programs.

**Features:**
- Save any program as a template
- Template library organized by:
  - Condition type
  - Treatment phase
  - Custom categories
- Template naming and description
- Edit templates
- Duplicate templates
- Share templates with other professionals in practice
- Apply template to patient with option to customize
- Template usage tracking

**User Story:** *"As a physiotherapist who treats many ACL reconstruction patients, I want to save my standard protocol as a template so I don't have to rebuild it each time."*

#### 3.4.3 Program Assignment & Tracking
**What it does:** Assign programs to patients and monitor compliance.

**Features:**
- Assign programs to specific patient conditions
- Send program notifications to patients (via mobile app)
- Track patient completion rates
- View patient exercise logs
- Modify active programs
- Pause/resume programs
- Program completion status
- Historical program archive

---

### 3.5 ASSESSMENT & QUESTIONNAIRES

#### 3.5.1 Standardized Questionnaires
**What it does:** Administer validated assessment tools to track patient outcomes.

**Required Questionnaires:**
1. **VAS Pain Scale** (Visual Analog Scale)
   - 0-10 pain rating
   - Body part selection
   - Pain type (Rest, Activity, Night)

2. **STarT Back Screening Tool**
   - 9-question assessment
   - Risk stratification (Low, Medium, High)
   - Automatic scoring

3. **Hip Assessment**
   - Hip Outcome Score (HOS)
   - Pain and function questions
   - Activity limitations

4. **Knee Assessment**
   - Knee Injury and Osteoarthritis Outcome Score (KOOS)
   - Pain, symptoms, daily activities, sport/recreation, quality of life

5. **Shoulder Assessment**
   - Shoulder Pain and Disability Index (SPADI)
   - Pain and disability subscales

6. **Ankle Assessment**
   - Foot and Ankle Outcome Score (FAOS)
   - Pain, symptoms, daily activities, sport/recreation, quality of life

**Features:**
- Digital questionnaire administration
- Automatic scoring and interpretation
- Progress tracking over time (baseline, follow-up assessments)
- Visual graphs and charts
- Compare assessments across time points
- Export assessment results
- Schedule recurring assessments
- Patient can complete via mobile app or web portal

**User Story:** *"As a physiotherapist, I want to send a knee assessment to my patient and automatically see their score improve over 8 weeks of treatment."*

#### 3.5.2 Custom Questionnaires
**What it does:** Create practice-specific assessment forms.

**Features:**
- Custom question builder (multiple choice, scale, text, yes/no)
- Save custom questionnaires as templates
- Assign to patients
- View responses and track over time

---

### 3.6 REPORTING & DOCUMENTATION

#### 3.6.1 PDF Protocol Generation
**What it does:** Create printable exercise protocols for patients.

**Features:**
- Generate PDF with exercise images and written instructions
- Include practice branding/logo
- Customizable layout templates
- Include or exclude:
  - Exercise images
  - Written instructions
  - Sets/reps/frequency
  - Practice contact info
  - Patient name and date
- Download and print
- Email directly to patient
- Save to patient file

**User Story:** *"As a physiotherapist, I want to print a PDF of my patient's home exercise program with images and instructions so they can follow it at home."*

#### 3.6.2 Progress Reports
**What it does:** Generate comprehensive patient progress reports.

**Features:**
- Treatment summary reports
- Assessment score comparisons
- Exercise compliance rates
- Visual progress charts
- Customizable date ranges
- Export to PDF
- Include notes and observations

---

### 3.7 DASHBOARD & ANALYTICS

#### 3.7.1 Professional Dashboard
**What it does:** Overview of daily activities and patient status.

**Features:**
- Today's appointments (if integrated with scheduling)
- Active patient count
- Pending assessments
- Recent patient activity
- Quick access to frequent actions
- Notifications and alerts
- Recent exercise program assignments

**User Story:** *"As a physiotherapist starting my day, I want to see which patients need follow-up assessments and who hasn't completed their exercises."*

#### 3.7.2 Practice Analytics
**What it does:** Insights for practice management (Admin only).

**Features:**
- Total patient count and trends
- Professional productivity metrics
- Most used exercises and programs
- Patient outcome statistics
- Assessment completion rates
- Storage usage
- System usage reports

---

### 3.8 COMMUNICATION

#### 3.8.1 Patient Messaging
**What it does:** Secure communication between professionals and patients.

**Features:**
- In-app messaging system
- Send messages to individual patients
- Attach documents or exercise links
- Message history
- Read receipts
- Push notifications for new messages

**User Story:** *"As a physiotherapist, I want to send a quick message to my patient to check how they're feeling after starting their new program."*

#### 3.8.2 Notifications
**What it does:** Keep users informed of important events.

**Features:**
- Email notifications
- In-app notifications
- Notification preferences
- Notifications for:
  - New patient registrations
  - Completed assessments
  - Exercise program milestones
  - Missed exercises
  - Messages received
  - Exercise requests processed

---

### 3.9 SEARCH & FILTERING

**What it does:** Quickly find information across the system.

**Features:**
- Global search bar
- Search patients by name, ID, condition
- Filter patients by professional, status, condition
- Search exercises by name, category, body part
- Filter programs by template, condition, date
- Advanced filter options
- Save common filter combinations

---

### 3.10 SETTINGS & CONFIGURATION

#### 3.10.1 Practice Settings
- Practice information editing
- Branding customization
- Default templates
- Email templates
- Notification preferences
- Data retention policies

#### 3.10.2 Professional Settings
- Personal information
- Profile photo
- Signature
- Notification preferences
- Default program settings

---

## 4. NON-FUNCTIONAL REQUIREMENTS

### 4.1 Performance
- Page load time: < 2 seconds
- Video streaming: Smooth playback on standard broadband
- Support 100+ concurrent users
- Database queries: < 500ms response time

### 4.2 Security
- HTTPS encryption for all data transmission
- Firebase Authentication with secure token management
- Role-based access control
- Data encryption at rest
- HIPAA/POPIA compliance
- Regular security audits
- Automatic session timeout after 30 minutes of inactivity
- Audit logs for sensitive actions

### 4.3 Reliability
- 99.9% uptime SLA
- Automated daily backups
- Disaster recovery plan
- Data redundancy

### 4.4 Usability
- Intuitive, modern interface
- Responsive design (desktop, tablet)
- Consistent navigation
- Helpful tooltips and guidance
- Minimal clicks to complete common tasks
- Keyboard shortcuts for power users

### 4.5 Scalability
- Support for practices with 1-50 professionals
- Handle 10,000+ patient records per practice
- Store unlimited exercise videos (within storage limits)
- Horizontal scaling capability

### 4.6 Compatibility
- Modern browsers: Chrome, Firefox, Safari, Edge (latest 2 versions)
- Minimum screen resolution: 1280x720

### 4.7 Data Management
- Export patient data (CSV, PDF)
- Import patient data (CSV)
- Data retention according to legal requirements
- GDPR/POPIA data deletion requests

---

## 5. USER INTERFACE REQUIREMENTS

### 5.1 Design Principles
- Clean, professional medical aesthetic
- Calming color palette (blues, greens, whites)
- Large, readable fonts
- Clear visual hierarchy
- Accessibility compliance (WCAG 2.1 AA)
- Consistent iconography

### 5.2 Key Screens
1. **Login/Registration**
2. **Practice Dashboard**
3. **Professional Dashboard**
4. **Patient List**
5. **Patient Profile**
6. **Condition Sub-Profile**
7. **Exercise Library**
8. **Exercise Detail View**
9. **Program Builder**
10. **Template Library**
11. **Assessment Administration**
12. **Assessment Results**
13. **Reports**
14. **Settings**
15. **Messaging**

---

## 6. INTEGRATION REQUIREMENTS

### 6.1 Firebase Services
- **Firebase Authentication:** User management
- **Cloud Firestore:** Database
- **Firebase Storage:** Video and image storage
- **Cloud Functions:** Backend logic
- **Firebase Hosting:** Web hosting
- **Firebase Cloud Messaging:** Notifications

### 6.2 Third-Party Services (Optional/Future)
- Payment gateway (Stripe/PayFast) for subscriptions
- Email service (SendGrid) for transactional emails
- SMS notifications (Twilio)
- Video transcoding service for optimal streaming

---

## 7. DEPLOYMENT & MAINTENANCE

### 7.1 Deployment
- Staging environment for testing
- Production environment
- CI/CD pipeline for automated deployments
- Version control (Git)

### 7.2 Maintenance
- Regular updates and bug fixes
- Security patches
- Feature enhancements based on feedback
- Technical support
- User documentation and training materials

---

## 8. ASSUMPTIONS & CONSTRAINTS

### 8.1 Assumptions
- Users have stable internet connection
- Users have modern devices and browsers
- Practice has necessary legal permissions for patient data storage
- Video content will be professionally produced or user-generated

### 8.2 Constraints
- Firebase free tier limitations (will require paid plan)
- Video storage costs scale with usage
- Compliance with local healthcare regulations
- Browser compatibility limitations

---

## 9. SUCCESS CRITERIA

The web application will be considered successful when:
1. ✅ Practices can register and create professional profiles
2. ✅ Professionals can manage patient records and conditions
3. ✅ Exercise library is fully functional with video playback
4. ✅ Custom exercise upload works reliably
5. ✅ Program builder allows creating and assigning programs
6. ✅ Templates can be saved and reused
7. ✅ All 6 questionnaires are functional with automatic scoring
8. ✅ PDF protocols generate correctly with images
9. ✅ System is secure and compliant with data protection laws
10. ✅ Users can complete common tasks efficiently

---

## 10. FUTURE ENHANCEMENTS (Phase 2)

- Appointment scheduling and calendar
- Billing and invoicing
- Insurance claim management
- Telehealth video consultations
- AI-powered exercise recommendations
- Integration with wearable devices
- Multi-language support
- Advanced analytics and machine learning insights
- Patient portal (web-based)
- API for third-party integrations

---

## 11. GLOSSARY

- **Practice:** A physiotherapy or rehabilitation business
- **Professional:** A physiotherapist, chiropractor, or other rehabilitation specialist
- **Sub-profile:** A condition-specific profile under a patient (e.g., knee injury)
- **Program:** A collection of exercises assigned to a patient
- **Template:** A saved program that can be reused
- **Assessment:** A standardized questionnaire to measure patient outcomes
- **Protocol:** A printed document with exercise instructions

---

## DOCUMENT APPROVAL

**Prepared by:** QuantumX Software  
**Client Review Required:** Yes  
**Approval Status:** Pending Client Review

---

*This document is subject to change based on client feedback and technical discoveries during development.*
