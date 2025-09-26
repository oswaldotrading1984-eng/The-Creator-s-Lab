# The Creator's Lab — GitHub Pages setup

This repository now contains a polished static site ready to publish via GitHub Pages.

What I added for you:

- `docs/index.html` — the website (cleaned and improved).
- `.github/workflows/pages.yml` — GitHub Actions workflow that publishes the `docs/` folder on push to `main`.

Quick publish steps (one-time):

1. Make the repository public (GitHub → Settings → General → Repository visibility).
2. Commit and push your changes to the `main` branch:

```bash
git add .
git commit -m "Prepare site for GitHub Pages (docs + workflow)"
git push origin main
```

3. The Actions workflow will run and publish the `docs/` folder. Track progress under the repository's Actions tab.

4. Your site will be available at:

    `https://<your-github-username>.github.io/<repository-name>/`

Notes & troubleshooting:

- Ensure the repository is public; GitHub Pages from private repos require special configuration.
- If you prefer manual publishing, go to Settings → Pages and choose `main` / `docs` as the source.
- If the workflow fails, open the Actions tab, copy the failing logs here and I will help fix them.

If you want, I can also:

- Open a pull request with these changes.
- Use the `gh` CLI to create a new repo and push (you'll need to provide auth).

Next step: push the current branch to GitHub. See command above.
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>The Creator's Lab 🎨</title>
<style>
/* ---------------- Global Styles ---------------- */
* { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; }
body { background-color: #f4f4f8; color: #111; scroll-behavior: smooth; transition: background-color 0.3s, color 0.3s; }
a { text-decoration: none; color: inherit; }
header { position: fixed; top:0; left:0; width:100%; background:#1abc9c; color:white; display:flex; justify-content:space-between; align-items:center; padding:1rem 2rem; z-index:1000; box-shadow:0 2px 8px rgba(0,0,0,0.1);}
header h1 { font-size:1.8rem; font-weight:bold; }
nav a { margin-left:1.5rem; font-weight:600; cursor:pointer; transition:0.2s; }
nav a:hover { opacity:0.8; }
section { padding:100px 5%; min-height:100vh; }
section h2 { font-size:2rem; margin-bottom:1rem; border-bottom:2px solid #1abc9c; display:inline-block; padding-bottom:0.2rem; }
button { cursor:pointer; border:none; border-radius:5px; padding:0.6rem 1.2rem; background:#1abc9c; color:white; font-weight:bold; transition:0.2s; }
button:hover { background:#16a085; }
input, textarea, select { width:100%; padding:0.8rem; margin-top:0.5rem; border:1px solid #ccc; border-radius:5px; }
textarea { resize:none; }
.container { max-width:1200px; margin:0 auto; }
/* ---------------- Dark Mode ---------------- */
body.dark-mode { background-color:#111; color:#eee; }
body.dark-mode header { background:#16a085; }
body.dark-mode section h2 { border-color:#16a085; }
body.dark-mode button { background:#16a085; }
body.dark-mode button:hover { background:#1abc9c; }
/* ---------------- Section Styles ---------------- */
#home { display:flex; flex-direction:column; justify-content:center; align-items:center; text-align:center; height:100vh; background:linear-gradient(135deg, #1abc9c, #16a085); color:white; }
#home h1 { font-size:3rem; margin-bottom:1rem; }
#home p { font-size:1.2rem; margin-bottom:2rem; }
#services, #portfolio, #staff, #tickets, #contact { background:#f9f9f9; }
body.dark-mode #services, body.dark-mode #portfolio, body.dark-mode #staff, body.dark-mode #tickets, body.dark-mode #contact { background:#222; }
.card-grid { display:grid; grid-template-columns:repeat(auto-fit,minmax(250px,1fr)); gap:1.5rem; margin-top:2rem; }
.card { background:white; padding:1rem; border-radius:8px; box-shadow:0 2px 10px rgba(0,0,0,0.1); transition:0.3s; }
.card:hover { transform:translateY(-5px); box-shadow:0 4px 15px rgba(0,0,0,0.2); }
body.dark-mode .card { background:#333; box-shadow:0 2px 10px rgba(0,0,0,0.4); }
/* ---------------- Additional Responsive Styles ---------------- */
@media (max-width: 768px){
    header { flex-direction: column; align-items: flex-start; }
    nav a { margin: 0.5rem 0; display: none; font-size:1.2rem; }
    #home h1 { font-size:2.5rem; }
    #home p { font-size:1rem; }
    .card-grid { grid-template-columns:repeat(auto-fit,minmax(200px,1fr)); }
}
@media (max-width: 480px){
    #home h1 { font-size:2rem; }
    #home p { font-size:0.9rem; }
    button { padding:0.5rem 1rem; font-size:0.9rem; }
}
</style>
</head>
<body>
<header>
<h1>The Creator's Lab 🎨</h1>
<nav>
<a href="#home">Home</a>
<a href="#services">Services</a>
<a href="#portfolio">Portfolio</a>
<a href="#staff">Staff</a>
<a href="#tickets">Tickets</a>
<a href="#contact">Contact</a>
<button id="darkModeToggle">🌙</button>
</nav>
</header>

<!-- ---------------- Home Section ---------------- -->
<section id="home">
<h1>Welcome to The Creator's Lab</h1>
<p>Your hub for custom designs, graphics, Discord services, and creative projects!</p>
<a href="https://discord.gg/YOURSERVER" target="_blank"><button>Join Our Discord 🚀</button></a>
</section>

<!-- ---------------- Services Section ---------------- -->
<section id="services">
<h2>🎨 Services</h2>
<div class="card-grid">
<div class="card"><h3>Graphics & Logos</h3><p>Custom logos, banners, and social media graphics designed to perfection.</p></div>
<div class="card"><h3>Discord Bots</h3><p>Custom Discord bots with full functionality, slash commands, and server integration.</p></div>
<div class="card"><h3>Vehicle Liveries</h3><p>High-quality vehicle designs for roleplay servers, personal projects, or community showcases.</p></div>
<div class="card"><h3>Uniforms & Clothing</h3><p>Custom uniforms, merch, and clothing designs for your team or community.</p></div>
</div>
</section>

<!-- ---------------- Portfolio Section ---------------- -->
<section id="portfolio">
<h2>🖼 Portfolio</h2>
<div class="card-grid" id="portfolioGallery">
<!-- 20 Portfolio Items -->
<div class="card"><img src="https://via.placeholder.com/300x200"><p>Logo Project #1</p></div>
<div class="card"><img src="https://via.placeholder.com/300x200"><p>Discord Bot Interface</p></div>
<div class="card"><img src="https://via.placeholder.com/300x200"><p>Vehicle Livery</p></div>
<div class="card"><img src="https://via.placeholder.com/300x200"><p>Custom Uniform</p></div>
<div class="card"><img src="https://via.placeholder.com/300x200"><p>Banner Design</p></div>
<div class="card"><img src="https://via.placeholder.com/300x200"><p>Logo Animation</p></div>
<div class="card"><img src="https://via.placeholder.com/300x200"><p>Bot Dashboard UI</p></div>
<div class="card"><img src="https://via.placeholder.com/300x200"><p>Livery Series #2</p></div>
<div class="card"><img src="https://via.placeholder.com/300x200"><p>Uniform Mockup</p></div>
<div class="card"><img src="https://via.placeholder.com/300x200"><p>Promotional Graphic</p></div>
<div class="card"><img src="https://via.placeholder.com/300x200"><p>Logo Set #3</p></div>
<div class="card"><img src="https://via.placeholder.com/300x200"><p>Bot Features UI</p></div>
<div class="card"><img src="https://via.placeholder.com/300x200"><p>Livery Series #3</p></div>
<div class="card"><img src="https://via.placeholder.com/300x200"><p>Team Uniform Concept</p></div>
<div class="card"><img src="https://via.placeholder.com/300x200"><p>Social Media Banner</p></div>
<div class="card"><img src="https://via.placeholder.com/300x200"><p>Event Poster</p></div>
<div class="card"><img src="https://via.placeholder.com/300x200"><p>UI Prototype</p></div>
<div class="card"><img src="https://via.placeholder.com/300x200"><p>Community Logo Pack</p></div>
<div class="card"><img src="https://via.placeholder.com/300x200"><p>Bot Command Layout</p></div>
<div class="card"><img src="https://via.placeholder.com/300x200"><p>Vehicle Concept Art</p></div>
</div>
</section>

<!-- ---------------- Staff Section ---------------- -->
<section id="staff">
<h2>👥 Our Team</h2>
<div class="card-grid">
<div class="card"><h3>Mikey</h3><p>Server Owner</p></div>
<div class="card"><h3>Noah</h3><p>Lead Developer</p></div>
<div class="card"><h3>Olivia</h3><p>Graphics Designer</p></div>
<div class="card"><h3>James</h3><p>Bot Specialist</p></div>
<div class="card"><h3>Alice</h3><p>Project Coordinator</p></div>
<div class="card"><h3>David</h3><p>Web Designer</p></div>
<div class="card"><h3>Sophia</h3><p>UI/UX Designer</p></div>
<div class="card"><h3>Leo</h3><p>Community Manager</p></div>
</div>
</section>

<!-- ---------------- Tickets Section ---------------- -->
<section id="tickets">
<h2>🎟 Open a Ticket</h2>
<p>Submit your request and our team will get back to you promptly!</p>
<form id="ticketForm">
<label>Your Name</label>
<input type="text" id="ticketName" required>
<label>Type of Request</label>
<select id="ticketType" required>
<option value="General Inquiry">General Inquiry</option>
<option value="Graphics Request">Graphics Request</option>
<option value="Bot Development">Bot Development</option>
<option value="Other">Other</option>
</select>
<label>Description</label>
<textarea id="ticketDesc" rows="5" required></textarea>
<button type="submit">Submit Ticket</button>
</form>
<div id="ticketResponse" style="margin-top:1rem; font-weight:bold;"></div>
</section>

<!-- ---------------- Contact Section ---------------- -->
<section id="contact">
<h2>📩 Contact Us</h2>
<p>Have questions or want to reach out directly? Fill the form below!</p>
<form id="contactForm">
<label>Your Name</label>
<input type="text" id="contactName" required>
<label>Email</label>
<input type="email" id="contactEmail" required>
<label>Message</label>
<textarea id="contactMessage" rows="5" required></textarea>
<button type="submit">Send Message</button>
</form>
<div id="contactResponse" style="margin-top:1rem; font-weight:bold;"></div>
</section>

<!-- ---------------- Back-to-Top Button ---------------- -->
<button id="backToTop" style="position:fixed;bottom:30px;right:30px;padding:0.8rem 1.2rem;background:#1abc9c;color:white;border:none;border-radius:50px;font-size:1.2rem;cursor:pointer;display:none;z-index:1000;">⬆️</button>

<footer style="text-align:center; padding:2rem; background:#1abc9c; color:white;">
<p>© 2025 The Creator's Lab | Made with ❤️ by our team</p>
</footer>

<script>
// ---------------- Dark/Light Mode ----------------
const darkModeToggle = document.getElementById('darkModeToggle');
darkModeToggle.addEventListener('click', () => {
    document.body.classList.toggle('dark-mode');
    darkModeToggle.textContent = document.body.classList.contains('dark-mode') ? '☀️' : '🌙';
});

// ---------------- Smooth Scroll ----------------
document.querySelectorAll('nav a').forEach(anchor => {
    anchor.addEventListener('click', function(e){
        e.preventDefault();
        document.querySelector(this.getAttribute('href')).scrollIntoView({behavior:'smooth'});
    });
});

// ---------------- Ticket Form → Discord Webhook ----------------
const ticketForm = document.getElementById('ticketForm');
const ticketResponse = document.getElementById('ticketResponse');
ticketForm.addEventListener('submit', async (e) => {
    e.preventDefault();
    const payload = {
        content:null,
        embeds:[{title:`🎟 New Ticket: ${document.getElementById('ticketType').value}`,
        description:`**Name:** ${document.getElementById('ticketName').value}\n**Type:** ${document.getElementById('ticketType').value}\n**Description:** ${document.getElementById('ticketDesc').value}`,
        color:3066993,
        timestamp:new Date().toISOString()}]
    };
    try{
        await fetch('https://discord.com/api/webhooks/1414288231943377026/eelZ6EuqrlAqc2AvuZ3bokFkExL0z-BfACZ5qq7JoI3cvCBT2LSk3PZPqf3HXd65NZx_',{method:'POST',headers:{'Content-Type':'application/json'},body:JSON.stringify(payload)});
        ticketResponse.textContent = '✅ Ticket submitted successfully!';
        ticketForm.reset();
    }catch(err){ticketResponse.textContent='❌ Error submitting ticket.';console.error(err);}
});

// ---------------- Contact Form → Discord Webhook ----------------
const contactForm = document.getElementById('contactForm');
const contactResponse = document.getElementById('contactResponse');
contactForm.addEventListener('submit', async (e) => {
    e.preventDefault(https://discord.com/api/webhooks/1414288231943377026/eelZ6EuqrlAqc2AvuZ3bokFkExL0z-BfACZ5qq7JoI3cvCBT2LSk3PZPqf3HXd65NZx_);
    const payload = {
        content:null,
        embeds:[{title:'📩 Contact Form Submission',
        description:`**Name:** ${document.getElementById('contactName').value}\n**Email:** ${document.getElementById('contactEmail').value}\n**Message:** ${document.getElementById('contactMessage').value}`,
        color:3447003,
        timestamp:new Date().toISOString()}]
    };
    try{
        await fetch('',{method:'POST',headers:{'Content-Type':'application/json'},body:JSON.stringify(payload)});
        contactResponse.textContent='✅ Message sent successfully!';
        contactForm.reset();
    }catch(err){contactResponse.textContent='❌ Error sending message.';console.error(err);}
});

// ---------------- Back-to-Top Button ----------------
const backToTop = document.getElementById('backToTop');
window.addEventListener('scroll',()=>{
    backToTop.style.display=window.scrollY>500?'block':'none';
});
backToTop.addEventListener('click',()=>{window.scrollTo({top:0,behavior:'smooth'});});

// ---------------- Card Hover Animations ----------------
const cards = document.querySelectorAll('.card');
cards.forEach(card=>{
    card.addEventListener('mouseover',()=>{card.style.transform='scale(1.08)';card.style.boxShadow='0 12px 25px rgba(0,0,0,0.35)';});
    card.addEventListener('mouseout',()=>{card.style.transform='scale(1)';card.style.boxShadow='0 2px 10px rgba(0,0,0,0.1)';});
});

// ---------------- Scroll Fade-in Animation ----------------
const fadeSections = document.querySelectorAll('section');
window.addEventListener('scroll',()=>{
    const scrollY=window.scrollY+window.innerHeight;
    fadeSections.forEach(sec=>{
        if(scrollY>sec.offsetTop+100){sec.style.opacity=1;sec.style.transform='translateY(0)';sec.style.transition='opacity 0.6s ease-out, transform 0.6s ease-out';}else{sec.style.opacity=0;sec.style.transform='translateY(50px)';}
    });
});

// ---------------- Footer Fade-in ----------------
const footer=document.querySelector('footer');
footer.style.opacity=0;
window.addEventListener('scroll',()=>{if(window.scrollY+window.innerHeight>footer.offsetTop){footer.style.transition='opacity 1s ease-out';footer.style.opacity=1;}});
</script>
</body>
</html>
