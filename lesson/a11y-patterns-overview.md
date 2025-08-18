# Web Accessibility Patterns: Making the Web Work for Everyone

**Duration:** 15 minutes  
**Level:** Beginner to Intermediate

---

## 🎯 What You'll Learn

By the end of this lesson, you'll understand the essential accessibility patterns that make websites usable for everyone, including the 1 billion+ people worldwide with disabilities.

---

## 1. Why Accessibility Matters

Web accessibility isn't just the right thing to do—it's smart business:
- **Legal protection**: Avoid costly lawsuits (companies pay millions in accessibility settlements)
- **Broader audience**: 15% of the global population has some form of disability
- **Better SEO**: Screen reader-friendly code is also search engine-friendly
- **Improved UX**: Accessibility features help everyone (think captions on videos in noisy environments)

---

## 2. Foundation: Semantic HTML

**The Golden Rule**: Use HTML elements for what they were designed to do.

### ✅ Good vs ❌ Bad Examples

```html
<!-- ✅ GOOD: Semantic and accessible -->
<button onclick="submitForm()">Submit Form</button>
<a href="/contact">Contact Us</a>

<!-- ❌ BAD: Looks right but breaks accessibility -->
<div onclick="submitForm()" style="cursor: pointer;">Submit Form</div>
<span onclick="goToContact()">Contact Us</span>
```

**Why this matters**: Screen readers announce "button" or "link" to help users understand what each element does.

### Essential Structural Elements
```html
<header>Site navigation and branding</header>
<main>Primary content area</main>
<aside>Sidebar content</aside>
<footer>Site info and links</footer>
```

---

## 3. Keyboard Navigation: The Invisible Users

**Reality check**: Many users navigate entirely with keyboards—not just people with motor disabilities, but also power users who find keyboards faster.

### Core Requirements
- **Tab order**: Should follow logical reading flow
- **Focus indicators**: Make it obvious which element is active
- **No keyboard traps**: Users must be able to navigate away from any element

### Focus Styling Example
```css
button:focus {
  outline: 3px solid #4A90F2;
  outline-offset: 2px;
  /* Never use outline: none without a replacement! */
}
```

### Modal Accessibility Pattern
When a modal opens:
1. Focus moves to the modal
2. Tab navigation stays within the modal
3. Esc key closes the modal
4. Focus returns to the trigger element

---

## 4. ARIA: When HTML Isn't Enough

**Think of ARIA as subtitles for screen readers**—it provides context that visual users get automatically.

### Most Important ARIA Patterns

| Attribute | Use Case | Example |
|-----------|----------|---------|
| `aria-label` | Describe purpose when text isn't clear | `<button aria-label="Close dialog">×</button>` |
| `aria-live` | Announce dynamic changes | `<div aria-live="polite">Status updates</div>` |
| `role` | Define element purpose | `<div role="dialog">Modal content</div>` |
| `aria-expanded` | Show/hide state | `<button aria-expanded="false">Menu</button>` |

### ⚠️ ARIA Rules
1. **Don't change semantics**: `<h1 role="button">` is confusing
2. **All interactive ARIA elements need keyboard support**
3. **Test with actual screen readers**

---

## 5. Forms That Actually Work

### The Label Connection
```html
<!-- Method 1: Explicit association -->
<label for="user-email">Email Address</label>
<input type="email" id="user-email" name="email" required>

<!-- Method 2: Implicit association -->
<label>
  Email Address
  <input type="email" name="email" required>
</label>
```

### Error Handling Best Practices
```html
<label for="password">Password</label>
<input type="password" id="password" aria-describedby="pwd-error" required>
<div id="pwd-error" role="alert">
  Password must be at least 8 characters
</div>
```

---

## 6. Visual Design & Media

### Color & Contrast
- **Minimum contrast ratio**: 4.5:1 for normal text, 3:1 for large text
- **Never rely on color alone**: Use icons, text, or patterns too
- **Test tool**: WebAIM Contrast Checker

### Images & Media
```html
<!-- Informative images -->
<img src="chart.png" alt="Sales increased 40% from January to March">

<!-- Decorative images -->
<img src="decoration.png" alt="" role="presentation">

<!-- Videos -->
<video controls>
  <source src="video.mp4" type="video/mp4">
  <track kind="captions" src="captions.vtt" srclang="en" label="English">
</video>
```

---

## 7. Quick Testing Checklist

### Manual Tests (5 minutes)
- [ ] Navigate entire site using only Tab, Shift+Tab, Enter, and Space
- [ ] Check all focus indicators are visible
- [ ] Verify all images have appropriate alt text
- [ ] Test forms without looking at the screen

### Automated Tools
- **Browser DevTools**: Built-in accessibility panel
- **Lighthouse**: Free accessibility audit
- **axe DevTools**: Chrome extension for detailed testing

---

## 8. Real-World Impact

**Before you implement these patterns, ask yourself:**
- Can someone who's blind complete the main task on this page?
- Can someone who can't use a mouse still navigate effectively?
- If someone has low vision and zooms to 200%, does the layout still work?

These aren't edge cases—they're real users who want to engage with your content.

---

## 🚀 Next Steps

1. **Audit one page** of your current project using these patterns
2. **Install axe DevTools** and run it on your site
3. **Try navigating your site** with only your keyboard
4. **Learn one screen reader** (NVDA is free for Windows, VoiceOver built into Mac)

Remember: Accessibility is not a checklist—it's an ongoing practice of inclusive design.