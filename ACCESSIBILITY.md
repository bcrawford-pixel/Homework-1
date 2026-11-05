# Accessibility Audit & Reflection

## Documented WAVE Issues & Fixes

### 1. Invalid Image Attribute
* **WAVE Report:** Invalid HTML attribute (`center`) on image element.
* **Element Affected:** `<img src="character-playing-videogames.jpg" center ...>`
* **User Impact:** Using non-standard HTML attributes like `center` causes unpredictable browser rendering and invalid HTML markup. Assistive technologies such as screen readers can misinterpret or ignore elements with invalid syntax, creating navigation barriers for visually impaired users.
* **Fix Applied:** Removed the obsolete `center` attribute from the HTML tag and implemented layout centering via CSS.

### 2. Redundant Alt Text & Caption
* **WAVE Report:** Redundant alternative text matching figure caption.
* **Element Affected:** `<img src="character-playing-videogames.jpg" alt="A person playing video games" />` inside `<figure>` with `<figcaption>Playing video games by myself</figcaption>`.
* **User Impact:** Screen reader users encounter repetitive descriptions when both the `alt` text and the caption express nearly identical information. This creates unnecessary cognitive load and slows down content consumption for auditory learners and screen reader users.
* **Fix Applied:** Updated the `alt` text to describe specific visual details of the image while allowing the `<figcaption>` to serve as the contextual label.

### 3. Missing Structural Landmark Navigation
* **WAVE Report:** Structural navigation landmark missing explicit region labeling.
* **Element Affected:** `<nav class="main-nav">`
* **User Impact:** Screen readers allow users to jump between major page landmarks (navigation, main content, footer). Without explicit labeling, users relying on screen readers cannot distinguish primary navigation from secondary or menu links on complex sites.
* **Fix Applied:** Added `aria-label="Main navigation"` to the `<nav>` tag and included a functioning skip-to-content link (`<a class="skip-link" href="#main-content">`) at the start of `<body>`.

---

## Written Reflection

Prior to conducting this accessibility audit, I viewed web development primarily through the lens of visual presentation and aesthetics. Analyzing my code using the WAVE tool fundamentally shifted my understanding of inclusive design. I realized that visual appeal means very little if assistive technologies cannot properly parse and navigate a page's structure. Learning how screen reader users rely on semantic landmarks, accurate heading hierarchies, and logical skip links highlighted how small coding decisions directly impact real users. 

Moving forward, I will prioritize web accessibility from the very beginning of my development process rather than treating it as a final polish step. This experience taught me to write valid HTML5, write meaningful and distinct alternative text, and ensure that every visual layout choice is supported by clean code and accessible design principles. Accessibility isn't just about compliance; it's about making content usable for everyone.
