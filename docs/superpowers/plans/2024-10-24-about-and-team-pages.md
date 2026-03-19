# About and Team Pages Implementation Plan

> **For agentic workers:** REQUIRED: Use superpowers:subagent-driven-development (if subagents available) or superpowers:executing-plans to implement this plan. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Create an About page and a Team page, sharing common styling with the existing site.

**Architecture:** Extract common CSS from `index.html` into a new `styles.css`. Create `about.html` and `team.html` that leverage this shared stylesheet, the common header, and the common footer. Add new CSS rules for the team grid.

**Tech Stack:** HTML, CSS

---

### Task 0: Content Improvement (Completed)

The page content has been refined by the marketing writer agent:

**About Page** - Now structured with clear sections (Mission, What We Do, Why It Matters), bullet points, and improved readability while maintaining B2B tone.

**Team Page** - Bios polished with grammatical fixes and consistent formatting.

---

### Task 1: Extract Shared CSS

**Files:**
- Create: `styles.css`
- Modify: `index.html`

- [ ] **Step 1: Create `styles.css` and copy styles from `index.html`**

Extract the contents of the `<style>` block in `index.html` (lines 8-895 approx, just the CSS) and place it into `styles.css`.

- [ ] **Step 2: Update `index.html` to link to the new stylesheet**

Remove the inline `<style>` block in `index.html` and replace it with:
`<link rel="stylesheet" href="styles.css">`

- [ ] **Step 3: Update Navigation Links in `index.html`**

Update the header navigation links in `index.html`:
```html
<ul class="nav-links">
    <li><a href="index.html">Home</a></li>
    <li><a href="about.html">About</a></li>
    <li><a href="team.html">Team</a></li>
    <li><a href="index.html#features">Features</a></li>
    <li><a href="index.html#contact">Contact</a></li>
</ul>
```
And similarly update the Footer links under "Company":
```html
<h3>Company</h3>
<ul>
    <li><a href="about.html">About</a></li>
    <li><a href="team.html">Team</a></li>
    <li><a href="#">Blog</a></li>
    <li><a href="index.html#contact">Contact</a></li>
</ul>
```

- [ ] **Step 4: Verify `index.html` still renders correctly**

(Visual check if possible, or verify no syntax errors)

### Task 2: Create the About Page

**Files:**
- Create: `about.html`

- [ ] **Step 1: Create the base HTML structure for `about.html`**

Copy the entire `index.html` file to `about.html`. This ensures the `<head>`, `<header>`, and `<footer>` are identical.

- [ ] **Step 2: Replace the body content with About information**

Remove the `hero`, `stats`, `features`, `waitlist`, and `contact` sections from `about.html`.
Replace them with this improved content:
```html
<section class="hero" style="padding: 8rem 2rem 2rem;">
    <div class="hero-container">
        <h1 class="fade-in">About <span class="highlight">Archetype</span></h1>
        <p class="fade-in" style="max-width: 800px;">Revolutionizing the electrical product safety certification process.</p>
    </div>
</section>

<section class="features" style="background: var(--white); padding: 4rem 2rem;">
    <div class="features-container" style="text-align: left; max-width: 800px; margin: 0 auto;">
        <h2 style="font-size: 2rem; margin-bottom: 1.5rem; color: var(--dark-gray);">Simplifying Electrical Product Certification</h2>
        
        <p class="fade-in" style="margin-bottom: 2rem;">Archetype bridges the gap between manufacturers and certification bodies, revolutionizing the electrical product safety certification process. We prioritize efficiency—understanding that for manufacturers, time is more valuable than money.</p>
        
        <h3 style="font-size: 1.5rem; margin-bottom: 1rem; color: var(--dark-gray);">Our Mission</h3>
        <p class="fade-in" style="margin-bottom: 2rem;">We streamline the certification journey by helping manufacturers identify the specific standards they should be asking certification bodies about, reducing confusion and saving valuable time.</p>
        
        <h3 style="font-size: 1.5rem; margin-bottom: 1rem; color: var(--dark-gray);">What We Do</h3>
        <ul class="fade-in" style="margin-bottom: 2rem; padding-left: 1.5rem; color: var(--text-gray);">
            <li style="margin-bottom: 1rem;"><strong>Standards Guidance:</strong> We help manufacturers pinpoint exactly which standards apply to their products, so they can ask the right questions and avoid costly delays.</li>
            <li style="margin-bottom: 1rem;"><strong>Proactive Updates:</strong> We empower manufacturers to stay ahead by tracking changes to the standards their certifications are based on.</li>
            <li style="margin-bottom: 1rem;"><strong>Certification Body Collaboration:</strong> Our guidance on working effectively with certification bodies ensures products receive certifications on time—crucial for maintaining production schedules.</li>
            <li><strong>Certification Directory:</strong> Manufacturers can post their certifications on our website, creating a centralized platform where customers can find certified components for their own compliance needs.</li>
        </ul>
        
        <h3 style="font-size: 1.5rem; margin-bottom: 1rem; color: var(--dark-gray);">Why It Matters</h3>
        <p class="fade-in" style="margin-bottom: 1rem;">One of the most common reasons for missed production dates is the difficulty in locating appropriately certified components. By providing a searchable directory of certified products, we help manufacturers:</p>
        <ul class="fade-in" style="padding-left: 1.5rem; color: var(--text-gray); margin-bottom: 2rem;">
            <li style="margin-bottom: 0.5rem;">Reduce the risk of production delays</li>
            <li style="margin-bottom: 0.5rem;">Accelerate time-to-market for their products</li>
            <li style="margin-bottom: 0.5rem;">Support their customers in meeting compliance requirements efficiently</li>
            <li>Create a more interconnected ecosystem that benefits all parties</li>
        </ul>
        
        <p class="fade-in">Our goal is to minimize the financial losses associated with missed certification timelines while enhancing operational efficiency for every customer we serve.</p>
    </div>
</section>
```

- [ ] **Step 3: Update JavaScript in `about.html`**
Remove the smooth scrolling logic that relies on IDs (`#`), as this is a separate page now. Keep the fade-in intersection observer.

### Task 3: Create the Team Page

**Files:**
- Create: `team.html`
- Modify: `styles.css`

- [ ] **Step 1: Add Team Grid CSS to `styles.css`**

Add the following to the bottom of `styles.css`:
```css
/* Team Section */
.team-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 3rem;
    margin-top: 3rem;
}

.team-member {
    background: var(--white);
    padding: 2.5rem;
    border-radius: 12px;
    box-shadow: 0 4px 20px rgba(0,0,0,0.08);
    transition: all 0.3s ease;
    text-align: center;
}

.team-member:hover {
    transform: translateY(-5px);
    box-shadow: 0 12px 40px rgba(0,0,0,0.15);
}

.team-avatar {
    width: 120px;
    height: 120px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--blush-pink), var(--eucalyptus-green));
    margin: 0 auto 1.5rem;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    font-size: 3rem;
    font-weight: bold;
}

.team-member h3 {
    font-size: 1.5rem;
    color: var(--dark-gray);
    margin-bottom: 0.5rem;
}

.team-role {
    color: var(--blush-pink);
    font-weight: 600;
    margin-bottom: 1.5rem;
    display: block;
}

.team-bio {
    color: var(--text-gray);
    font-size: 0.95rem;
    line-height: 1.6;
    text-align: left;
}
```

- [ ] **Step 2: Create the base HTML structure for `team.html`**

Copy `about.html` to `team.html`.

- [ ] **Step 3: Replace the body content with Team information**

```html
<section class="hero" style="padding: 8rem 2rem 2rem;">
    <div class="hero-container">
        <h1 class="fade-in">Meet Our <span class="highlight">Team</span></h1>
        <p class="fade-in" style="max-width: 800px;">The experts behind Archetype driving innovation in certification.</p>
    </div>
</section>

<section class="features" style="background: var(--light-gray); padding: 4rem 2rem;">
    <div class="features-container">
        <div class="team-grid">
            <!-- Mary Foerster -->
            <div class="team-member fade-in">
                <div class="team-avatar">M</div>
                <h3>Mary Foerster</h3>
                <span class="team-role">CEO & Founder</span>
                <p class="team-bio">With over a decade of experience in the certification ecosystem, Mary brings a unique perspective to our mission. Her inquisitive nature helps her connect the dots in complex processes, guiding manufacturers through certification smoothly. Passionate about helping others, she thrives on simplifying the intricacies of certification. Her established relationships with both manufacturers and certification bodies strengthen our network and keep us at the forefront of industry standards.</p>
            </div>

            <!-- Dr. Tomer Libal -->
            <div class="team-member fade-in">
                <div class="team-avatar">T</div>
                <h3>Dr. Tomer Libal</h3>
                <span class="team-role">CTO</span>
                <p class="team-bio">Dr. Tomer Libal brings over 24 years of AI expertise, with a focused interest in AI and Law since 2017. He served as a tenured professor of AI at the American University of Paris (2017–2024) and was a principal investigator on access-to-justice projects at the University of Luxembourg. Dr. Libal's practical knowledge of AI applications in legal and regulatory domains drives our technology strategy.</p>
            </div>

            <!-- Devin Buell -->
            <div class="team-member fade-in">
                <div class="team-avatar">D</div>
                <h3>Devin Buell</h3>
                <span class="team-role">COO</span>
                <p class="team-bio">Devin has over 15 years of experience bringing new products to market, including building teams and processes from the ground up. He has led multiple development teams, managed sustained business operations, and built lasting partnerships. This experience positions Archetype to scale effectively—establishing the right team and processes to grow the business and hone our customer base.</p>
            </div>

            <!-- Steven Foerster -->
            <div class="team-member fade-in">
                <div class="team-avatar">S</div>
                <h3>Steven Foerster</h3>
                <span class="team-role">VP of Engineering</span>
                <p class="team-bio">Steven brings over 28 years of experience building systems at the intersection of cybersecurity, automation, and AI. He specializes in taking hard problems in secure infrastructure and making them usable and resilient.</p>
            </div>
        </div>
    </div>
</section>
```
