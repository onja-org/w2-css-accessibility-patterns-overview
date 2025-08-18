# Accessibility Patterns Lab  

## 📖 Description  
In this lab, you will explore **basic accessibility patterns** in web development.  
You are given an **HTML + CSS file** that implements:  
- A simple **navigation bar**  
- A **button with focus styles**  

Your task is to:  
1. Test accessibility using only the **keyboard**. 
2. Inspect the **HTML code** to see how accessibility is implemented  

This exercise will help you understand **why accessibility matters** and how to apply it in your own projects.  

---

## 🎯 Learning Goals  
By the end of this exercise, you should be able to:  
- Navigate a webpage using **keyboard only**  
- Recognize the importance of **focus indicators**  
- Test how a screen reader announces links, buttons, and navigation  
- Identify **semantic HTML** and **ARIA attributes** that improve accessibility  

---

## 🛠️ Tasks  

### 1. Test with the Keyboard  
- Open the HTML file in your browser.  
- Press **Tab** → focus should move through navigation links and the button.  
- Press **Shift + Tab** → focus should move backwards.  
- Check if the **focus is visible** (highlight/outline).  
- When focus is on a button or link, press **Enter** or **Space** → it should activate.  


---

### 2. Inspect the HTML  
Open the `index.html` file and look for these accessibility patterns:  

- **Navigation bar**  
  - Uses `<nav>` with `aria-label="Main navigation"`  
  - Links are real `<a>` elements inside a `<ul>` list  

- **Button**  
  - Implemented with a real `<button>` element (not a `<div>`)  
  - Has a visible focus style  
  - May include `aria-label` for extra screen reader context  

- **General patterns**  
  - Semantic elements (`<main>`, `<header>`, `<footer>`)  
  - Meaningful structure instead of only `<div>` and `<span>`  

---

## ✅ Expected Results  
- The **Tab key** moves focus in a logical order:  
  `Home → About → Services → Contact → Button`  
- The **focus outline** is always visible.  
- The **button** is announced as a button by a screen reader.  
- The **navigation** is announced as "Navigation".  
- The HTML uses **semantic tags** and/or **ARIA attributes** correctly.  

---
 
#### Watch this video to understand more 
- Click the link bellow and watch the video : 
[https: //www.youtube.com/watch?v=dEbl5jvLKGQ](https://www.youtube.com/watch?v=dEbl5jvLKGQ)