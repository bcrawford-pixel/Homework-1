# Accessibility Audit & Reflection

## Documented WAVE Issues & Fixes

### 1. Invalid Image Attribute
* **WAVE Report:** Invalid HTML attribute (`center`) on image element.
* **Element Affected:** `<img src="character-playing-videogames.jpg" center ...>`
* **User Impact:** Using old or unsupported attributes like `center` breaks standard HTML validation. Browsers and screen readers might get confused or fail to process the element correctly, creating extra barriers for visually impaired users trying to navigate the page.
* **Fix Applied:** Removed the outdated `center` attribute from the `<img>` tag in `index.html` so it follows clean HTML5 standards:
  ```html
  <img src="character-playing-videogames.jpg" alt="Gamer sitting comfortably holding a controller while focused on a video game" />
  2. Redundant Alt Text & Caption
WAVE Report: Alternative text redundant with figure caption.

Element Affected: <img src="character-playing-videogames.jpg" alt="A person playing video games" /> inside <figure> with <figcaption>Playing video games by myself</figcaption>.

User Impact: Having almost identical text in both the alt tag and the <figcaption> forces screen reader users to listen to the same exact sentence twice back-to-back. This creates annoying repetition and slows down how quickly users can consume the content.

Fix Applied: Changed the alt text to focus on key visual details while letting the caption provide the context: <img src="character-playing-videogames.jpg" alt="Gamer sitting comfortably holding a controller while focused on a video game" />
<figcaption>Playing video games by myself</figcaption>


3. Missing Structural Landmark Navigation & Skip Link
WAVE Report: Structural navigation landmark missing explicit region labeling and skip navigation.

Element Affected: <nav class="main-nav">

User Impact: Keyboard and screen reader users normally have to tab through every single navigation link before they can read the actual page content. Without clear landmark labels or a skip link, getting through the header feels slow and frustrating.

Fix Applied: Added aria-label="Main navigation" to the <nav> tag and placed a functional skip link at the top of <body>: <a class="skip-link" href="#main-content">Skip to main content</a>
<nav class="main-nav" aria-label="Main navigation">

Written Reflection
Before testing my site with WAVE, I mainly cared about how my code looked on the screen. Running an accessibility check completely changed how I think about building websites. I realized that an attractive design doesn't mean much if someone using a screen reader can't navigate the page smoothly. Seeing how small details—like adding a skip link, organizing heading tags, or labeling landmarks—make such a huge difference for screen reader users really opened my eyes to how important structure is.

Going forward, I am going to think about accessibility right from the start instead of treating it as something I fix at the very end. This project taught me the importance of writing clean, valid HTML, creating descriptive alt text that doesn't repeat captions, and making sure my sites are easy for everyone to use. Building accessible pages isn't just about passing a test; it's about making sure nobody gets left out when visiting my website.
