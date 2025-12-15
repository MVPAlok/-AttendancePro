# 🚀 AttendancePro Setup Flow - User Guide

## Quick Start

### Accessing the Setup Flow

The multi-step setup flow can be triggered from two locations on the home page:

1. **Hero Section**: Large green "Start Tracking Attendance" button
2. **Final CTA Section**: "Get Started Now" button at the bottom

Both buttons will smoothly fade to the setup page.

---

## Step-by-Step Instructions

### 📋 STEP 1: Organization Setup (2-3 minutes)

**What you'll see:**

- A form with 5 fields to configure
- Progress bar showing "Step 1 of 4"
- Step indicator tabs at the top

**Fields to fill:**

1. **Organization Name** ⭐ Required

   - Example: "TechFlow Inc." or "St. Xavier's School"
   - Enter your company/institution name

2. **Organization Type** ⭐ Required

   - Choose one from dropdown:
     - College / University
     - School
     - Company
     - Startup
     - Institute

3. **Time Zone**

   - Pre-selected: UTC (GMT+0)
   - Choose your timezone from 7 options
   - Options: UTC, EST, CST, MST, PST, IST, GST

4. **Working Days**

   - Green buttons = Selected days
   - Gray buttons = Unselected days
   - Default: Mon-Fri (already selected)
   - Click to toggle any day on/off

5. **Working Hours**
   - Start Time: Default 09:00 (9 AM)
   - End Time: Default 18:00 (6 PM)
   - Click to change using time picker

**What happens next:**

- Click blue "Continue to User Setup →" button
- Form validates (name and type are required)
- All data is saved
- Smooth transition to Step 2

**Buttons:**

- **Cancel**: Return to home page
- **Continue**: Proceed to next step (validates form)

---

### 👥 STEP 2: User/Member Setup (5-10 minutes)

**What you'll see:**

- Two tabs: "Add Manually" and "Upload CSV"
- User entry cards
- Progress bar showing "Step 2 of 4"

#### Option A: Add Users Manually (Tab 1)

**Default State:**

- One empty user card appears automatically
- "Add Another User" button below

**For each user card, fill:**

1. **Full Name** ⭐ Required

   - Example: "John Smith"

2. **Role** ⭐ Required

   - Choose: Admin / Manager / Employee / Student
   - Different permissions based on role

3. **ID / Roll No** (Optional)

   - Example: "EMP-001" or "2024-A-123"

4. **Department / Class** (Optional)
   - Example: "Engineering" or "Class 12-A"

**Quick Actions:**

- Click ✕ button on any card to remove that user
- Click "Add Another User" to add more users
- Fields validate individually

**Must have:** At least 1 user to proceed

#### Option B: Upload CSV (Tab 2)

**How to use:**

1. Click the upload area or drag & drop a CSV file
2. File should have 4 columns:

   - Full Name
   - Role (Admin/Manager/Employee/Student)
   - ID/Roll No
   - Department/Class

3. **Example CSV format:**

   ```
   Full Name,Role,ID/Roll No,Department
   John Smith,Manager,EMP-001,Engineering
   Sarah Johnson,Employee,EMP-002,Engineering
   Mike Chen,Employee,EMP-003,Sales
   ```

4. Preview shows first 5 rows
5. Click "Choose Attendance Method →" to continue

**What happens next:**

- At least 1 user required
- If none added: Error toast appears
- If valid: Data saved and proceed to Step 3

**Buttons:**

- **Back**: Return to Step 1
- **Choose Attendance Method →**: Proceed to Step 3 (validates users)

---

### 📍 STEP 3: Attendance Method Selection (3-5 minutes)

**What you'll see:**

- 4 method cards in 2x2 grid
- Description and pros for each method
- Additional settings below
- Progress bar showing "Step 3 of 4"

**Choose ONE attendance method:**

#### 1️⃣ One-Click Web Check-in

**Best for:** Simple, fast check-ins

- **How it works:** Employees click a button to mark attendance
- **Pros:** Quick setup, works on all devices, no hardware
- **Best for:** Remote teams, flexible work
- **Badge:** Most Popular ⭐

#### 2️⃣ QR Code Attendance

**Best for:** Secure, tamper-proof tracking

- **How it works:** Employees scan dynamic QR codes
- **Pros:** Prevents proxy attendance, quick scanning, tamper-proof
- **Best for:** Offices with physical presence requirements
- **Badge:** Highly Secure 🔒

#### 3️⃣ Location-Based (Geo-fencing)

**Best for:** Automatic, location-aware tracking

- **How it works:** Automatic check-in when arriving at office location
- **Pros:** Fully automatic, real location tracking, no manual effort
- **Best for:** Multiple office locations, on-site work
- **Badge:** Requires GPS 📍

#### 4️⃣ Time-Based Auto Lock

**Best for:** Scheduled, automated tracking

- **How it works:** Automatically mark attendance at specific times
- **Pros:** Fully automated, prevents late marking, time-locked accuracy
- **Best for:** Shift-based work, strict timing requirements
- **Badge:** Scheduled ⏰

**Additional Settings (Toggles):**

1. **Allow Late Marking** ✓ (Checked by default)

   - If ON: Employees can mark up to 30 mins after start time
   - If OFF: Must mark on time

2. **Auto Mark Absent** ✓ (Checked by default)
   - If ON: Automatically mark absent after work end time
   - If OFF: Manual absent marking only

**How to select:**

- Click any card to select it
- Selected card shows green border and glow effect
- Changes also saved in toggles

**What happens next:**

- Selection is required to proceed
- Click "Launch Attendance Dashboard →"
- Advances to final step (dashboard preview)

**Buttons:**

- **Back**: Return to Step 2
- **Launch Attendance Dashboard →**: Proceed to Step 4

---

### 📊 STEP 4: Dashboard Preview (1-2 minutes)

**What you'll see:**

- Success notification: "Setup Complete!"
- Preview of the actual dashboard you'll use
- Realistic dummy data
- Progress bar showing "Step 4 of 4" (complete)

**Dashboard Components:**

**1. Success Banner**

- Green checkmark
- "Setup Complete!" message
- "Your attendance system is ready to go"

**2. Dashboard Preview (Browser Frame)**

- Fake browser chrome (red, yellow, green dots)
- Responsive layout

**Left Sidebar (Desktop only):**

- Dashboard (currently selected, highlighted)
- Employees
- Schedule
- Reports

**Main Content Area:**

**Stats Cards (Top Row):**

- **Total Present**: 842 employees
  - Change: +12% (green, trending up)
- **Late Arrivals**: 24 employees
  - Change: -3% (orange, improvement)
- **On Leave**: 18 employees
  - Status: Normal (gray)

**Weekly Attendance Trends Chart:**

- Bar chart showing Mon-Fri attendance
- Y-axis: Attendance percentage
- Interactive bars (hover for details)
- Grid lines for readability
- "Export Data" button (for reports)

**What this shows:**

- This is what your dashboard will look like after setup
- Real data will replace dummy data
- You can track attendance in real-time

**What happens next:**

- Click "Start Using Dashboard →"
- Setup completes with success notification
- Toast message: "Attendance system successfully activated!"
- Redirects to home page after 1.5 seconds

**Buttons:**

- **Back**: Return to Step 3 to change method
- **Start Using Dashboard →**: Complete setup (success!)

---

## 🎯 Key Tips & Tricks

### Data Persistence

- Your progress is saved after each step
- If you navigate away, data is stored locally
- Returning to setup will restore your progress

### Form Validation

- Required fields must be filled (marked with red \*)
- Error messages appear below fields
- Fix errors to proceed to next step

### Animations

- Pages fade smoothly (not jarring)
- Progress bar animates as you advance
- Buttons have hover effects
- Toast notifications slide up gently

### Mobile Friendly

- Works on phones, tablets, laptops
- Touch-friendly buttons (44px minimum)
- Responsive layouts adjust to screen size

### Keyboard Shortcuts (if needed)

- Tab: Navigate between fields
- Enter: Submit form
- Esc: Cancel setup (back to home)

---

## ❓ Frequently Asked Questions

**Q: Can I change my answers after moving to the next step?**
A: Yes! Use the "Back" button to return to any previous step.

**Q: What if I close the browser during setup?**
A: Your data is saved to localStorage. Come back later and resume from where you left off.

**Q: Is all this information required?**
A: Organization Name, Organization Type, Role, and Attendance Method are required. Others are optional but recommended.

**Q: Can I upload a CSV file with different column names?**
A: Expected columns are: Full Name, Role, ID/Roll No, Department. Keep these column names for proper parsing.

**Q: What happens after I complete setup?**
A: You'll see a success message and be taken back to the home page. Your attendance system is then ready to use!

**Q: Can I edit organization settings later?**
A: Yes! After setup, admin users can change settings in the Settings section of the dashboard.

---

## 🎨 Visual Guide

```
HOME PAGE
    │
    ├─ Click "Start Tracking Attendance"
    │
    ▼
STEP 1: Organization Setup
    │
    ├─ Fill: Name, Type, Timezone, Working Days, Hours
    ├─ Click "Continue to User Setup →"
    │
    ▼
STEP 2: User Setup
    │
    ├─ Add users manually OR upload CSV
    ├─ At least 1 user required
    ├─ Click "Choose Attendance Method →"
    │
    ▼
STEP 3: Attendance Method
    │
    ├─ Select one of 4 methods
    ├─ Configure additional settings
    ├─ Click "Launch Attendance Dashboard →"
    │
    ▼
STEP 4: Dashboard Preview
    │
    ├─ Review your new dashboard
    ├─ See realistic dummy data
    ├─ Click "Start Using Dashboard →"
    │
    ▼
SUCCESS! ✨
    │
    └─ Redirects to home with success notification
```

---

## 📱 Browser Compatibility

✅ **Fully Supported:**

- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

✅ **Mobile Browsers:**

- iOS Safari
- Chrome Mobile
- Firefox Mobile
- Samsung Internet

⚠️ **Not Supported:**

- Internet Explorer (ancient)

---

## 🆘 Troubleshooting

**Issue: Button not responding**

- Solution: Refresh page, check browser console

**Issue: Form won't submit**

- Solution: Check for error messages, fill all required fields (marked with \*)

**Issue: Data not saving**

- Solution: Check browser localStorage is enabled (Settings → Privacy)

**Issue: CSV preview not showing**

- Solution: Ensure CSV has correct column names, try with smaller file

---

**Happy Setting Up! 🎉**

For support, contact: support@attendancepro.com
