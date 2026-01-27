// ====================================
// THEME TOGGLE
// ====================================
const themeToggle = document.querySelector(’.theme-toggle’);
const body = document.body;

// Check for saved theme preference or default to light mode
const currentTheme = localStorage.getItem(‘theme’) || ‘light’;
body.setAttribute(‘data-theme’, currentTheme);

// Update icon based on current theme
updateThemeIcon(currentTheme);

themeToggle.addEventListener(‘click’, () => {
let theme = body.getAttribute(‘data-theme’);

```
if (theme === 'light') {
    body.setAttribute('data-theme', 'dark');
    localStorage.setItem('theme', 'dark');
    updateThemeIcon('dark');
} else {
    body.setAttribute('data-theme', 'light');
    localStorage.setItem('theme', 'light');
    updateThemeIcon('light');
}
```

});

function updateThemeIcon(theme) {
const icon = themeToggle.querySelector(‘i’);
if (theme === ‘dark’) {
icon.classList.remove(‘fa-moon’);
icon.classList.add(‘fa-sun’);
} else {
icon.classList.remove(‘fa-sun’);
icon.classList.add(‘fa-moon’);
}
}

// ====================================
// MOBILE MENU TOGGLE
// ====================================
const mobileMenuToggle = document.querySelector(’.mobile-menu-toggle’);
const navMenu = document.querySelector(’.nav-menu’);

mobileMenuToggle.addEventListener(‘click’, () => {
navMenu.classList.toggle(‘active’);
mobileMenuToggle.classList.toggle(‘active’);
});

// Close mobile menu when clicking on a nav link
const navLinks = document.querySelectorAll(’.nav-link’);
navLinks.forEach(link => {
link.addEventListener(‘click’, () => {
navMenu.classList.remove(‘active’);
mobileMenuToggle.classList.remove(‘active’);
});
});

// ====================================
// SMOOTH SCROLLING
// ====================================
document.querySelectorAll(‘a[href^=”#”]’).forEach(anchor => {
anchor.addEventListener(‘click’, function (e) {
const href = this.getAttribute(‘href’);

```
    // Don't prevent default for empty href or just "#"
    if (href === '#' || href === '') return;
    
    e.preventDefault();
    const target = document.querySelector(href);
    
    if (target) {
        const navbarHeight = document.querySelector('.navbar').offsetHeight;
        const targetPosition = target.offsetTop - navbarHeight;
        
        window.scrollTo({
            top: targetPosition,
            behavior: 'smooth'
        });
    }
});
```

});

// ====================================
// ACTIVE NAV LINK ON SCROLL
// ====================================
const sections = document.querySelectorAll(‘section[id]’);

window.addEventListener(‘scroll’, () => {
const scrollY = window.pageYOffset;

```
sections.forEach(section => {
    const sectionHeight = section.offsetHeight;
    const sectionTop = section.offsetTop - 100;
    const sectionId = section.getAttribute('id');
    const navLink = document.querySelector(`.nav-link[href="#${sectionId}"]`);
    
    if (scrollY > sectionTop && scrollY <= sectionTop + sectionHeight) {
        navLinks.forEach(link => link.classList.remove('active'));
        if (navLink) {
            navLink.classList.add('active');
        }
    }
});
```

});

// ====================================
// FORM HANDLING
// ====================================
const contactForm = document.getElementById(‘contactForm’);

contactForm.addEventListener(‘submit’, (e) => {
e.preventDefault();

```
const formData = new FormData(contactForm);
const name = formData.get('name');
const email = formData.get('email');
const message = formData.get('message');

// Basic validation
if (!name || !email || !message) {
    alert('Please fill in all fields');
    return;
}

// Email validation
const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
if (!emailRegex.test(email)) {
    alert('Please enter a valid email address');
    return;
}

// Here you would typically send the form data to a server
// For now, we'll just show a success message
alert(`Thank you, ${name}! Your message has been received. I'll get back to you soon.`);

// Reset form
contactForm.reset();
```

});

// ====================================
// SCROLL REVEAL ANIMATIONS
// ====================================
const observerOptions = {
threshold: 0.1,
rootMargin: ‘0px 0px -50px 0px’
};

const observer = new IntersectionObserver((entries) => {
entries.forEach(entry => {
if (entry.isIntersecting) {
entry.target.style.opacity = ‘1’;
entry.target.style.transform = ‘translateY(0)’;
}
});
}, observerOptions);

// Observe elements for fade-in animation
const animateElements = document.querySelectorAll(’.service-card, .stat-card, .experience-item, .project-card, .contact-card’);
animateElements.forEach(el => {
el.style.opacity = ‘0’;
el.style.transform = ‘translateY(30px)’;
el.style.transition = ‘opacity 0.6s ease, transform 0.6s ease’;
observer.observe(el);
});

// ====================================
// NAVBAR BACKGROUND ON SCROLL
// ====================================
const navbar = document.querySelector(’.navbar’);

window.addEventListener(‘scroll’, () => {
if (window.scrollY > 50) {
navbar.style.boxShadow = ‘0 4px 20px rgba(0, 0, 0, 0.3)’;
} else {
navbar.style.boxShadow = ‘0 4px 16px rgba(0, 0, 0, 0.15)’;
}
});

// ====================================
// PREVENT FRAMEWORK ROTATION ON MOBILE
// ====================================
if (window.innerWidth <= 768) {
const frameworkCircle = document.querySelector(’.framework-circle’);
if (frameworkCircle) {
frameworkCircle.style.animation = ‘none’;
}
}

// ====================================
// SERVICE CARDS MODAL (OPTIONAL)
// ====================================
const serviceLinks = document.querySelectorAll(’.service-link’);

serviceLinks.forEach(link => {
link.addEventListener(‘click’, (e) => {
e.preventDefault();
const serviceCard = link.closest(’.service-card’);
const serviceTitle = serviceCard.querySelector(’.service-title’).textContent;

```
    // You can implement a modal here to show more details
    // For now, we'll just show an alert
    alert(`More details about "${serviceTitle}" coming soon!`);
});
```

});

// ====================================
// CONSOLE WELCOME MESSAGE
// ====================================
console.log(’%c👋 Welcome to Japheth's Portfolio!’, ‘font-size: 20px; font-weight: bold; color: #C15F3C;’);
console.log(’%cBuilt with ❤️ using HTML, CSS, and JavaScript’, ‘font-size: 14px; color: #0D3B46;’);
console.log(’%cInterested in working together? Let's connect!’, ‘font-size: 14px; color: #2F2F2F;’);
