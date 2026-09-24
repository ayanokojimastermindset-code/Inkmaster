<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>InkEmpire — Discover & Shop</title>
  <meta name="description" content="InkEmpire - Discover trending ideas, products and inspiration.">

  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: Arial, Helvetica, sans-serif;
      background: #f7f7f7;
      color: #222;
    }

    /* HEADER */
    header {
      position: sticky;
      top: 0;
      z-index: 1000;
      background: white;
      border-bottom: 1px solid #eee;
      padding: 12px 20px;
    }

    .nav {
      max-width: 1400px;
      margin: auto;
      display: flex;
      align-items: center;
      gap: 18px;
    }

    .logo {
      font-size: 27px;
      font-weight: 900;
      color: #d60023;
      white-space: nowrap;
    }

    .search {
      flex: 1;
      position: relative;
    }

    .search input {
      width: 100%;
      padding: 14px 45px 14px 20px;
      border: none;
      outline: none;
      border-radius: 30px;
      background: #eee;
      font-size: 16px;
    }

    .search button {
      position: absolute;
      right: 10px;
      top: 8px;
      border: none;
      background: none;
      font-size: 20px;
      cursor: pointer;
    }

    .nav button {
      border: none;
      background: none;
      font-size: 15px;
      font-weight: bold;
      cursor: pointer;
    }

    .join {
      background: #111 !important;
      color: white !important;
      padding: 12px 18px;
      border-radius: 25px;
    }

    /* HERO */
    .hero {
      max-width: 1400px;
      margin: 30px auto;
      padding: 35px 25px;
      text-align: center;
    }

    .hero h1 {
      font-size: 42px;
      margin-bottom: 12px;
    }

    .hero p {
      color: #666;
      font-size: 18px;
    }

    /* CATEGORIES */
    .categories {
      max-width: 1400px;
      margin: 0 auto 25px;
      padding: 0 20px;
      display: flex;
      gap: 10px;
      overflow-x: auto;
    }

    .category {
      background: white;
      padding: 12px 20px;
      border-radius: 25px;
      border: 1px solid #ddd;
      white-space: nowrap;
      cursor: pointer;
    }

    .category:hover {
      background: #111;
      color: white;
    }

    /* PINTEREST STYLE GRID */
    .grid {
      max-width: 1400px;
      margin: auto;
      padding: 0 20px 50px;
      columns: 5 220px;
      column-gap: 18px;
    }

    .card {
      display: inline-block;
      width: 100%;
      margin-bottom: 18px;
      background: white;
      border-radius: 18px;
      overflow: hidden;
      break-inside: avoid;
      box-shadow: 0 2px 8px rgba(0, 0, 0, 0.08);
      transition: 0.2s;
    }

    .card:hover {
      transform: translateY(-3px);
      box-shadow: 0 7px 20px rgba(0, 0, 0, 0.14);
    }

    .card img {
      width: 100%;
      display: block;
    }

    .card-content {
      padding: 13px;
    }

    .card h3 {
      font-size: 17px;
      margin-bottom: 7px;
    }

    .card p {
      color: #777;
      font-size: 13px;
      margin-bottom: 12px;
    }

    .actions {
      display: flex;
      gap: 8px;
    }

    .save,
    .shop {
      border: none;
      padding: 9px 12px;
      border-radius: 20px;
      cursor: pointer;
      font-weight: bold;
    }

    .save {
      background: #eee;
    }

    .shop {
      background: #d60023;
      color: white;
      text-decoration: none;
    }

    /* FOOTER */
    footer {
      background: #111;
      color: white;
      padding: 45px 20px;
      text-align: center;
    }

    footer h2 {
      margin-bottom: 10px;
    }

    footer p {
      color: #bbb;
      max-width: 600px;
      margin: 8px auto;
    }

    /* WHATSAPP BUTTON */
    .whatsapp-button {
      position: fixed;
      right: 20px;
      bottom: 20px;
      background: #25D366;
      color: white;
      padding: 14px 20px;
      border-radius: 30px;
      text-decoration: none;
      font-weight: bold;
      z-index: 9999;
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
      transition: 0.2s;
    }

    .whatsapp-button:hover {
      transform: scale(1.05);
    }

    /* MOBILE */
    @media (max-width: 700px) {
      .nav {
        flex-wrap: wrap;
      }

      .logo {
        font-size: 23px;
      }

      .search {
        order: 3;
        flex-basis: 100%;
      }

      .hero h1 {
        font-size: 32px;
      }

      .grid {
        columns: 2 150px;
        padding: 0 10px 30px;
        column-gap: 10px;
      }

      .card {
        margin-bottom: 10px;
      }

      .whatsapp-button {
        right: 15px;
        bottom: 15px;
        padding: 12px 16px;
      }
    }
  </style>
</head>

<body>

  <!-- HEADER -->
  <header>
    <div class="nav">

      <div class="logo">InkEmpire</div>

      <div class="search">
        <input
          id="searchInput"
          type="text"
          placeholder="Search ideas, products & inspiration..."
          onkeyup="searchCards()"
        >
        <button type="button">🔍</button>
      </div>

      <button type="button" onclick="showHome()">Home</button>

      <button type="button" onclick="showSaved()">Saved</button>

      <button type="button" class="join" onclick="joinNow()">
        Join
      </button>

    </div>
  </header>


  <!-- HERO -->
  <section class="hero">

    <h1>Discover Your Next Idea</h1>

    <p>
      Inspiration, trending products and amazing discoveries — all in one place.
    </p>

  </section>


  <!-- CATEGORIES -->
  <div class="categories">

    <div class="category" onclick="filterCards('all')">
      ✨ All
    </div>

    <div class="category" onclick="filterCards('fashion')">
      👕 Fashion
    </div>

    <div class="category" onclick="filterCards('tech')">
      💻 Tech
    </div>

    <div class="category" onclick="filterCards('home')">
      🏠 Home
    </div>

    <div class="category" onclick="filterCards('gaming')">
      🎮 Gaming
    </div>

    <div class="category" onclick="filterCards('fitness')">
      🏋️ Fitness
    </div>

    <div class="category" onclick="filterCards('lifestyle')">
      ✨ Lifestyle
    </div>

  </div>


  <!-- PIN CARDS -->
  <main class="grid" id="grid">

    <!-- CARD 1 -->
    <article class="card" data-category="tech" data-title="Gaming Setup">

      <img
        src="https://images.unsplash.com/photo-1593305841991-05c297ba4575?auto=format&fit=crop&w=700&q=80"
        alt="Gaming setup"
      >

      <div class="card-content">

        <h3>Ultimate Gaming Setup</h3>

        <p>Upgrade your gaming space.</p>

        <div class="actions">

          <button class="save" type="button" onclick="saveCard(this)">
            ♡ Save
          </button>

          <a
            class="shop"
            href="YOUR_AFFILIATE_LINK"
            target="_blank"
            rel="nofollow sponsored noopener"
          >
            Shop
          </a>

        </div>
      </div>
    </article>


    <!-- CARD 2 -->
    <article class="card" data-category="home" data-title="Modern Room">

      <img
        src="https://images.unsplash.com/photo-1616486338812-3dadae4b4ace?auto=format&fit=crop&w=700&q=80"
        alt="Modern room"
      >

      <div class="card-content">

        <h3>Modern Room Ideas</h3>

        <p>Make your room look amazing.</p>

        <div class="actions">

          <button class="save" type="button" onclick="saveCard(this)">
            ♡ Save
          </button>

          <a
            class="shop"
            href="YOUR_AFFILIATE_LINK"
            target="_blank"
            rel="nofollow sponsored noopener"
          >
            Shop
          </a>

        </div>
      </div>
    </article>


    <!-- CARD 3 -->
    <article class="card" data-category="fashion" data-title="Streetwear Fashion">

      <img
        src="https://images.unsplash.com/photo-1529139574466-a303027c1d8b?auto=format&fit=crop&w=700&q=80"
        alt="Streetwear fashion"
      >

      <div class="card-content">

        <h3>Streetwear Fashion</h3>

        <p>Trending everyday fashion ideas.</p>

        <div class="actions">

          <button class="save" type="button" onclick="saveCard(this)">
            ♡ Save
          </button>

          <a
            class="shop"
            href="YOUR_AFFILIATE_LINK"
            target="_blank"
            rel="nofollow sponsored noopener"
          >
            Shop
          </a>

        </div>
      </div>
    </article>


    <!-- CARD 4 -->
    <article class="card" data-category="fitness" data-title="Fitness">

      <img
        src="https://images.unsplash.com/photo-1517836357463-d25dfeac3438?auto=format&fit=crop&w=700&q=80"
        alt="Fitness"
      >

      <div class="card-content">

        <h3>Fitness Inspiration</h3>

        <p>Build a better workout space.</p>

        <div class="actions">

          <button class="save" type="button" onclick="saveCard(this)">
            ♡ Save
          </button>

          <a
            class="shop"
            href="YOUR_AFFILIATE_LINK"
            target="_blank"
            rel="nofollow sponsored noopener"
          >
            Shop
          </a>

        </div>
      </div>
    </article>


    <!-- CARD 5 -->
    <article class="card" data-category="gaming" data-title="Gaming Chair">

      <img
        src="https://images.unsplash.com/photo-1598550476439-6847785fcea6?auto=format&fit=crop&w=700&q=80"
        alt="Gaming chair"
      >

      <div class="card-content">

        <h3>Gaming Chair Setup</h3>

        <p>Ideas for your gaming station.</p>

        <div class="actions">

          <button class="save" type="button" onclick="saveCard(this)">
            ♡ Save
          </button>

          <a
            class="shop"
            href="YOUR_AFFILIATE_LINK"
            target="_blank"
            rel="nofollow sponsored noopener"
          >
            Shop
          </a>

        </div>
      </div>
    </article>


    <!-- CARD 6 -->
    <article class="card" data-category="lifestyle" data-title="Travel">

      <img
        src="https://images.unsplash.com/photo-1500534623283-312aade485b7?auto=format&fit=crop&w=700&q=80"
        alt="Travel"
      >

      <div class="card-content">

        <h3>Travel Inspiration</h3>

        <p>Discover beautiful destinations.</p>

        <div class="actions">

          <button class="save" type="button" onclick="saveCard(this)">
            ♡ Save
          </button>

          <a
            class="shop"
            href="YOUR_AFFILIATE_LINK"
            target="_blank"
            rel="nofollow sponsored noopener"
          >
            Explore
          </a>

        </div>
      </div>
    </article>


    <!-- CARD 7 -->
    <article class="card" data-category="tech" data-title="Laptop Desk">

      <img
        src="https://images.unsplash.com/photo-1496181133206-80ce9b88a853?auto=format&fit=crop&w=700&q=80"
        alt="Laptop desk setup"
      >

      <div class="card-content">

        <h3>Best Desk Setup</h3>

        <p>Clean and productive workspace.</p>

        <div class="actions">

          <button class="save" type="button" onclick="saveCard(this)">
            ♡ Save
          </button>

          <a
            class="shop"
            href="YOUR_AFFILIATE_LINK"
            target="_blank"
            rel="nofollow sponsored noopener"
          >
            Shop
          </a>

        </div>
      </div>
    </article>


    <!-- CARD 8 -->
    <article class="card" data-category="home" data-title="Luxury Interior">

      <img
        src="https://images.unsplash.com/photo-1600607687920-4e2a09cf159d?auto=format&fit=crop&w=700&q=80"
        alt="Luxury interior"
      >

      <div class="card-content">

        <h3>Luxury Interior Ideas</h3>

        <p>Beautiful home inspiration.</p>

        <div class="actions">

          <button class="save" type="button" onclick="saveCard(this)">
            ♡ Save
          </button>

          <a
            class="shop"
            href="YOUR_AFFILIATE_LINK"
            target="_blank"
            rel="nofollow sponsored noopener"
          >
            Shop
          </a>

        </div>
      </div>
    </article>

  </main>


  <!-- FOOTER -->
  <footer>

    <h2>InkEmpire</h2>

    <p>
      Discover ideas. Save inspiration. Find products.
    </p>

    <p>
      © 2026 InkEmpire
    </p>

  </footer>


  <!-- WHATSAPP BUTTON -->
  <a
    class="whatsapp-button"
    href="https://wa.me/919835226088"
    target="_blank"
    rel="noopener"
    aria-label="Chat with InkEmpire on WhatsApp"
  >
    💬 WhatsApp
  </a>


  <!-- JAVASCRIPT -->
  <script>

    // SEARCH
    function searchCards() {

      const input =
        document.getElementById("searchInput").value.toLowerCase().trim();

      const cards =
        document.querySelectorAll(".card");

      cards.forEach(function(card) {

        const title =
          card.dataset.title.toLowerCase();

        const category =
          card.dataset.category.toLowerCase();

        if (
          title.includes(input) ||
          category.includes(input)
        ) {
          card.style.display = "inline-block";
        } else {
          card.style.display = "none";
        }

      });

    }


    // CATEGORY FILTER
    function filterCards(category) {

      const cards =
        document.querySelectorAll(".card");

      document.getElementById("searchInput").value = "";

      cards.forEach(function(card) {

        if (
          category === "all" ||
          card.dataset.category === category
        ) {
          card.style.display = "inline-block";
        } else {
          card.style.display = "none";
        }

      });

    }


    // SAVE BUTTON
    function saveCard(button) {

      if (button.innerText.includes("♡")) {

        button.innerText = "♥ Saved";
        button.style.background = "#ffd9df";

      } else {

        button.innerText = "♡ Save";
        button.style.background = "#eee";

      }

    }


    // HOME
    function showHome() {

      document.getElementById("searchInput").value = "";

      filterCards("all");

      window.scrollTo({
        top: 0,
        behavior: "smooth"
      });

    }


    // JOIN
    function joinNow() {

      alert(
        "Welcome to InkEmpire! Sign-up functionality can be connected later."
      );

    }


    // SAVED
    function showSaved() {

      alert(
        "Saved-pins system is ready for database integration."
      );

    }

  </script>

</body>
</html>
