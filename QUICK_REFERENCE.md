# 🚀 Quick Reference Guide

## File Overview

| File                      | Purpose                           | Size          | Type        |
| ------------------------- | --------------------------------- | ------------- | ----------- |
| index.html                | Complete SaaS app with setup flow | 1498 lines    | HTML+CSS+JS |
| IMPLEMENTATION_SUMMARY.md | Feature documentation             | Comprehensive | Markdown    |
| USER_GUIDE.md             | End-user instructions             | Detailed      | Markdown    |
| TECHNICAL_DOCS.md         | Developer documentation           | Extensive     | Markdown    |
| QUICK_REFERENCE.md        | This file                         | Quick lookups | Markdown    |

---

## Instant Code Reference

### Import/Include

```html
<!-- No external imports needed -->
<!-- Already included in <head>: -->
<!-- - Tailwind CSS -->
<!-- - Material Icons -->
<!-- - Google Fonts (Spline Sans) -->
```

### Key IDs to Know

```javascript
'app-container'       // Main container
'home-page'          // Landing page
'setup-page'         // Setup flow page
'step-1', 'step-2', 'step-3', 'step-4'  // Individual steps
'org-form'           // Step 1 form
'org-name'           // Org name input
'org-type'           // Org type dropdown
'timezone'           // Timezone selector
'users-container'    // User cards container
'manual-tab'         // Manual user tab
'csv-tab'            // CSV upload tab
'csv-input'          // CSV file input
'csv-preview'        // CSV preview area
'toast-container'    // Toast notifications
'progress-1', ..., 'progress-4'  // Progress bars
'current-step'       // Step counter display
```

### Key Classes to Know

```javascript
"page-content"; // Page wrapper
"setup-step"; // Individual step wrapper
"slide-in-right"; // Slide animation
"user-card"; // User entry card
"chip-btn"; // Working days button
"selectable-card"; // Method selection card
"selected"; // Active method card
"active"; // Active chip/step
"hidden"; // Hidden element
"toast"; // Toast notification
"glass-card"; // Glass-morphism card
"glass-panel"; // Glass-morphism panel
```

---

## Function Quick Reference

### Navigation

```javascript
navigateTo(page); // Navigate to 'home' or 'setup'
navigateHome(); // Go back to home + reset
resetSetupState(); // Clear all form data
goToStep(step); // Jump to step 1-4
goToPreviousStep(); // Go back one step
```

### Validation

```javascript
validateAndNextStep(step); // Validate & proceed
validateStep1(); // Org validation
validateStep2(); // User validation
validateStep3(); // Method validation
```

### User Management

```javascript
addUserField(); // Create new user card
switchUserTab(tab); // Switch to 'manual' or 'csv'
handleCSVUpload(event); // Process CSV file
```

### Method Selection

```javascript
selectMethod(method, el); // Select attendance method
```

### UI/UX

```javascript
updateProgress(step); // Update progress bar
showError(id, msg); // Display field error
hideError(id); // Hide field error
showToast(msg, type); // Show notification
```

### State Management

```javascript
saveCurrentStep(); // Save to localStorage
completeSetup(); // Finish flow + success toast
```

---

## Component Structure

### Step Template

```html
<div id="step-X" class="setup-step hidden">
  <div class="max-w-2xl mx-auto bg-surface-dark border ...">
    <h2>Title</h2>
    <p>Description</p>
    <!-- Form content -->
    <div class="flex gap-4 pt-4">
      <button onclick="goToPreviousStep()">Back</button>
      <button onclick="validateAndNextStep(X)">Next</button>
    </div>
  </div>
</div>
```

### User Card Template

```html
<div class="user-card bg-surface-highlight/50 ...">
  <input type="text" data-field="name" />
  <select data-field="role">
    <option>Admin</option>
    <option>Manager</option>
    <option>Employee</option>
    <option>Student</option>
  </select>
  <input type="text" data-field="id" />
  <input type="text" data-field="department" />
</div>
```

### Method Card Template

```html
<div
  class="selectable-card border-white/10 rounded-2xl ..."
  onclick="selectMethod('method-id', this)"
>
  <div
    class="w-12 h-12 bg-primary/10 rounded-lg flex items-center justify-center"
  >
    <span class="material-symbols-outlined">icon_name</span>
  </div>
  <h3>Method Name</h3>
  <p>Description</p>
  <div class="bg-white/5 rounded-lg p-3">
    <p class="text-primary text-xs font-bold">✓ Pros:</p>
    <ul class="text-gray-400 text-xs">
      <li>• Benefit 1</li>
      <li>• Benefit 2</li>
    </ul>
  </div>
  <input type="radio" name="method" value="method-id" class="hidden" />
</div>
```

---

## CSS Customization

### Colors

```css
/* Primary theme color */
--primary: #36e27b;

/* Dark mode colors */
--background-dark: #122118;
--surface-dark: #1a2e24;
--surface-highlight: #23392e;

/* Change in tailwind.config */
colors: {
  "primary":"#36e27b","secondary": "#254632", ...;
}
```

### Animations (in <style> tag)

```css
@keyframes fadeOut/fadeIn      /* Page transitions */
@keyframes slideInRight        /* Step entry */
@keyframes slideProgress       /* Progress bar */
@keyframes slideUp; /* Toast notification */
```

### Border Radius

```css
rounded     /* 1rem (default) */
rounded-lg  /* 1.5rem */
rounded-xl  /* 2rem */
rounded-2xl /* 3rem */
rounded-full /* 9999px (pills) */
```

---

## State Object Reference

```javascript
setupState = {
  currentStep: 1,
  formData: {
    organization: {
      name: "TechFlow Inc.",
      type: "company",
      timezone: "EST",
      workingDays: ["mon", "tue", "wed", "thu", "fri"],
      workStart: "09:00",
      workEnd: "18:00",
    },
    users: [
      {
        name: "John Smith",
        role: "Admin",
        id: "EMP-001",
        department: "Engineering",
      },
    ],
    method: "web-checkin",
    settings: {
      lateMarking: true,
      autoAbsent: true,
    },
  },
};
```

---

## Common Tasks

### Add a new field to Step 1

1. Add input/select in Step 1 HTML
2. Give it unique ID (e.g., `#new-field`)
3. In `validateStep1()`, save value:
   ```javascript
   setupState.formData.organization.newField =
     document.getElementById("new-field").value;
   ```

### Change animation duration

```css
/* In <style> tag */
.slide-in-right {
  animation: slideInRight 0.4s ease-out forwards; /* Change 0.4s */
}
```

### Modify color scheme

```javascript
/* In tailwind config */
colors: {
  "primary": "#YOUR_COLOR",  // Change hex
  "secondary": "#YOUR_COLOR",
  ...
}
```

### Add validation to a field

```javascript
// In validateStep1() or appropriate function
const fieldValue = document.getElementById("field-id").value;
if (!fieldValue || fieldValue.trim() === "") {
  showError("field-error-id", "Error message here");
  return false;
}
hideError("field-error-id");
```

### Change API endpoint (when adding backend)

```javascript
// Replace in validateAndNextStep()
const response = await fetch("YOUR_API_ENDPOINT", {
  method: "POST",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify(setupState.formData),
});
```

---

## Testing Common Scenarios

### Test 1: Complete full setup

1. Open browser, click "Start Tracking Attendance"
2. Fill all required fields in Step 1
3. Add 2-3 users in Step 2
4. Select any method in Step 3
5. Verify Step 4 shows success

### Test 2: Field validation

1. Go to Step 1
2. Leave "Organization Name" empty
3. Click "Continue" → should see error
4. Fill field → error disappears
5. Successfully proceed

### Test 3: localStorage persistence

1. Complete Step 1
2. Close/refresh browser
3. Click "Start Tracking Attendance" again
4. Should resume at Step 2 (data saved)

### Test 4: CSV upload

1. Go to Step 2
2. Click CSV tab
3. Upload valid CSV with correct columns
4. Verify preview shows rows
5. Proceed to next step

### Test 5: Responsive design

1. Open on desktop (1920px+)
2. Shrink window to tablet (768px)
3. Shrink to mobile (375px)
4. Verify layout adapts correctly
5. Touch targets remain adequate

---

## API Integration Checklist

When connecting to backend APIs:

- [ ] Add authentication headers
- [ ] Replace localStorage with API calls
- [ ] Add loading states to buttons
- [ ] Add error handling for network failures
- [ ] Add retry logic for failed requests
- [ ] Update toast messages for API responses
- [ ] Handle rate limiting
- [ ] Add request timeouts
- [ ] Log errors for debugging
- [ ] Update state based on API response

### Example API integration template:

```javascript
async function validateAndNextStep(step) {
  if (!validate()) return;

  // Show loading state
  button.disabled = true;
  button.textContent = "Loading...";

  try {
    // Make API call
    const response = await fetch(`/api/step-${step}`, {
      method: "POST",
      headers: { "Content-Type": "application/json" },
      body: JSON.stringify(setupState.formData),
    });

    if (!response.ok) throw new Error("API error");

    const data = await response.json();

    // Update state and proceed
    setupState.formData.id = data.id;
    goToStep(step + 1);
  } catch (error) {
    showToast(`Error: ${error.message}`, "error");
  } finally {
    // Reset loading state
    button.disabled = false;
    button.textContent = "Continue";
  }
}
```

---

## Browser DevTools Tips

### Check localStorage

```javascript
// In Console
localStorage.getItem("setupState");
JSON.parse(localStorage.getItem("setupState"));
localStorage.clear();
```

### Debug setupState

```javascript
// In Console
setupState; // View entire state
setupState.currentStep; // Check current step
setupState.formData; // View all form data
```

### Check animations

```javascript
// Inspect element and look for:
// - animation property in Computed tab
// - transition property for smooth effects
// - transform property for positioning
```

### Profile performance

```javascript
// In DevTools > Performance tab
// Record interaction, check for:
// - Long tasks (>50ms)
// - Layout thrashing
// - Excessive repaints
```

---

## Keyboard Shortcuts (Browser)

| Shortcut     | Action                           |
| ------------ | -------------------------------- |
| F12          | Open DevTools                    |
| Ctrl+Shift+J | Open Console                     |
| Ctrl+Shift+I | Open Inspector                   |
| Tab          | Navigate form fields             |
| Enter        | Submit form                      |
| Esc          | Can close modal (if implemented) |

---

## File Size Reference

```
index.html:                 ~85 KB (unminified)
CSS (inline):              ~15 KB
JavaScript (inline):       ~45 KB
Documentation files:       ~100 KB total

Total single file:         ~85 KB (production ready)
```

---

## Support & Debugging

### Check Console for Errors

- Open DevTools (F12)
- Go to Console tab
- Look for red error messages
- Check for undefined variables

### Common Errors & Fixes

**"setupState is not defined"**

- Check if global setupState object is declared
- Verify script tag is not missing

**"Cannot read property 'classList' of null"**

- Element ID doesn't exist in HTML
- Check HTML for typos in IDs

**"File upload not working"**

- Check if input#csv-input exists
- Verify accept=".csv" attribute

**"Progress bar not animating"**

- Check if animation classes applied
- Verify CSS @keyframes defined
- Check browser support (all modern browsers)

---

## Resources

- **Tailwind CSS**: https://tailwindcss.com/docs
- **Material Icons**: https://fonts.google.com/icons
- **MDN Web Docs**: https://developer.mozilla.org
- **Can I Use**: https://caniuse.com
- **JSON Validator**: https://jsonlint.com

---

## Quick Commands

```bash
# Start local server
python -m http.server 8000
# Access at: http://localhost:8000

# Pretty print HTML (if you have prettier)
prettier --write index.html

# Check file size
ls -lh index.html

# Open in browser (macOS)
open index.html

# Open in browser (Windows)
start index.html

# Open in browser (Linux)
xdg-open index.html
```

---

**Last Updated:** December 15, 2025
**Version:** 1.0
**Status:** ✅ Production Ready
