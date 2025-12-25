# Ex.08 Design of Interactive Image Gallery
# Date:
# AIM:
To design a web application for an inteactive image gallery with minimum five images.

# DESIGN STEPS:
## Step 1:
Clone the github repository and create Django admin interface.

## Step 2:
Change settings.py file to allow request from all hosts.

## Step 3:
Use CSS for positioning and styling.

## Step 4:
Write JavaScript program for implementing interactivity.

## Step 5:
Validate the HTML and CSS code.

## Step 6:
Publish the website in the given URL.

# PROGRAM :
```
home.html

{% load static %}
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Image Gallery</title>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background: #000;
  color: #fff;
  font-family: serif;
}

/* Title */
.title {
  text-align: center;
  padding: 30px 0;
  font-style: italic;
}

/* Gallery */
.gallery {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 40px;
  padding: 60px 5%;
}

.gallery img {
  width: 100%;
  aspect-ratio: 1/1;
  object-fit: cover;
  cursor: pointer;
}

/* Modal */
.modal {
  position: fixed;
  inset: 0;
  background: rgba(0,0,0,0.75);
  display: none;
  align-items: center;
  justify-content: center;
  z-index: 1000;
}

.modal-box {
  background: #e6e6e6;
  padding: 25px;
  border-radius: 35px;
  width: min(90%, 380px);
  text-align: center;
}

.modal-box img {
  width: 100%;
  border-radius: 25px;
  margin-bottom: 20px;
}

/* Buttons */
.modal-box button {
  width: 100%;
  padding: 12px;
  margin-top: 10px;
  border-radius: 25px;
  border: 2px solid #000;
  background: #7ed957;
  font-size: 18px;
  cursor: pointer;
}

</style>
</head>

<body>

<header class="title">image<br>gallery</header>

<section class="gallery">
  <img src="{% static 'ad1.png' %}" onclick="openModal(0)">
  <img src="{% static 'ad2.png' %}" onclick="openModal(1)">
  <img src="{% static 'ad3.png' %}" onclick="openModal(2)">
  <img src="{% static 'ad4.png' %}" onclick="openModal(3)">
  <img src="{% static 'ad5.png' %}" onclick="openModal(4)">
</section>

<!-- MODAL -->
<div class="modal" id="modal">
  <div class="modal-box">
    <img id="modal-img">
    <button onclick="nextImg()">next</button>
    <button onclick="prevImg()">back</button>
    <button onclick="closeModal()">close</button>
  </div>
</div>
<script>
    const images = [
  "{% static 'ad1.png' %}",
  "{% static 'ad2.png' %}",
  "{% static 'ad3.png' %}",
  "{% static 'ad4.png' %}",
  "{% static 'ad5.png' %}"
];

let current = 0;

function openModal(index) {
  current = index;
  document.getElementById("modal").style.display = "flex";
  document.getElementById("modal-img").src = images[current];
}

function closeModal() {
  document.getElementById("modal").style.display = "none";
}

function nextImg() {
  current = (current + 1) % images.length;
  document.getElementById("modal-img").src = images[current];
}

function prevImg() {
  current = (current - 1 + images.length) % images.length;
  document.getElementById("modal-img").src = images[current];
}

</script>
</body>
</html>
```
# OUTPUT:
<img width="1919" height="1079" alt="528705154-39f63874-18db-4557-84c4-c02e895065e4" src="https://github.com/user-attachments/assets/b45a92a1-49ca-46f3-9ba0-19fca23e6d1f" />
<img width="1919" height="1078" alt="528705026-95bfbfea-cffd-4a83-9a75-d7ec8e825c56" src="https://github.com/user-attachments/assets/d4399c5a-5efa-43a0-a997-6991daa7653a" />

# RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
