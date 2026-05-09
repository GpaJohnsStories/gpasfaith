# **GENERAL RULES — Updated: 5/9/2026**

## **1) Each repo works with only one website**
  gpas-faith = GpasFaith.com  
  gpas-kids = GpasKids.com  
  gpas-shop = GpasShop.com  
  
  *All pages in gpas-admin repo will NEVER be published to the web and active code will only be used on Gpa John's personal PC.*

---

## **2) Public and Admin sites share no components**  
Each public site (Faith, Kids, Shop) is fully independent. No cross‑site imports.

---

## **3a) ALL CODE must be HTML or JavaScript only**  
- No external CSS files may be created or referenced. All CSS must be inside the <style> block of the same HTML file.

## **3b) All public pages must be fully built with Accessibility Features**
- Resizable text
- Keyboard navigation
- Alternative text for images
- Captions or transcripts for video
- High Contrast option
- Ensure compatibility with assistive technologies like screen readers
- Accessibility code must not change the visual design unless the user activates a tool (High Contrast, Larger Text, etc.
- Since most commonly used browsers have most, if not all, of the necessary accessibility functions, they are not to be built into gpa's code. Instead there will be "Help" displayed to guide them in utilizing their browser as needed.

---

## **4) Shared Components MUST Be Loaded with fetch()**  
All shared UI components — public and admin — must be fetched into the page.

### **This includes:**
- All public headers (vertical menus)  
- All admin menus (vertical menus)  
- All footers (must always sit at the bottom)  
- All accessibility tools (Go To Top, High Contrast, Page Top, etc.)

### **Why fetch is required:**
- These components appear on every page  
- Updates must propagate instantly  
- They must run inside the page’s DOM  
- Floating tools must control the entire page  
- Fetch keeps the architecture consistent and helper‑friendly

## **5) Standard Screen Display Sizes**

- Tablet Landscape Mode and Desktops: ~1200px wide, 2–3 columns, partial desktop feel 
- Phone and Tablet Portrait Mode: ≤ 480px, Single column, 300–310px cells stack vertically 

Build code initially for faith, kids and shop to tablet landscape mode. Phone and portrait modes will be handled later...
Do not generate any phone‑specific CSS until explicitly instructed...
Build code for all admin pages ONLY for desktop/laptop screens...

## **6) ALL Story PDFs Must Be Displayed Using an `<iframe>`**  
- PDFs must never be embedded using <object> or <embed>. Only <iframe> is allowed.
- Story files are documents, not HTML components.

### **In the PDF iframe, Visitors must be able to:**
- View  
- Zoom  
- Scroll  
- Print  
- Download  

All of this is built into the browser’s PDF viewer.

### **Standard PDF iframe pattern:**
```html
<iframe 
  src="/stories/kids/STORYCODE.pdf"
  style="width:100%; height:100vh; border:none;">
</iframe>
```

---

## **7) Story cards and product cards are site‑specific**  
They are not shared across sites.

---

## **8) Frequently used pages may use hard‑coded text**  
This improves performance and reduces fetch calls.

---

## **9) Reusable Sections Must Be Standalone Files**  
Any component used on multiple pages must be its own HTML file and loaded via fetch.

### **Examples:**
- kids-menu-header.html  
- kids-footer.html  
- super-av.html  
- Floating tools (kids-break, high-contrast, page-top) combined into one vertical floating box

---

## **10) Standard HTML File Structure (Required Order)**  
Every recreated page must follow this exact structure:

1. `<head></head>`  
2. `<style></style>`  
3. `<body></body>`  
4. `<script></script>`

No additional <style> or <script> blocks may appear anywhere else in the file.

This ensures consistency, readability, and long‑term maintainability.

---

## **11) Every HTML File Must Be HEAVILY Documented**  
Use clear, descriptive comments to explain:

- What each function does  
- Major sections  
- Webtext placement  
- Anchors  
- Reusable blocks  
- Any non‑obvious logic  

This is essential for helpers and future maintainers.

---

## **12) IF Recreating pages from TSX, they must match the original TSX design**  
Colors, layout, spacing, and UI behavior must match the original site...
Matching design does NOT include React/TSX logic. Only the visual layout and behavior must match

---

## **13) All webtext and stories will be stored in GitHub repos**  
API keys and directory structure will be provided when needed.

---

## **14) All indexing will be done by a json index file, one for each site**  
All previous content on SupaBase has been moved to github for storage. 
Each file must be reformatted to either pdf or html format or deleted if no longer needed.

---

## **15) Only four fonts may be used across all GPAS sites**  
- **Kalam** — fun  
- **Lexend** — titles  
- **Georgia** — stories  
- **Gloria Hallelujah** (cursive, color `#0B3D91`) — Grandpa John’s notes/signature only

---

## **16) ALL existing Story files will Be Reformatted and Migrated to PDF**  
Grandpa John will:

- Reformat stories in Google Docs
- Embed photos  
- Set fonts, titles, paragraphs  
- Export as print‑ready PDF  
- Upload to GitHub using the 8‑digit story code = ?-nnn.bbb 
where ? = first character of category, nnn = sequential, unique number for that first character 
and bbb = file extension: html, pdf, url, mp3, mp4

---

## **17) ALL Non‑Hardcoded Webtext Will Be Migrated to HTML Files**  
Using a new admin tool based on super‑text:

- Clean HTML only  
- Includes titles, photos, formatting  
- Stored in GitHub using a 7‑digit code

---

## **18) No “inline junk” allowed**  
- No nested spans  
- No mystery classes  
- No hidden scripts  
- No leftover framework artifacts  

Clean HTML only.

---

## **19) Icons must be stored in GitHub Repo in "Icons" directory**  
Each site gets its own icon directories:

- `/site-code/icons/`  

All Icon Filenames must begin with `ICO`.  
If an icon is used on multiple sites, it must exist separately in each site’s repo.

---

## **20) Buttons and labels on public pages must follow GPAS style**  
- Buttons: 3D, pill‑shaped, rounded ends, minimum size 55px x 55px
- Labels: 3D, square/rectangular with slightly rounded corners  
- No hover effects (primary devices are tablets/phones)

---

## **21) No tooltips for photos or icons**  
However, accessibility code must be included for visually impaired users.

---

## **22) Bad Words Check**
- All text input fields, public or admin, unless they are created with a dropdown list, MUST be reviewed against the BadWords List...
- This includes search terms and phrases entered by site visitors.

---

# **SPECIFIC RULES FOR GPASFAITH.COM SITE**

## **A) Each Category type (identified by first character of fileCat) will require a unique specific display/format code**
CoPilot, or any other helping AI, must not guess or invent display rules...
Each category’s display format will be provided separately.

**END**
---
