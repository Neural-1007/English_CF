# 🎭 Quick Start Guide - English: A Play in Five Acts

## **What's New**

✨ **11 Interactive Games Added**  
🖼️ **College Images Integrated**  
🔧 **Fixed Colleges Scrolling**  
📱 **Mobile Optimized Game Interface**

---

## **Files Overview**

| File | Changes |
|------|---------|
| `app.js` | +600 lines of game logic, fixed scroll mechanics |
| `games.html` | **NEW** - All 11 games interface |
| `colleges.html` | Fixed height (520vh), added college images |
| `index.html` | Added Games link in menu |
| `style.css` | +400 lines of game styling |
| `history.html`, `careers.html`, `feedback.html` | Updated navigation (auto-generated) |
| `README.md` | **NEW** - Complete documentation |
| `QUICK_START.md` | This file |

---

## **🚀 Deploy in 3 Steps**

### **Step 1: Copy All Files**
```bash
# Move all files to your web server
cp *.html *.js *.css *.md /var/www/your-site/

# Or upload via FTP/SFTP
```

### **Step 2: Test Locally (Optional)**
```bash
# Start a local server
python -m http.server 8000

# Open: http://localhost:8000
```

### **Step 3: Configure (2 minutes)**

**Edit `app.js` Line 1:**
```javascript
const FEEDBACK = {
  formspree: 'https://formspree.io/f/YOUR_ID',  // Get from formspree.io
  email: 'your@email.com'
};
```

**Update Credits:** Replace "to be added" with creator names in:
- `index.html` (2 places)
- `app.js` (footer)

---

## **✅ Quick Verification Checklist**

After deployment, verify:

- [ ] Index page loads with all 5 menu links
- [ ] Games page shows all 11 game cards
- [ ] College images display (5 colleges visible on scroll)
- [ ] Games open in modals when clicked
- [ ] Feedback form submits without errors
- [ ] 3D background animations work
- [ ] Mobile view is responsive

---

## **📱 Colleges Page - What Was Fixed**

### **Before:**
- Scroll height: `450vh` (too short, couldn't scroll to end)
- No images on college cards

### **After:**
```html
<!-- Height increased to allow full scrolling -->
<section class="pin reel" style="height:520vh">

<!-- College images added -->
<div class="college-img" style="background-image:url('...')"></div>

<!-- More college details -->
<ul>
  <li>🎓 BA/MA programs</li>
  <li>📚 Specializations</li>
  <li>👥 Alumni info</li>
</ul>
```

**Test it:** Scroll through colleges → images should appear & end of content should be reachable

---

## **🎮 The 11 Games at a Glance**

| # | Game | Duration | Type |
|---|------|----------|------|
| 1 | Etymology Tracer | 2 min | Educational |
| 2 | Word Chain | 5 min | Skill-based |
| 3 | Quote Attribution | 5 min | Knowledge |
| 4 | Career Match Quiz | 3 min | Personality |
| 5 | College Route Planner | 3 min | Decision tool |
| 6 | Story Adventure | 8 min | Narrative |
| 7 | Debate Spinner | 3 min | Discussion |
| 8 | Typing Speed | 5 min | Challenge |
| 9 | Accent Guesser | 2 min | Audio |
| 10 | Daily Word | 1 min | Daily habit |
| 11 | Spelling Bee | 3 min | Challenge |

---

## **🎯 How to Customize Games**

All game data is in `app.js`. Examples:

### **Add a new word to Etymology:**
```javascript
// Line ~40
const etymologyDB = {
  journalist: { /* ... */ },
  educator: {  // NEW
    path: [
      {era: 'Late Modern', origin: '...', meaning: '...'},
      // ...
    ]
  }
};
```

Then in `games.html`, add button:
```html
<button class="game-btn" onclick="showEtymology('educator')">educator</button>
```

### **Add a new quote:**
```javascript
// Line ~80
const quoteData = [
  { /* existing quotes */ },
  {quote: '"New quote text"', author: 'Author', era: 'Early Modern', correct: 2}
];
```

### **Add career to quiz:**
```javascript
// Line ~120
const careerQuiz = {
  careers: [
    { /* existing */ },
    {name: 'New Career', desc: 'Description', match: [1,0,0,1]}
  ]
};
```

---

## **🖼️ College Images - Using Your Own**

Default: Using Unsplash free images

To use local images:

1. **Upload images to your server:**
   ```
   /images/st-stephens.jpg
   /images/st-xaviers.jpg
   ... etc
   ```

2. **Update `colleges.html`:**
   ```html
   <!-- From: -->
   <div class="college-img" style="background-image:url('https://images.unsplash.com/...')"></div>
   
   <!-- To: -->
   <div class="college-img" style="background-image:url('/images/st-stephens.jpg')"></div>
   ```

**Image requirements:**
- Size: 400×250px minimum
- Format: JPG, PNG, WebP
- Weight: <200KB each

---

## **🎨 Customize Colors**

Edit `style.css` Line 1:
```css
:root {
  --ink: #140c08;        /* Background: Dark brown */
  --parch: #f1e3c8;      /* Text: Cream */
  --gold: #e8c872;       /* Accents: Gold */
  --wine: #7a1f2b;       /* Buttons: Wine red */
}
```

Example: Change accent color to blue:
```css
--gold: #3498db;
```

---

## **🔗 Deploy Checklist**

### **Before Going Live:**

- [ ] Update Formspree ID (or use email fallback)
- [ ] Add creator names (replace "to be added")
- [ ] Test all games in browser
- [ ] Check college images load
- [ ] Test feedback form submission
- [ ] Verify all links work (navigate between pages)
- [ ] Test on mobile device
- [ ] Check console for errors (F12)

### **Before Telling Students:**

- [ ] Set up analytics (optional, see README)
- [ ] Test on school network (if applicable)
- [ ] Brief students on game selection
- [ ] Have IT support ready if needed

---

## **📊 Common Configuration Scenarios**

### **Scenario 1: Using School Email**
```javascript
const FEEDBACK = {
  formspree: '',
  email: 'english-dept@school.edu'
};
```
✅ Students click "Seal" → mail app opens with pre-filled message

### **Scenario 2: Direct Backend (Recommended)**
```javascript
const FEEDBACK = {
  formspree: 'https://formspree.io/f/xyzabc123',
  email: 'fallback@school.edu'
};
```
✅ Responses auto-send to email + appear in Formspree dashboard

### **Scenario 3: Google Forms Alternative**
Instead of Formspree, embed Google Form:
1. Create Google Form
2. Get embed code
3. Replace `<form id=fm>` in `feedback.html` with embed

---

## **🐛 Troubleshooting**

### **Games don't load**
```
Solution: Check browser console (F12)
- Look for red errors
- Ensure app.js is loaded in Network tab
- Try hard refresh: Ctrl+Shift+R
```

### **College images not showing**
```
Solution:
1. Check image URLs are correct
2. Test URL directly in new tab
3. Check for CORS errors in console
4. Verify image path is absolute or relative correctly
```

### **Feedback form errors**
```
Solution:
1. Check Formspree URL (copy-paste carefully)
2. Try incognito mode (cache issue)
3. Check inbox spam folder
4. Try email fallback option
```

### **Colleges scroll doesn't reach end**
```
Solution: Already fixed! (height: 520vh)
If still issues:
- Check height in colleges.html <section> tag
- Increase to 550vh or 600vh if needed
```

---

## **📈 Next Steps**

### **After Launch:**

1. **Collect feedback** via the feedback form
2. **Monitor games** - which are most played?
3. **Update content** - add new quotes, careers, words
4. **Refine** - based on student feedback

### **Future Enhancements:**

- Add leaderboard (localStorage)
- Create user accounts
- Add more games
- Enable multiplayer
- Create printable certificates

---

## **📞 Support Resources**

- **README.md** - Complete documentation
- **Browser DevTools** (F12) - Debug issues
- **Network Tab** - Check file loading
- **Lighthouse** (in Chrome DevTools) - Performance check

---

## **✨ You're Ready!**

All files are optimized and tested. Simply:

1. ✅ Copy files to server
2. ✅ Update Formspree ID (1 minute)
3. ✅ Update creator names (2 minutes)
4. ✅ Test everything loads (5 minutes)
5. ✅ Go live!

**Total setup time: ~10 minutes**

---

## **Preview**

Students will experience:

1. **Landing Page** → Dramatic title with 3D effects
2. **History** → Book flip through English eras
3. **Careers** → Rotating ring of job sectors
4. **Colleges** → Horizontal scroll with images
5. **Games** → 11 interactive challenges
6. **Feedback** → Seal & send their thoughts

---

**Happy launching! 🎭📚✨**

Questions? Check `README.md` for detailed docs.
