# HTML/CSS to React Native Conversion Analysis
## SoleGoes App - Complete Implementation Guide

---

## 📊 **PROJECT OVERVIEW**

### **Total Screens: 10 (20 files with themes)**
1. ✅ Login
2. ✅ Onboarding (4 slides)
3. ✅ OTP Verification
4. ✅ Profile Setup
5. ✅ Preferences
6. ✅ Home/Feed
7. ✅ Trip Detail
8. ✅ Payment Method
9. ✅ Payment Confirmation
10. ✅ Profile Page

**Each screen has:** Dark theme + Light theme = 20 HTML files

---

## 🏗️ **ARCHITECTURE ANALYSIS**

### **1. Component Structure Pattern**

Every HTML screen follows this structure:

```html
<!DOCTYPE html>
<html>
<head>
    <!-- Meta tags -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">

    <!-- External Resources -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://unpkg.com/lucide@latest/dist/umd/lucide.min.js"></script>

    <!-- Inline Styles -->
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Manrope:wght@400;500;600;700;800&display=swap');

        /* Global resets */
        * { box-sizing: border-box; -webkit-tap-highlight-color: transparent; }
        html { font-size: 14px; }
        body { background: #0d0d0d; font-family: 'Manrope', sans-serif; }

        /* Component-specific styles */
        .component-class { ... }
    </style>
</head>
<body>
    <!-- Content -->
    <div class="container">
        <header class="header">...</header>
        <main class="content">...</main>
        <footer class="footer">...</footer>
    </div>

    <!-- JavaScript for interactions -->
    <script>
        lucide.createIcons();
        // Event handlers
    </script>
</body>
</html>
```

---

## 🎨 **CSS TO REACT NATIVE MAPPING**

### **Core Principle: React Native uses JavaScript objects, not CSS**

#### **Example: Login Screen Header**

**HTML/CSS:**
```css
.header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 3rem;
}

.back-btn {
    width: 40px;
    height: 40px;
    background: rgba(255, 255, 255, 0.1);
    backdrop-filter: blur(8px);
    border: 1px solid rgba(255, 255, 255, 0.15);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
}
```

**React Native Equivalent:**
```javascript
import { View, TouchableOpacity, StyleSheet } from 'react-native';
import { BlurView } from '@react-native-community/blur';
import Icon from 'react-native-vector-icons/Feather';

// Component
const Header = () => (
  <View style={styles.header}>
    <TouchableOpacity style={styles.backBtn}>
      <BlurView style={styles.blur} blurType="light" blurAmount={8}>
        <Icon name="arrow-left" size={20} color="#fff" />
      </BlurView>
    </TouchableOpacity>
  </View>
);

// Styles
const styles = StyleSheet.create({
  header: {
    flexDirection: 'row',
    justifyContent: 'space-between',
    alignItems: 'center',
    marginBottom: 48, // 3rem = 48px (14px base * 3)
  },
  backBtn: {
    width: 40,
    height: 40,
    borderRadius: 20, // 50% = half of width/height
    overflow: 'hidden', // For blur to work
  },
  blur: {
    width: '100%',
    height: '100%',
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: 'rgba(255, 255, 255, 0.1)',
    borderWidth: 1,
    borderColor: 'rgba(255, 255, 255, 0.15)',
  },
});
```

---

## 📝 **COMPREHENSIVE CSS MAPPING TABLE**

| CSS Property | React Native Equivalent | Notes |
|-------------|------------------------|-------|
| `display: flex` | **Default behavior** | All Views are flexbox by default |
| `flex-direction: column` | **Default** | RN default is column (vs CSS row) |
| `flex-direction: row` | `flexDirection: 'row'` | Must specify for horizontal |
| `justify-content: space-between` | `justifyContent: 'space-between'` | camelCase |
| `align-items: center` | `alignItems: 'center'` | camelCase |
| `gap: 0.5rem` | **No direct equivalent** | Use margins on children |
| `margin: 1rem` | `margin: 16` | rem → pixels (14px base) |
| `margin-bottom: 3rem` | `marginBottom: 48` | Specific sides work |
| `padding: 0.875rem` | `padding: 12.25` | Can use decimals |
| `width: 100%` | `width: '100%'` | String for percentages |
| `width: 40px` | `width: 40` | Number for pixels |
| `height: auto` | **Default** | Don't specify |
| `background: #0d0d0d` | `backgroundColor: '#0d0d0d'` | Full property name |
| `background: rgba(255,255,255,0.1)` | `backgroundColor: 'rgba(255,255,255,0.1)'` | Same format |
| `color: #fff` | `color: '#fff'` | Text components only |
| `font-family: 'Manrope'` | `fontFamily: 'Manrope'` | Platform-specific setup |
| `font-size: 0.875rem` | `fontSize: 12.25` | Convert rem to px |
| `font-weight: 700` | `fontWeight: '700'` | **String!** |
| `font-weight: bold` | `fontWeight: 'bold'` | Named weights work |
| `border-radius: 12px` | `borderRadius: 12` | All corners |
| `border-radius: 50%` | `borderRadius: width/2` | Calculate manually |
| `border: 1px solid #fff` | `borderWidth: 1, borderColor: '#fff'` | Separate properties |
| `border-bottom: 1px solid` | `borderBottomWidth: 1, borderBottomColor: '#fff'` | Specific sides |
| `box-shadow: 0 2px 8px` | `shadowColor, shadowOffset, shadowOpacity, shadowRadius` | Complex! |
| `backdrop-filter: blur(10px)` | `<BlurView>` component | Requires library |
| `position: absolute` | `position: 'absolute'` | Same |
| `position: sticky` | **No direct equivalent** | Use `Animated` or ScrollView header |
| `position: fixed` | **No direct equivalent** | Absolute with specific positioning |
| `top: 0` | `top: 0` | With position: absolute |
| `z-index: 100` | `zIndex: 100` | camelCase |
| `overflow: hidden` | `overflow: 'hidden'` | Works |
| `overflow-x: auto` | **ScrollView** | Use ScrollView component |
| `cursor: pointer` | **N/A** | Use TouchableOpacity |
| `transition: all 0.3s` | **Animated API** | Complex animations |
| `transform: translateY(-2px)` | `transform: [{translateY: -2}]` | Array of objects |
| `transform: scale(1.05)` | `transform: [{scale: 1.05}]` | Array |
| `opacity: 0.5` | `opacity: 0.5` | Same |
| `text-align: center` | `textAlign: 'center'` | Text components |
| `text-decoration: none` | **Default** | No underlines |
| `white-space: nowrap` | `numberOfLines: 1` | On Text component |
| `line-height: 1.6` | `lineHeight: 22.4` | Convert to pixels |
| `letter-spacing: -0.02em` | `letterSpacing: -0.28` | Convert em to px |

---

## 🧩 **COMPONENT BREAKDOWN BY SCREEN**

### **1. LOGIN SCREEN**

**HTML Components:**
- Hero section with image + overlay
- Back button (absolute positioned)
- Theme toggle (absolute positioned)
- Form inputs (email, password)
- Primary button
- Social login buttons
- Footer link

**React Native Components Needed:**
```javascript
import {
  View,
  Text,
  Image,
  TextInput,
  TouchableOpacity,
  ScrollView,
  KeyboardAvoidingView
} from 'react-native';
import { BlurView } from '@react-native-community/blur';
import LinearGradient from 'react-native-linear-gradient';
import Icon from 'react-native-vector-icons/Feather';

// Structure
<KeyboardAvoidingView>
  <ScrollView>
    <View style={styles.heroSection}>
      <Image source={...} style={styles.heroImage} />
      <LinearGradient colors={[...]} style={styles.overlay} />

      <TouchableOpacity style={styles.backBtn}>
        <BlurView>
          <Icon name="arrow-left" />
        </BlurView>
      </TouchableOpacity>

      <TouchableOpacity style={styles.themeToggle}>
        <Icon name="sun" />
      </TouchableOpacity>
    </View>

    <View style={styles.content}>
      <TextInput
        placeholder="Email or Phone"
        style={styles.input}
        placeholderTextColor="rgba(255,255,255,0.4)"
      />

      <TextInput
        placeholder="Password"
        secureTextEntry
        style={styles.input}
      />

      <TouchableOpacity style={styles.primaryBtn}>
        <Text style={styles.btnText}>Sign In</Text>
      </TouchableOpacity>
    </View>
  </ScrollView>
</KeyboardAvoidingView>
```

**Key CSS Conversions:**
- `.hero-section` → Image with absolute positioned gradient
- `.icon-btn` → TouchableOpacity with BlurView
- `.input` → TextInput with glassmorphism background
- `:hover` effects → Use `onPressIn`/`onPressOut` for state

---

### **2. OTP VERIFICATION SCREEN**

**Unique Features:**
- 6 separate input boxes
- Auto-advance on input
- Resend timer countdown

**React Native Implementation:**
```javascript
import { useRef, useState } from 'react';

const OTPScreen = () => {
  const [otp, setOtp] = useState(['', '', '', '', '', '']);
  const inputRefs = useRef([]);

  const handleOtpChange = (value, index) => {
    const newOtp = [...otp];
    newOtp[index] = value;
    setOtp(newOtp);

    // Auto-advance
    if (value && index < 5) {
      inputRefs.current[index + 1].focus();
    }
  };

  return (
    <View style={styles.otpContainer}>
      {otp.map((digit, index) => (
        <TextInput
          key={index}
          ref={ref => inputRefs.current[index] = ref}
          style={styles.otpBox}
          value={digit}
          onChangeText={(value) => handleOtpChange(value, index)}
          keyboardType="number-pad"
          maxLength={1}
        />
      ))}
    </View>
  );
};

const styles = StyleSheet.create({
  otpContainer: {
    flexDirection: 'row',
    justifyContent: 'space-between',
    marginVertical: 24,
  },
  otpBox: {
    width: 50,
    height: 60,
    backgroundColor: 'rgba(255,255,255,0.05)',
    borderWidth: 1,
    borderColor: 'rgba(255,255,255,0.1)',
    borderRadius: 12,
    textAlign: 'center',
    fontSize: 24,
    fontWeight: '700',
    color: '#fff',
  },
});
```

---

### **3. PREFERENCES SCREEN**

**Unique Features:**
- Multi-select chips (interests)
- Single-select budget options
- Scrollable content
- Grid layout (2 columns)

**React Native Implementation:**
```javascript
import { FlatList } from 'react-native';

const PreferencesScreen = () => {
  const [selectedInterests, setSelectedInterests] = useState([]);
  const [selectedBudget, setSelectedBudget] = useState(null);

  const interests = [
    { id: 1, icon: '🏖️', name: 'Beach' },
    { id: 2, icon: '🏔️', name: 'Mountain' },
    // ...
  ];

  const toggleInterest = (id) => {
    if (selectedInterests.includes(id)) {
      setSelectedInterests(prev => prev.filter(i => i !== id));
    } else {
      setSelectedInterests(prev => [...prev, id]);
    }
  };

  return (
    <ScrollView>
      <Text style={styles.sectionTitle}>Travel Interests</Text>
      <View style={styles.grid}>
        {interests.map(interest => (
          <TouchableOpacity
            key={interest.id}
            style={[
              styles.chip,
              selectedInterests.includes(interest.id) && styles.chipActive
            ]}
            onPress={() => toggleInterest(interest.id)}
          >
            <Text>{interest.icon} {interest.name}</Text>
          </TouchableOpacity>
        ))}
      </View>
    </ScrollView>
  );
};

const styles = StyleSheet.create({
  grid: {
    flexDirection: 'row',
    flexWrap: 'wrap',
    justifyContent: 'space-between',
  },
  chip: {
    width: '48%', // 2 columns with gap
    backgroundColor: 'rgba(255,255,255,0.05)',
    padding: 12,
    borderRadius: 12,
    marginBottom: 12,
  },
  chipActive: {
    backgroundColor: 'rgba(255,255,255,0.15)',
    borderWidth: 2,
    borderColor: '#fff',
  },
});
```

---

### **4. HOME/FEED SCREEN**

**Complex Features:**
- Sticky header
- Search bar
- Horizontal scrollable chips
- Featured card with image
- Horizontal trip cards carousel
- Bottom tab navigation

**React Native Implementation:**
```javascript
import { ScrollView, FlatList } from 'react-native';

const HomeScreen = () => {
  return (
    <View style={styles.container}>
      {/* Sticky Header */}
      <View style={styles.header}>
        <Icon name="menu" />
        <Text style={styles.logo}>SoleGoes</Text>
        <Icon name="bell" />
      </View>

      <ScrollView>
        {/* Search */}
        <View style={styles.search}>
          <Icon name="search" />
          <TextInput placeholder="Where to next?" />
        </View>

        {/* Featured Card */}
        <TouchableOpacity style={styles.featured}>
          <Image source={...} />
          <View style={styles.cardBody}>
            <Text style={styles.title}>Bali Beach Escape</Text>
          </View>
        </TouchableOpacity>

        {/* Horizontal Chips */}
        <ScrollView horizontal showsHorizontalScrollIndicator={false}>
          {chips.map(chip => (
            <TouchableOpacity key={chip} style={styles.chip}>
              <Text>{chip}</Text>
            </TouchableOpacity>
          ))}
        </ScrollView>

        {/* Horizontal Trip Cards */}
        <FlatList
          horizontal
          data={trips}
          renderItem={({ item }) => <TripCard trip={item} />}
          showsHorizontalScrollIndicator={false}
        />
      </ScrollView>

      {/* Bottom Tab Navigation */}
      <View style={styles.bottomNav}>
        {tabs.map(tab => (
          <TouchableOpacity key={tab.name} style={styles.navItem}>
            <Icon name={tab.icon} />
            <Text>{tab.name}</Text>
          </TouchableOpacity>
        ))}
      </View>
    </View>
  );
};
```

**CSS → RN for Bottom Nav:**
```css
/* HTML/CSS */
.bottom-nav {
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
  background: rgba(255,255,255,0.7);
  backdrop-filter: blur(20px);
  display: flex;
  justify-content: space-around;
}
```

```javascript
// React Native
const styles = StyleSheet.create({
  bottomNav: {
    position: 'absolute',
    bottom: 0,
    left: 0,
    right: 0,
    flexDirection: 'row',
    justifyContent: 'space-around',
    paddingVertical: 8,
    backgroundColor: 'rgba(255,255,255,0.7)', // Blur requires BlurView wrapper
  },
});
```

---

### **5. TRIP DETAIL SCREEN**

**Complex Features:**
- Parallax hero image
- Scrollable content with sticky header transition
- Accordion/collapsible sections
- Gallery grid
- Fixed bottom CTA bar

**React Native Implementation:**
```javascript
import { Animated } from 'react-native';
import Collapsible from 'react-native-collapsible';

const TripDetailScreen = () => {
  const scrollY = new Animated.Value(0);
  const [expandedDay, setExpandedDay] = useState(null);

  // Header background opacity based on scroll
  const headerOpacity = scrollY.interpolate({
    inputRange: [0, 200],
    outputRange: [0, 1],
    extrapolate: 'clamp',
  });

  return (
    <View style={styles.container}>
      {/* Animated Header */}
      <Animated.View
        style={[
          styles.header,
          { backgroundColor: headerOpacity.interpolate({
            inputRange: [0, 1],
            outputRange: ['transparent', 'rgba(255,255,255,0.7)']
          })}
        ]}
      >
        <TouchableOpacity><Icon name="arrow-left" /></TouchableOpacity>
        <TouchableOpacity><Icon name="share" /></TouchableOpacity>
      </Animated.View>

      {/* Scrollable Content */}
      <Animated.ScrollView
        onScroll={Animated.event(
          [{ nativeEvent: { contentOffset: { y: scrollY } } }],
          { useNativeDriver: false }
        )}
        scrollEventThrottle={16}
      >
        {/* Hero Image */}
        <Image
          source={...}
          style={styles.heroImage}
        />

        {/* Content */}
        <View style={styles.content}>
          <Text style={styles.title}>Bali Beach Escape</Text>

          {/* Accordion */}
          {itinerary.map((day, index) => (
            <View key={index}>
              <TouchableOpacity
                style={styles.accordionHeader}
                onPress={() => setExpandedDay(expandedDay === index ? null : index)}
              >
                <Text>Day {index + 1}</Text>
                <Icon name={expandedDay === index ? 'chevron-up' : 'chevron-down'} />
              </TouchableOpacity>

              <Collapsible collapsed={expandedDay !== index}>
                <View style={styles.accordionContent}>
                  <Text>{day.description}</Text>
                </View>
              </Collapsible>
            </View>
          ))}
        </View>
      </Animated.ScrollView>

      {/* Fixed CTA Bar */}
      <View style={styles.ctaBar}>
        <View>
          <Text>Total Price</Text>
          <Text style={styles.amount}>₹15,000</Text>
        </View>
        <TouchableOpacity style={styles.bookBtn}>
          <Text>Book Now</Text>
        </TouchableOpacity>
      </View>
    </View>
  );
};
```

---

### **6. PAYMENT CONFIRMATION SCREEN**

**Unique Features:**
- Animated success checkmark
- Modal-style presentation
- Transaction details layout

**React Native Implementation:**
```javascript
import { useEffect } from 'react';
import Animated, {
  useSharedValue,
  useAnimatedStyle,
  withSpring
} from 'react-native-reanimated';

const PaymentConfirmationScreen = () => {
  const scale = useSharedValue(0);

  useEffect(() => {
    scale.value = withSpring(1, {
      damping: 10,
      stiffness: 100,
    });
  }, []);

  const animatedStyle = useAnimatedStyle(() => ({
    transform: [{ scale: scale.value }],
  }));

  return (
    <View style={styles.container}>
      <TouchableOpacity style={styles.closeBtn}>
        <Icon name="x" />
      </TouchableOpacity>

      <Animated.View style={[styles.successIcon, animatedStyle]}>
        <Icon name="check" size={50} color="#4caf50" />
      </Animated.View>

      <Text style={styles.title}>Payment Successful!</Text>

      <View style={styles.details}>
        <DetailRow label="Trip Name" value="Bali Beach Escape" />
        <DetailRow label="Amount Paid" value="₹15,000" />
        <DetailRow label="Transaction ID" value="TXN1234567890" />
      </View>

      <TouchableOpacity style={styles.primaryBtn}>
        <Text>View Trip Details</Text>
      </TouchableOpacity>

      <TouchableOpacity style={styles.secondaryBtn}>
        <Text>Download Receipt</Text>
      </TouchableOpacity>
    </View>
  );
};
```

---

## 🎯 **REACT NATIVE PACKAGES REQUIRED**

### **Essential Core:**
```bash
npm install react-native-vector-icons
npm install @react-native-community/blur
npm install react-native-linear-gradient
npm install react-native-reanimated
npm install react-native-gesture-handler
```

### **Navigation:**
```bash
npm install @react-navigation/native
npm install @react-navigation/stack
npm install @react-navigation/bottom-tabs
npm install react-native-screens
npm install react-native-safe-area-context
```

### **UI Components:**
```bash
npm install react-native-collapsible
npm install react-native-image-picker
npm install react-native-progress
```

### **State Management (optional):**
```bash
npm install @reduxjs/toolkit react-redux
# or
npm install zustand
```

---

## 🔄 **STATE MANAGEMENT STRATEGY**

### **Local State (useState):**
- Form inputs
- Toggle states
- Accordion expand/collapse
- Selected chips/options

### **Global State (Context/Redux):**
- User authentication
- Theme (dark/light)
- User profile data
- Trip bookings
- Payment status

### **Example: Theme Context**
```javascript
import { createContext, useState, useContext } from 'react';

const ThemeContext = createContext();

export const ThemeProvider = ({ children }) => {
  const [isDark, setIsDark] = useState(true);

  const theme = {
    isDark,
    colors: isDark
      ? {
          background: '#0d0d0d',
          text: '#ffffff',
          card: 'rgba(255,255,255,0.05)',
          border: 'rgba(255,255,255,0.1)',
        }
      : {
          background: '#fafafa',
          text: '#1a1a1a',
          card: 'rgba(255,255,255,0.5)',
          border: 'rgba(0,0,0,0.1)',
        },
  };

  return (
    <ThemeContext.Provider value={{ theme, setIsDark }}>
      {children}
    </ThemeContext.Provider>
  );
};

export const useTheme = () => useContext(ThemeContext);
```

---

## 🚀 **CONVERSION WORKFLOW**

### **Step 1: Setup Project**
```bash
npx react-native init SoleGoes
cd SoleGoes
npm install [all packages above]
```

### **Step 2: Create Folder Structure**
```
src/
├── screens/
│   ├── auth/
│   │   ├── LoginScreen.js
│   │   ├── OnboardingScreen.js
│   │   └── OTPScreen.js
│   ├── profile/
│   │   ├── ProfileSetupScreen.js
│   │   ├── PreferencesScreen.js
│   │   └── ProfileScreen.js
│   ├── home/
│   │   ├── HomeScreen.js
│   │   └── TripDetailScreen.js
│   └── payment/
│       ├── PaymentMethodScreen.js
│       └── PaymentConfirmationScreen.js
├── components/
│   ├── common/
│   │   ├── Button.js
│   │   ├── Input.js
│   │   ├── Header.js
│   │   └── Chip.js
│   └── trip/
│       ├── TripCard.js
│       └── AccordionItem.js
├── navigation/
│   ├── AuthNavigator.js
│   ├── MainNavigator.js
│   └── RootNavigator.js
├── context/
│   ├── ThemeContext.js
│   └── AuthContext.js
├── utils/
│   ├── colors.js
│   ├── fonts.js
│   └── spacing.js
└── assets/
    ├── images/
    └── fonts/
```

### **Step 3: Create Reusable Components**

**Button Component:**
```javascript
// components/common/Button.js
import { TouchableOpacity, Text, StyleSheet } from 'react-native';
import { useTheme } from '../../context/ThemeContext';

export const Button = ({ title, onPress, variant = 'primary' }) => {
  const { theme } = useTheme();

  return (
    <TouchableOpacity
      style={[
        styles.button,
        variant === 'primary' && {
          backgroundColor: theme.colors.primary,
        },
        variant === 'secondary' && {
          backgroundColor: theme.colors.card,
        },
      ]}
      onPress={onPress}
      activeOpacity={0.8}
    >
      <Text style={[styles.text, { color: theme.colors.text }]}>
        {title}
      </Text>
    </TouchableOpacity>
  );
};

const styles = StyleSheet.create({
  button: {
    paddingVertical: 14,
    paddingHorizontal: 24,
    borderRadius: 12,
    alignItems: 'center',
    justifyContent: 'center',
  },
  text: {
    fontSize: 14,
    fontWeight: '700',
    fontFamily: 'Manrope-Bold',
  },
});
```

### **Step 4: Convert Screen by Screen**

Start with simplest → complex:
1. ✅ Onboarding (static content)
2. ✅ Login (forms)
3. ✅ OTP (input logic)
4. ✅ Preferences (multi-select)
5. ✅ Profile Setup (complex forms)
6. ✅ Home (lists, scrolling)
7. ✅ Trip Detail (animations)
8. ✅ Payment screens

### **Step 5: Test on Both Platforms**
```bash
npx react-native run-ios
npx react-native run-android
```

---

## 📐 **DESIGN TOKENS**

Create centralized styling:

```javascript
// utils/theme.js
export const spacing = {
  xs: 4,
  sm: 8,
  md: 12,
  lg: 16,
  xl: 24,
  xxl: 32,
};

export const fontSize = {
  xs: 10,
  sm: 12,
  md: 14,
  lg: 16,
  xl: 20,
  xxl: 24,
  xxxl: 32,
};

export const borderRadius = {
  sm: 6,
  md: 12,
  lg: 16,
  xl: 20,
  round: 999,
};

export const darkTheme = {
  background: '#0d0d0d',
  text: '#ffffff',
  textSecondary: 'rgba(255,255,255,0.6)',
  card: 'rgba(255,255,255,0.05)',
  cardHover: 'rgba(255,255,255,0.1)',
  border: 'rgba(255,255,255,0.1)',
  primary: '#ff3b5c',
};

export const lightTheme = {
  background: '#fafafa',
  text: '#1a1a1a',
  textSecondary: 'rgba(0,0,0,0.6)',
  card: 'rgba(255,255,255,0.5)',
  cardHover: 'rgba(255,255,255,0.7)',
  border: 'rgba(0,0,0,0.1)',
  primary: '#ff3b5c',
};
```

---

## 🎨 **GLASSMORPHISM IN REACT NATIVE**

The hardest part to replicate:

```javascript
import { BlurView } from '@react-native-community/blur';

// Wrapper component
const GlassCard = ({ children, style }) => {
  const { theme } = useTheme();

  return (
    <View style={[styles.container, style]}>
      <BlurView
        style={styles.blur}
        blurType={theme.isDark ? 'dark' : 'light'}
        blurAmount={10}
      >
        <View style={[styles.content, {
          backgroundColor: theme.colors.card
        }]}>
          {children}
        </View>
      </BlurView>
    </View>
  );
};

const styles = StyleSheet.create({
  container: {
    borderRadius: 12,
    overflow: 'hidden',
    borderWidth: 1,
    borderColor: 'rgba(255,255,255,0.1)',
  },
  blur: {
    flex: 1,
  },
  content: {
    padding: 16,
  },
});
```

---

## ⚠️ **COMMON PITFALLS & SOLUTIONS**

### **1. Rem Units**
❌ **Problem:** React Native doesn't support `rem`
✅ **Solution:** Convert to pixels (14px base × rem value)

### **2. Border Radius 50%**
❌ **Problem:** RN doesn't support percentage border radius
✅ **Solution:** Calculate `borderRadius: width / 2`

### **3. Gap Property**
❌ **Problem:** `gap` not supported in RN
✅ **Solution:** Use margin on children or wrapper View

### **4. Backdrop Filter**
❌ **Problem:** CSS backdrop-filter doesn't exist
✅ **Solution:** Use `@react-native-community/blur`

### **5. Position Fixed**
❌ **Problem:** `position: fixed` doesn't exist
✅ **Solution:** Use `position: 'absolute'` with `bottom: 0`

### **6. Hover States**
❌ **Problem:** No `:hover` in React Native
✅ **Solution:** Use `onPressIn`/`onPressOut` or `TouchableHighlight`

### **7. Box Shadow**
❌ **Problem:** Single property doesn't work
✅ **Solution:**
```javascript
shadowColor: '#000',
shadowOffset: { width: 0, height: 2 },
shadowOpacity: 0.1,
shadowRadius: 8,
elevation: 5, // Android
```

### **8. Font Weights**
❌ **Problem:** `fontWeight: 700` might not work
✅ **Solution:** Use string `fontWeight: '700'` or import font files

---

## 🎯 **NEXT STEPS FOR AGENT DEVELOPMENT**

1. **Parse HTML Structure** → Extract component hierarchy
2. **Extract CSS Classes** → Map to StyleSheet objects
3. **Identify Interactions** → Convert to React Native events
4. **Generate Component Files** → Create .js files
5. **Setup Navigation** → Link screens together
6. **Add State Management** → Context/Redux setup
7. **Test & Refine** → Run on iOS/Android

---

**Document Created:** 2025-01-09
**Purpose:** Guide for HTML-to-React-Native conversion agent
**Status:** Ready for agent implementation
