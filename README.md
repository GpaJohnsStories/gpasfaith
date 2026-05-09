# Each repo works with only one website...
  gpas-faith = GpasFaith.com  
  gpas-kids = GpasKids.com  
  gpas-shop = GpasShop.com  
  
  All pages in gpas-admin repo will NEVER be published to the web and active code will only be used on Gpa John's personal PC.

### **GENERAL RULES — Updated: 1/9/2026**
## **1) Public and Admin sites share no components**  
Each site is fully independent. No cross‑site imports.

---

## **2) ALL CODE must be HTML or JavaScript only**  
No external CSS, no TSX, no TS.  
All styling must be done inside an inline `<style>` block in each HTML file.

---

## **3) Shared Components MUST Be Loaded with `fetch()`**  
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

Standard Screen Display Sizes…

Screen Type
Width Range
Layout Behavior
Tablet – Landscape and Desktops
~1200px
2–3 columns, partial desktop feel 
Phone Portrait and Tablet Portrait
≤ 480px 
Single column, 300–310px cells stack vertically 

Build code for faith, kids and shop to tablet landscape mode.
Build code for all admin pages ONLY for desktop/laptop screens

## **4) ALL Story PDFs Must Be Displayed Using an `<iframe>`**  
Story files are documents, not HTML components.

### **Visitors must be able to:**
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

## **5) Story cards and product cards are site‑specific**  
They are not shared across sites.

---

## **6) Frequently used pages may use hard‑coded text**  
This improves performance and reduces fetch calls.

---

## **7) Reusable Sections Must Be Standalone Files**  
Any component used on multiple pages must be its own HTML file and loaded via fetch.

### **Examples:**
- kids-menu-header.html  
- kids-footer.html  
- super-av.html  
- Floating tools (kids-break, high-contrast, page-top) combined into one vertical floating box

---

## **8) Standard HTML File Structure (Required Order)**  
Every recreated page must follow this exact structure:

1. `<head></head>`  
2. `<style></style>`  
3. `<body></body>`  
4. `<script></script>`

This ensures consistency, readability, and long‑term maintainability.

---

## **9) Every HTML File Must Be HEAVILY Documented**  
Use clear, descriptive comments to explain:

- What each function does  
- Major sections  
- Webtext placement  
- Anchors  
- Reusable blocks  
- Any non‑obvious logic  

This is essential for helpers and future maintainers.

---

## **10) Recreated pages must match the original TSX design**  
Colors, layout, spacing, and UI behavior must match the original site.

---

## **11) All webtext and stories will be stored in GitHub repos**  
API keys and directory structure will be provided when needed.

---

## **12) Supabase story table is retained for indexing only**  
Once all content is migrated to GitHub:

- The `content` field will be deleted  
- Other Supabase tables may be migrated, kept, or hard‑coded  
- Decisions will be made page‑by‑page by Grandpa John

---

## **13) Only four fonts may be used across all GPAS sites**  
- **Kalam** — fun  
- **Lexend** — titles  
- **Georgia** — stories  
- **Gloria Hallelujah** (cursive, color `#0B3D91`) — Grandpa John’s notes/signature only

---

## **14) ALL Story Files Must Be Reformatted and Migrated to PDF**  
Grandpa John will:

- Reformat stories in Google Docs
- Embed photos  
- Set fonts, titles, paragraphs  
- Export as print‑ready PDF  
- Upload to GitHub using the 7‑digit story code

---

## **15) ALL Non‑Hardcoded Webtext Must Be Migrated to HTML Files**  
Using a new admin tool based on super‑text:

- Clean HTML only  
- Includes titles, photos, formatting  
- Stored in GitHub using a 7‑digit code

---

## **16) No “inline junk” allowed**  
- No nested spans  
- No mystery classes  
- No hidden scripts  
- No leftover framework artifacts  

Clean HTML only.

---

## **17) Icons must be stored in GitHub, not Supabase**  
Each site gets its own icon directories:

- `/site-code/icons-core/`  
- `/site-code/icons-other/`  

All filenames must begin with `ICO`.  
If an icon is used on multiple sites, it must exist separately in each site’s repo.

---

## **18) Buttons and labels must follow GPAS style**  
- Buttons: 3D, pill‑shaped, rounded ends  
- Labels: 3D, square/rectangular with slightly rounded corners  
- No hover effects (primary devices are tablets/phones)

---

## **19) No tooltips for photos or icons**  
However, accessibility code must be included for visually impaired users.

---

## **20) GPASKIDS‑Specific Rules**  
1. Recreate the gpaskids title/menu bar → `kids-menu-header.html`  
2. Recreate the gpaskids footer → `kids-footer.html`  
3. Recreate the home page → `kids-home.html`  
4. Replace all webtext with hard‑coded text (except story cards)
