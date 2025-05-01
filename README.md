<!DOCTYPE html>
 <html lang="uk">
 <head>
     <meta charset="UTF-8">
     <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <title>Volkswagen</title>
     <link rel="icon" type="image/jpeg" href="images/05.jpg"> <!-- ІКОНКА ДЛЯ ВКЛАДКИ -->>
     <link rel="stylesheet" href="style.css">
 </head>
 <body>
   <header>
     <h1>Ласкаво просимо на наш сайт</h1>
   </header>
 
   <!-- Пошук -->
   <div class="search-bar">
     <input type="text" id="searchInput" placeholder="Пошук товарів..." onkeyup="searchProducts()" />
   </div>
 
   <!-- Вкладки -->
   <div class="tabs">
     <div class="tab active" onclick="openTab(event, 'cars')">Автомобілі</div>
     <div class="tab" onclick="openTab(event, 'accessories')">Аксесуари</div>
   </div>
 
   <!-- Контент вкладок -->
   <div id="cars" class="tab-content active">
     <div class="container">
       <div class="product-card" onclick="showModal()">
         <img src="images/01.avif" alt="Volkswagen car 1" />
         <h2>Автомобіль 1</h2>
         <p class="price">Ціна: $25,000</p>
       </div>
       <div class="product-card" onclick="showModal()">
         <img src="images/02.jpg" alt="Volkswagen car 2" />
         <h2>Автомобіль 2</h2>
         <p class="price">Ціна: $30,000</p>
       </div>
       <div class="product-card" onclick="showModal()">
         <img src="images/03.webp" alt="Volkswagen car 3" />
         <h2>Автомобіль 3</h2>
         <p class="price">Ціна: $280,500</p>
       </div>
     </div>
   </div>
 
   <div id="accessories" class="tab-content">
     <div class="container">
       <div class="product-card" onclick="showModal()">
         <img src="images/04.jpeg" alt="Моторне мастило" />
         <h2>Моторне мастило</h2>
         <p class="price">Ціна: $50</p>
       </div>
      <div class="product-card" onclick="showModal()">
       <img src="images/04.jpeg" alt="Освітлення" />
       <h2>Освітлення</h2>
       <p class="price">Ціна: $500</p>
      </div> 
       <div class="product-card" onclick="showModal()">
         <img src="images/04.jpeg" alt="Освіжувач повітря" />
         <h2>Освіжувач повітря</h2>
         <p class="price">Ціна: $10</p>
       </div>
     </div>
   </div>
 
   <!-- Модальне вікно -->
   <div id="thankYouModal" class="modal">
     <div class="modal-content">
       <span class="close" onclick="closeModal()">&times;</span>
       <h2>Дякуємо за покупку!</h2>
       <p>Ваше замовлення успішно оформлено. Очікуйте на доставку!</p>
     </div>
   </div>
 
   <script>
     function showModal() {
       document.getElementById("thankYouModal").style.display = "block";
     }
 
     function closeModal() {
       document.getElementById("thankYouModal").style.display = "none";
     }
 
     window.onclick = function (event) {
       var modal = document.getElementById("thankYouModal");
       if (event.target == modal) {
         modal.style.display = "none";
       }
     };
 
     function openTab(evt, tabId) {
       const tabs = document.querySelectorAll(".tab");
       const contents = document.querySelectorAll(".tab-content");
 
       tabs.forEach((t) => t.classList.remove("active"));
       contents.forEach((c) => c.classList.remove("active"));
 
       evt.currentTarget.classList.add("active");
       document.getElementById(tabId).classList.add("active");
     }
 
     function searchProducts() {
       const input = document.getElementById("searchInput").value.toLowerCase();
       const cards = document.querySelectorAll(".product-card");
 
       cards.forEach(card => {
         const title = card.querySelector("h2").innerText.toLowerCase();
         card.style.display = title.includes(input) ? "block" : "none";
       });
     }
   </script>
 </body>
 </html>
