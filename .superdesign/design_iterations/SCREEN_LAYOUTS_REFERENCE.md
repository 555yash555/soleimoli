# SoleGoes - Screen Layouts Reference
## Option15 Design System - All Screens

### Implementation Status
✅ **All Screens Completed** (10 screens - Dark & Light themes)

**Implemented Screens:**
1. ✅ Login Screen (option15_login.html)
2. ✅ Onboarding Screen - 4 slides (option15_onboarding.html)
3. ✅ OTP Verification Screen (option15_otp.html)
4. ✅ Preferences Screen (option15_preferences.html)
5. ✅ Profile Setup Screen (option15_profile_setup.html)
6. ✅ Home/Feed Screen (option15_mobile.html)
7. ✅ Trip Detail Screen (option15_trip_detail.html)
8. ✅ Payment Method Screen (option15_payment_method.html)
9. ✅ Payment Confirmation Screen (option15_payment_confirmation.html)
10. ✅ Profile Page Screen (option15_profile_page.html)

**Navigation Flow:**
Onboarding → Login → OTP → Profile Setup → Preferences → Home → Trip Detail → Payment Method → Payment Confirmation

**Additional Features:**
- All screens available in Dark & Light themes
- Theme switchers on every screen
- Proper back button navigation
- No validation blocking (easy demo navigation)
- Profile page accessible from Home (avatar button)

---

## **1. LOGIN SCREEN** ✅ COMPLETED

```
┌─────────────────────────────────────┐
│  ←                            ☀️/🌙 │ Header
├─────────────────────────────────────┤
│                                     │
│                                     │
│           [  SoleGoes  ]            │ Logo (Large)
│      Travel Solo, Meet People       │ Tagline
│                                     │
│                                     │
│         Welcome Back 👋              │ Title
│   Sign in to continue your journey  │ Subtitle
│                                     │
│   Email or Phone                    │ Label
│   ┌───────────────────────────────┐ │
│   │ 📧  email@example.com        │ │ Input
│   └───────────────────────────────┘ │
│                                     │
│   Password                          │ Label
│   ┌───────────────────────────────┐ │
│   │ 🔒  ••••••••••              │ │ Input
│   └───────────────────────────────┘ │
│                     Forgot Password?│ Link
│                                     │
│   ┌───────────────────────────────┐ │
│   │        Sign In               │ │ Primary Button
│   └───────────────────────────────┘ │
│                                     │
│   ─────── or continue with ───────  │ Divider
│                                     │
│   ┌──────────────┐ ┌──────────────┐ │
│   │  🔵  Google  │ │  🍎  Apple   │ │ Social Buttons
│   └──────────────┘ └──────────────┘ │
│                                     │
│                                     │
│   Don't have an account? Sign Up    │ Footer Link
│                                     │
└─────────────────────────────────────┘
```

**Key Features:**
- Centered layout with max-width 400px
- Glassmorphism inputs with backdrop blur
- Social login options (Google, Apple)
- Theme toggle (dark/light)
- Animated fade-in entrance
- Link to onboarding for new users

---

## **2. ONBOARDING SCREEN** ✅ COMPLETED (4 screens with pagination)

### Screen 1/4
```
┌─────────────────────────────────────┐
│                              Skip → │ Header
├─────────────────────────────────────┤
│                                     │
│          [ILLUSTRATION]             │ Hero Image/Animation
│             🌍✈️🎒                    │ (Large, centered)
│                                     │
│                                     │
│        Discover New Places          │ Title (Bold)
│                                     │
│   Travel solo but never alone.      │ Description
│   Connect with fellow travelers     │ (2-3 lines)
│   and explore the world together    │
│                                     │
│                                     │
│          ● ○ ○ ○                    │ Progress Dots
│                                     │
│                                     │
│   ┌───────────────────────────────┐ │
│   │           Next                │ │ Primary Button
│   └───────────────────────────────┘ │
│                                     │
│   Already have an account? Sign In  │ Footer Link
│                                     │
└─────────────────────────────────────┘
```

### Screen 2/4
```
        Meet Like-Minded Travelers
    Join groups of solo travelers
    with similar interests and make
    lifelong friendships

    Progress: ○ ● ○ ○
```

### Screen 3/4
```
        Safe & Verified Experiences
    All trips curated by trusted
    agencies with verified reviews
    from real travelers

    Progress: ○ ○ ● ○
```

### Screen 4/4
```
        Easy Booking & Payment
    Simple booking process with
    secure payments and instant
    confirmation

    Progress: ○ ○ ○ ●
    Button: Get Started
```

---

## **3. OTP VERIFICATION SCREEN** ✅ COMPLETED

```
┌─────────────────────────────────────┐
│  ←                            ☀️/🌙 │ Header
├─────────────────────────────────────┤
│                                     │
│                                     │
│              📱                      │ Large Icon
│                                     │
│        Verify Your Number           │ Title
│                                     │
│   We sent a code to +91 98765 43210│ Subtitle
│              Edit                   │ Edit link
│                                     │
│   Enter 6-digit code                │ Label
│                                     │
│     ┌───┐ ┌───┐ ┌───┐ ┌───┐         │
│     │ 5 │ │ 2 │ │ 7 │ │ 9 │         │ OTP Input Boxes
│     └───┘ └───┘ └───┘ └───┘         │ (6 boxes, large)
│     ┌───┐ ┌───┐                     │
│     │ 1 │ │ 4 │                     │
│     └───┘ └───┘                     │
│                                     │
│        Didn't receive code?         │
│            Resend (30s)             │ Timer/Resend Link
│                                     │
│   ┌───────────────────────────────┐ │
│   │          Verify               │ │ Primary Button
│   └───────────────────────────────┘ │
│                                     │
│                                     │
└─────────────────────────────────────┘
```

**Key Features:**
- 6 large input boxes for OTP digits
- Auto-advance to next box on input
- Resend timer (30 seconds countdown)
- Edit phone number option
- Shake animation on error
- Success animation with checkmarks

---

## **4. PREFERENCES SCREEN** ✅ COMPLETED (Enhanced with Budget & Traits)

```
┌─────────────────────────────────────┐
│  ←              (2/4)          Skip →│ Header w/ Progress
├─────────────────────────────────────┤
│                                     │
│    Tell us about your preferences   │ Title
│   Help us personalize your trips    │ Subtitle
│                                     │
│   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ │ Scrollable Content
│                                     │
│   Travel Interests                  │ Section Title
│   (Select at least 3)               │ Helper
│                                     │
│   ┌──────────────┐ ┌──────────────┐ │
│   │   🏖️ Beach   │ │  🏔️ Mountain │ │ Category Pills
│   │   [Selected] │ │             │ │ (2 columns)
│   └──────────────┘ └──────────────┘ │
│   ┌──────────────┐ ┌──────────────┐ │
│   │ 🏛️ Heritage  │ │ 🎉 Adventure │ │
│   │             │ │   [Selected] │ │
│   └──────────────┘ └──────────────┘ │
│   ┌──────────────┐ ┌──────────────┐ │
│   │  🍜 Food     │ │  🎨 Art      │ │
│   │   [Selected] │ │             │ │
│   └──────────────┘ └──────────────┘ │
│   ┌──────────────┐ ┌──────────────┐ │
│   │  🎵 Music    │ │  🏕️ Camping  │ │
│   │             │ │             │ │
│   └──────────────┘ └──────────────┘ │
│   ┌──────────────┐ ┌──────────────┐ │
│   │  🧘 Wellness │ │  🎿 Sports   │ │
│   │             │ │             │ │
│   └──────────────┘ └──────────────┘ │
│   ┌──────────────┐ ┌──────────────┐ │
│   │  🌃 Nightlife│ │  🛍️ Shopping │ │
│   │             │ │             │ │
│   └──────────────┘ └──────────────┘ │
│                                     │
│   Average Budget per Trip           │ Section Title
│   (Select one)                      │ Helper
│                                     │
│   ┌───────────────────────────────┐ │
│   │  💰  Under ₹10,000            │ │ Budget Options
│   │                               │ │
│   ├───────────────────────────────┤ │
│   │  💰💰  ₹10,000 - ₹25,000      │ │
│   │  [Selected]                   │ │
│   ├───────────────────────────────┤ │
│   │  💰💰💰  ₹25,000 - ₹50,000    │ │
│   │                               │ │
│   ├───────────────────────────────┤ │
│   │  💰💰💰💰  ₹50,000+            │ │
│   │                               │ │
│   └───────────────────────────────┘ │
│                                     │
│   Travel Style                      │ Section Title
│   (Select one)                      │ Helper
│                                     │
│   ┌──────────────┐ ┌──────────────┐ │
│   │  🎒 Backpack │ │  🏨 Comfort  │ │ Style Pills
│   │   [Selected] │ │             │ │
│   └──────────────┘ └──────────────┘ │
│   ┌──────────────┐ ┌──────────────┐ │
│   │  👑 Luxury   │ │  🌿 Eco     │ │
│   │             │ │             │ │
│   └──────────────┘ └──────────────┘ │
│                                     │
│   Trip Duration Preference          │ Section Title
│   (Select one)                      │ Helper
│                                     │
│   ┌──────────────┐ ┌──────────────┐ │
│   │  📅 Weekend  │ │  📆 Week     │ │ Duration Pills
│   │   (2-3 days) │ │   (5-7 days) │ │
│   │   [Selected] │ │             │ │
│   └──────────────┘ └──────────────┘ │
│   ┌──────────────┐ ┌──────────────┐ │
│   │  📋 Extended │ │  🗓️ Flexible │ │
│   │  (10+ days)  │ │   (Any)      │ │
│   │             │ │             │ │
│   └──────────────┘ └──────────────┘ │
│                                     │
│   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ │
│                                     │
│   ┌───────────────────────────────┐ │
│   │        Continue              │ │ Primary Button
│   └───────────────────────────────┘ │
│                                     │
└─────────────────────────────────────┘
```

**Key Features:**
- Multi-select interests (min 3)
- Single-select budget ranges (4 tiers)
- Travel style selection
- Trip duration preference
- Progress indicator (2/4)
- Skip option for quick onboarding
- Validation before continue

---

## **5. PROFILE SETUP SCREEN** ✅ COMPLETED (Enhanced)

```
┌─────────────────────────────────────┐
│  ←              (3/4)               │ Header w/ Progress
├─────────────────────────────────────┤
│                                     │
│        Complete Your Profile        │ Title
│                                     │
│            ┌─────────┐              │
│            │  [IMG]  │  📷          │ Profile Photo Upload
│            │  Add    │              │ (Circular, centered)
│            └─────────┘              │
│                                     │
│   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ │ Scrollable Content
│                                     │
│   Basic Information                 │ Section Title
│                                     │
│   Full Name *                       │
│   ┌───────────────────────────────┐ │
│   │ 👤  Enter your name          │ │ Input
│   └───────────────────────────────┘ │
│                                     │
│   Date of Birth *                   │
│   ┌───────────────────────────────┐ │
│   │ 📅  DD / MM / YYYY           │ │ Input
│   └───��───────────────────────────┘ │
│                                     │
│   Gender *                          │
│   ┌──────┐ ┌──────┐ ┌──────┐       │
│   │ Male │ │Female│ │Other │       │ Radio Pills
│   │ [✓]  │ │      │ │      │       │
│   └──────┘ └──────┘ └──────┘       │
│                                     │
│   City *                            │
│   ┌───────────────────────────────┐ │
│   │ 📍  Select your city         │ │ Dropdown
│   └───────────────────────────────┘ │
│                                     │
│   About You                         │ Section Title
│                                     │
│   Occupation                        │
│   ┌───────────────────────────────┐ │
│   │ 💼  e.g., Software Engineer  │ │ Input
│   └───────────────────────────────┘ │
│                                     │
│   Languages You Speak               │
│   (Select all that apply)           │ Helper
│   ┌────────┐ ┌────────┐ ┌────────┐  │
│   │English │ │ Hindi  │ │Marathi │  │ Language Pills
│   │  [✓]   │ │  [✓]   │ │       │  │ (Multi-select)
│   └────────┘ └────────┘ └────────┘  │
│   ┌────────┐ ┌────────┐ ┌────────┐  │
│   │ Tamil  │ │ Telugu │ │Bengali │  │
│   │       │ │       │ │       │  │
│   └────────┘ └────────┘ └────────┘  │
│   ┌────────┐                        │
│   │ +More  │                        │
│   └────────┘                        │
│                                     │
│   Personality Traits                │ Section Title
│   (Help others know you better)     │ Helper
│                                     │
│   ┌──────────────┐ ┌──────────────┐ │
│   │ 🗣️ Outgoing  │ │ 📚 Introverted│ │ Trait Pills
│   │   [Selected] │ │             │ │
│   └──────────────┘ └──────────────┘ │
│   ┌──────────────┐ ┌──────────────┐ │
│   │ 🌅 Early Bird│ │ 🌙 Night Owl │ │
│   │   [Selected] │ │             │ │
│   └──────────────┘ └──────────────┘ │
│   ┌──────────────┐ ┌──────────────┐ │
│   │ 📸 Photographer│ │ 🎮 Gamer   │ │
│   │             │ │   [Selected] │ │
│   └──────────────┘ └──────────────┘ │
│   ┌──────────────┐ ┌──────────────┐ │
│   │ 🍷 Foodie    │ │ 🏃 Fitness   │ │
│   │   [Selected] │ │             │ │
│   └──────────────┘ └──────────────┘ │
│   ┌──────────────┐ ┌──────────────┐ │
│   │ 🎭 Creative  │ │ 🔍 Planner   │ │
│   │             │ │   [Selected] │ │
│   └──────────────┘ └──────────────┘ │
│   ┌──────────────┐ ┌──────────────┐ │
│   │ 🌟 Spontaneous│ │ 🤝 Team Player│ │
│   │   [Selected] │ │             │ │
│   └──────────────┘ └──────────────┘ │
│                                     │
│   Bio (Optional)                    │
│   ┌───────────────────────────────┐ │
│   │ Tell others about yourself,  │ │ Textarea
│   │ your travel experiences...   │ │
│   │                              │ │
│   └───────────────────────────────┘ │
│                                     │
│   Social Media (Optional)           │ Section Title
│   ┌───────────────────────────────┐ │
│   │ 📷  Instagram handle         │ │ Input
│   └───────────────────────────────┘ │
│                                     │
│   Emergency Contact                 │ Section Title
│   ┌───────────────────────────────┐ │
│   │ 👤  Contact name             │ │ Input
│   └───────────────────────────────┘ │
│   ┌───────────────────────────────┐ │
│   │ 📞  +91 Phone number         │ │ Input
│   └───────────────────────────────┘ │
│                                     │
│   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ │
│                                     │
│   ┌───────────────────────────────┐ │
│   │      Complete Profile        │ │ Primary Button
│   └───────────────────────────────┘ │
│                                     │
└─────────────────────────────────────┘
```

**Key Features:**
- Profile photo upload with camera icon
- Required fields marked with *
- Basic info (name, DOB, gender, city)
- Occupation field
- Multi-select languages with "More" option
- 12 personality trait options
- Optional bio textarea
- Instagram handle (optional)
- Emergency contact (required)
- Form validation before submission

---

## **6. PROFILE PAGE SCREEN** ✅ COMPLETED

```
┌─────────────────────────────────────┐
│  ←      Profile           ⚙️  ☀️/🌙 │ Header
├─────────────────────────────────────┤
│                                     │
│         ┌───────────────┐           │
│         │   [AVATAR]    │           │ Profile Photo
│         │     Edit      │           │ (Large, centered)
│         └───────────────┘           │
│                                     │
│          Rahul Sharma                │ Name (Bold)
│       rahul.sharma@email.com        │ Email
│         +91 98765 43210             │ Phone
│                                     │
│   ┌──────────────┐ ┌──────────────┐ │
│   │   5 Trips    │ │  3 Upcoming  │ │ Stats Cards
│   └──────────────┘ └──────────────┘ │
│                                     │
├─────────────────────────────────────┤
│                                     │
│   Personal Information              │ Section
│   ┌───────────────────────────────┐ │
│   │ 📧 Email               →      │ │ List Item
│   ├───────────────────────────────┤ │
│   │ 📱 Phone               →      │ │
│   ├───────────────────────────────┤ │
│   │ 📅 Date of Birth       →      │ │
│   ├───────────────────────────────┤ │
│   │ ⚧ Gender               →      │ │
│   └───────────────────────────────┘ │
│                                     │
│   Travel Preferences                │ Section
│   ┌───────────────────────────────┐ │
│   │ 🎒 Interests           →      │ │
│   ├───────────────────────────────┤ │
│   │ 💰 Budget Range        →      │ │
│   └───────────────────────────────┘ │
│                                     │
│   Payment & Bookings                │ Section
│   ┌───────────────────────────────┐ │
│   │ 💳 Payment Methods     →      │ │
│   ├───────────────────────────────┤ │
│   │ 📜 Booking History     →      │ │
│   └───────────────────────────────┘ │
│                                     │
│   ┌───────────────────────────────┐ │
│   │        Logout                │ │ Logout Button
│   └───────────────────────────────┘ │
│                                     │
└─────────────────────────────────────┘
```

**Key Features:**
- Large profile photo with edit option
- Name, email, phone display
- Stats cards (trips completed, upcoming)
- Grouped sections: Personal, Travel, Payment
- Settings gear icon
- Theme toggle
- Logout button at bottom

---

## **7. PAYMENT METHOD SCREEN** ✅ COMPLETED

```
┌─────────────────────────────────────┐
│  ←    Payment Method          ☀️/🌙 │ Header
├─────────────────────────────────────┤
│                                     │
│   Select Payment Method             │ Title
│                                     │
│   Cards & UPI                       │ Category
│   ┌───────────────────────────────┐ │
│   │ 💳  Credit/Debit Card   →    │ │ Option (Selected)
│   └───────────────────────────────┘ │
│   ┌───────────────────────────────┐ │
│   │ 📱  UPI                  →    │ │ Option
│   └───────────────────────────────┘ │
│                                     │
│   Wallets                           │ Category
│   ┌───────────────────────────────┐ │
│   │ 👛  Paytm                →    │ │ Option
│   └───────────────────────────────┘ │
│   ┌───────────────────────────────┐ │
│   │ 💰  PhonePe              →    │ │ Option
│   └───────────────────────────────┘ │
│   ┌───────────────────────────────┐ │
│   │ 🅖  Google Pay           →    │ │ Option
│   └───────────────────────────────┘ │
│                                     │
│   Banking                           │ Category
│   ┌───────────────────────────────┐ │
│   │ 🏦  Net Banking          →    │ │ Option
│   └───────────────────────────────┘ │
│                                     │
│   ────────────────────────────────  │
│                                     │
│   Amount: ₹15,000                   │ Amount Display
│                                     │
│   ┌───────────────────────────────┐ │
│   │        Proceed to Pay        │ │ Primary Button
│   └───────────────────────────────┘ │
│                                     │
└─────────────────────────────────────┘
```

**Key Features:**
- Grouped payment options by category
- Selected state with visual indicator
- Fixed amount display at bottom
- Radio-style selection (single choice)
- Proceed button always visible

---

## **8. PAYMENT CONFIRMATION SCREEN** ✅ COMPLETED

```
┌─────────────────────────────────────┐
│              ✕                      │ Close Button
├─────────────────────────────────────┤
│                                     │
│                                     │
│              ┌─────┐                │
│              │  ✓  │                │ Success Icon
│              └─────┘                │ (Large, animated)
│                                     │
│         Payment Successful!         │ Title
│                                     │
│   Your booking has been confirmed   │ Subtitle
│                                     │
│   ─────────────────────────────────  │
│                                     │
│   Transaction Details               │ Section Title
│                                     │
│   Trip Name                         │
│   Bali Beach Escape                 │
│                                     │
│   Amount Paid                       │
│   ₹15,000                           │
│                                     │
│   Transaction ID                    │
│   TXN1234567890                     │
│                                     │
│   Date & Time                       │
│   Dec 28, 2024 at 3:45 PM           │
│                                     │
│   Payment Method                    │
│   •••• 4242 (Visa)                  │
│                                     │
│   ──────────��──────────────────────  │
│                                     │
│   ┌───────────────────────────────┐ │
│   │    Download Receipt          │ │ Secondary Button
│   └───────────────────────────────┘ │
│                                     │
│   ┌───────────────────────────────┐ │
│   │    View Trip Details         │ │ Primary Button
│   └───────────────────────────────┘ │
│                                     │
│   ┌───────────────────────────────┐ │
│   │    Back to Home              │ │ Tertiary Button
│   └───────────────────────────────┘ │
│                                     │
└─────────────────────────────────────┘
```

**Key Features:**
- Large animated success checkmark
- Full transaction details
- Three action buttons (hierarchy)
- Close button (top right)
- Receipt download option
- Modal-style overlay design

---

## Design System Summary

### **Colors**
- Dark BG: `#0d0d0d`
- Light BG: `#fafafa`
- Dark Text: `#ffffff`
- Light Text: `#1a1a1a`

### **Typography**
- Font: Manrope (400, 500, 600, 700, 800)
- Base: 14px
- Titles: 1.75rem - 2.5rem (800 weight)

### **Spacing**
- Base: 1rem (16px)
- Section gap: 1.5rem - 2rem
- Input padding: 0.875rem

### **Border Radius**
- Inputs/Buttons: 0.875rem
- Cards: 0.75rem - 1.25rem
- Icons: 50% (circular)

### **Glassmorphism**
- Dark: `rgba(255,255,255,0.05)` + blur(8px)
- Light: `rgba(255,255,255,0.5)` + blur(10px)

### **Transitions**
- Standard: 0.3s ease
- Quick: 0.2s ease
- Hover lift: translateY(-2px)

---

**File Created:** 2024-10-06
**Version:** Option15 Final
**Status:** Ready for Implementation
