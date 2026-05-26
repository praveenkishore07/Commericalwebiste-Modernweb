# Commericalwebiste-Modernweb
# Ex02 Commercial Website
## Date: 20/05/26

## AIM
To create a commercial website using CSS Flexbox.

## ALGORITHM
### STEP 1
Create an HTML file (index.html)

### STEP 2
Create a CSS file (style.css)

### STEP 3
Include a navigation bar with links to different sections.

### STEP 4
Add structured sections for Homepage, Products / Services, About Us, Contact Details and User Account.

### STEP 5
Include social media links at the footer with copyright information.

### STEP 6
Define global styles for fonts, colors, and layout.

### STEP 7
Style the header, navigation bar, and sections.

### STEP 8
Use Flexbox for layout design.

### STEP 9
Add hover effects and transitions for interactivity.

### STEP 10
Add Images and Media.

### STEP 11
Use optimized images for a professional look.

### STEP 12
Open the HTML file in a browser to check layout and functionality.

### STEP 13
Fix styling issues and refine content placement.

### STEP 14
Deploy the website.

### STEP 15
Upload to GitHub Pages for free hosting.

## PROGRAM
```
base.html:

{% load static %}
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>{% block title %}Spice Delight{% endblock %}</title>
<style>
body {
  font-family: Arial, sans-serif;
  background: #f5f5f5;
  margin: 0; padding: 0;
}

header {
  background-color: #c0392b;
  padding: 10px;
  color: white;
}

nav ul {
  list-style: none;
  text-align: center;
  padding: 0;
}

nav ul li {
  display: inline-block;
  margin: 0 15px;
}

nav ul li a {
  color: white;
  text-decoration: none;
  font-weight: bold;
}

.banner {
  width: 100%;
  height: 300px;
  object-fit: cover;
}

.intro {
  padding: 40px;
  text-align: center;
}

.menu-grid, .team-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 20px;
  padding: 20px;
}

.menu-grid .item img, .team-grid .member img {
  width: 100%;
  border-radius: 10px;
}

footer {
  background-color: #333;
  color: white;
  text-align: center;
  padding: 10px;
}

</style>

</head>
<body>
  <header>
    <img src="{% static 'images/banner.jpg' %}" alt="Banner" class="banner">
    <nav>
      <ul>
        <li><a href="{% url 'home' %}">Home</a></li>
        <li><a href="{% url 'menu' %}">Menu</a></li>
        <li><a href="{% url 'administration' %}">Administration</a></li>
        <li><a href="{% url 'contact' %}">Contact Us</a></li>
      </ul>
    </nav>
  </header>

  <main>
    {% block content %}{% endblock %}
  </main>

  <footer>
    <p>Designed by Your Name © 2025</p>
  </footer>
</body>
</html>
```
```
contact.html:

{% extends 'base.html' %}
{% block title %}Contact Us — Spice Delight{% endblock %}
{% block content %}
<section class="contact">
  <h2>Contact Us</h2>
  <p>📍 Address: {{ contact.address }}</p>
  <p>📞 Phone: {{ contact.phone }}</p>
  <p>✉️ Email: {{ contact.email }}</p>
</section>
{% endblock %}
```
```
home.hmtl:

{% extends 'base.html' %}
{% block title %}Home — Spice Delight{% endblock %}
{% block content %}
<section class="intro">
  <h1>Welcome to Spice Delight</h1>
  <p>Serving traditional flavors with a modern twist. Join us for an unforgettable experience.</p>
</section>
{% endblock %}
```
```
menu.html: 

{% extends 'base.html' %}
{% load static%}
{% block title %}Menu — Spice Delight{% endblock %}
{% block content %}
<section class="menu">
  <h2>Our Menu</h2>
  <div class="menu-grid">
    {% for food in foods %}
      <div class="item">
        <img src="{% static 'images/'|add:food.image %}" alt="{{ food.name }}">
        <p>{{ food.name }}</p>
      </div>
    {% endfor %}
  </div>
</section>
{% endblock %}
```
```
adminstration.html: 

{% extends 'base.html' %}
{% load static%}
{% block title %}Administration — Spice Delight{% endblock %}
{% block content %}
<section class="team">
  <h2>Our Team</h2>
  <div class="team-grid">
    {% for member in team %}
      <div class="member">
        <img src="{% static 'images/'|add:member.image %}" alt="{{ member.name }}">
        <p>{{ member.name }} – {{ member.role }}</p>
      </div>
    {% endfor %}
  </div>
</section>
{% endblock %}
```
```
views: 
from django.shortcuts import render

def home_view(request):
    return render(request, 'home.html')

def menu_view(request):
    # example food list
    foods = [
        {'name': 'Ghee Dosa', 'image': 'menu/ghee.jpg'},
        {'name': 'Panner', 'image': 'menu/panner.jpg'},
       
        # add up to 12 ...
    ]
    return render(request, 'menu.html', {'foods': foods})

def admin_view(request):
    # team members list
    team = [
        {'name': 'Ajith Kumar', 'role': 'Head COOK', 'image': 'team/ak.jpg'},
        {'name': 'Dhanush', 'role': 'Manager', 'image': 'team/d,jpg.jpg'},
        # add 4 more ...
    ]
    return render(request, 'administration.html', {'team': team})

def contact_view(request):
    contact_info = {
        'address': '123 Spice Street, Chennai City',
        'phone': '+91-9876543210',
        'email': 'contact@spicedelight.com',
    }
    return render(request, 'contact.html', {'contact': contact_info})
```

## OUTPUT
<img width="1042" height="387" alt="Screenshot 2026-05-26 180759" src="https://github.com/user-attachments/assets/fb0d6240-1cbe-4920-8a5e-d33e47293c66" />
<img width="1037" height="472" alt="Screenshot 2026-05-26 180844" src="https://github.com/user-attachments/assets/7d466b96-e5c4-4845-8257-7517e7c28bef" />



## RESULT
The program for creating commercial website using CSS Flexbox is executed successfully.
