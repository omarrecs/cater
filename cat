<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Romantic Date Invite</title>
    <style>
      body {
        margin: 0;
        overflow: hidden;
        background-color: #fbd4e0;
        font-family: "Arial", sans-serif;
        color: #5a3a3a;
        text-align: center;
      }

      #sparkles-container,
      #hearts-container {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        pointer-events: none;
        overflow: hidden;
      }

      .star {
        position: absolute;
        background: rgb(255, 255, 255);
        clip-path: polygon(
          50% 0%,
          61% 35%,
          98% 35%,
          68% 57%,
          79% 91%,
          50% 70%,
          21% 91%,
          32% 57%,
          2% 35%,
          39% 35%
        );
        opacity: 0.7;
        animation: twinkle 2s ease-in-out forwards;
      }

      @keyframes twinkle {
        0% {
          opacity: 0;
          transform: scale(0.5);
        }
        25% {
          opacity: 0.5;
          transform: scale(1);
        }
        50% {
          opacity: 0.8;
          transform: scale(1.2);
        }
        75% {
          opacity: 0.5;
          transform: scale(1);
        }
        100% {
          opacity: 0;
          transform: scale(0.5);
        }
      }

      .heart {
        position: absolute;
        width: 20px;
        height: 20px;
        background: red;
        transform: rotate(-45deg);
        opacity: 0.8;
      }
      .heart::before,
      .heart::after {
        content: "";
        position: absolute;
        width: 20px;
        height: 20px;
        background: red;
        border-radius: 50%;
      }
      .heart::before {
        top: -10px;
        left: 0;
      }
      .heart::after {
        left: 10px;
        top: 0;
      }

      .center {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        z-index: 10;
        width: 90%;
      }

      button {
        background-color: #ffb6c1;
        border: none;
        padding: 10px 20px;
        margin: 10px;
        border-radius: 8px;
        font-size: 18px;
        cursor: pointer;
        transition: transform 0.2s ease;
      }

      button:hover {
        transform: scale(1.1);
        background-color: #ff99aa;
      }

      .shake {
        animation: shake 0.3s ease-in-out infinite alternate;
      }
      @keyframes shake {
        from {
          transform: translateX(-3px);
        }
        to {
          transform: translateX(3px);
        }
      }

      #menu {
        display: none;
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 20px;
        width: 80%;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        z-index: 10;
        text-align: center;
        transition: filter 0.4s ease;
      }

      .blurred {
        filter: blur(6px);
      }

      .menu-item {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        margin: 0;
        padding: 20px;
        background: rgba(255, 182, 193, 0.8);
        border-radius: 12px;
        cursor: pointer;
        transition: transform 0.3s ease;
        min-height: 100px;
        position: relative;
      }
      .menu-item:hover {
        transform: scale(1.1);
      }

      .fav-icon {
        position: absolute;
        top: 8px;
        right: 8px;
        font-size: 20px;
        cursor: pointer;
        user-select: none;
      }
      .fav-icon.filled {
        color: red;
      }

      #description {
        display: none;
        position: fixed;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%) scale(0.5);
        background: white;
        padding: 20px;
        border-radius: 12px;
        z-index: 20;
        opacity: 0;
        transition: all 0.4s ease;
        box-shadow: 0 0 20px rgba(0, 0, 0, 0.3);
        max-width: 300px;
      }
      #description.show {
        opacity: 1;
        transform: translate(-50%, -50%) scale(1);
      }

      #overlay {
        display: none;
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        z-index: 15;
        background: rgba(0, 0, 0, 0.2);
      }

      .booking-message {
        margin-top: 10px;
        font-size: 14px;
        color: #e75480;
        font-style: italic;
      }

      /* New "fine 🙄" popup */
      #finePopup {
        display: none;
        background: #fff0f5;
        color: #5a3a3a;
        border-radius: 12px;
        padding: 15px;
        margin-top: 15px;
        cursor: pointer;
        user-select: none;
        font-weight: bold;
      }

      /* "thanks luv" modal */
      #thanksOverlay {
        display: none;
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: rgba(0, 0, 0, 0.6);
        z-index: 50;

        justify-content: center;
        align-items: center;

        /* fade-in */
        animation: fadeInOverlay 0.5s ease forwards;
      }

      #thanksPopup {
        background: white;
        padding: 15px 25px;
        border-radius: 15px;
        box-shadow: 0 0 25px rgba(0, 0, 0, 0.25);
        font-size: 16px;
        color: #e75480;
        user-select: none;
        position: relative;
        opacity: 0;
        transform: translateY(10px);
        animation: fadeInPopup 0.5s ease forwards;
        transition: all 0.3s ease;
      }

      #thanksPopup button {
        margin-top: 15px;
        padding: 6px 14px;
        background: #e75480;
        border: none;
        color: white;
        border-radius: 8px;
        cursor: pointer;
        font-size: 14px;
      }

      @keyframes fadeInOverlay {
        from {
          opacity: 0;
        }
        to {
          opacity: 1;
        }
      }
      @keyframes fadeInPopup {
        from {
          opacity: 0;
          transform: translateY(10px);
        }
        to {
          opacity: 1;
          transform: translateY(0);
        }
      }
    </style>
  </head>
  <body>
    <div id="sparkles-container"></div>
    <div id="hearts-container"></div>

    <div id="page1" class="center">
      <h1>Wanna go on an online date? ❤️</h1>
      <button onclick="yesClicked()">Yes</button>
      <button onclick="noClicked()">No</button>
    </div>

    <div id="menu"></div>

    <div id="overlay" onclick="closeDescription()"></div>
    <div id="description"></div>

    <!-- New fine 🙄 popup -->
    <div id="finePopup" onclick="showThanks()">fine 🙄</div>

    <!-- New thanks luv modal -->
    <div id="thanksOverlay" onclick="hideThanks()">
      <div id="thanksPopup" onclick="event.stopPropagation()">
        thanks luv
        <br />
        <button onclick="hideThanks()">Close</button>
      </div>
    </div>

    <script>
      const dateIdeas = [
        {
          title: "Netflix Party",
          text: "We watch the same movie, snack together, and chat!",
        },
        {
          title: "Online Cooking",
          text: "We cook the same meal together over video call!",
        },
        {
          title: "Stargazing",
          text: "We find a star map app and watch the night sky together.",
        },
        {
          title: "Online Games",
          text: "Fun multiplayer games to laugh and compete.",
        },
        {
          title: "Digital Art Date",
          text: "We draw each other or something silly in a shared canvas.",
        },
        {
          title: "Photo Challenge",
          text: "We pick a theme and send cute pics to each other.",
        },
        {
          title: "Placeholder 1",
          text: "This is placeholder text 1.",
        },
        {
          title: "Placeholder 2",
          text: "This is placeholder text 2.",
        },
        {
          title: "Placeholder 3",
          text: "This is placeholder text 3.",
        },
      ];

      let favorites = JSON.parse(localStorage.getItem("favorites")) || {};

      function createMenu() {
        const menu = document.getElementById("menu");
        menu.innerHTML = "";
        dateIdeas.forEach((idea) => {
          const item = document.createElement("div");
          item.className = "menu-item";
          item.onclick = () => showDescription(idea.title, idea.text);

          const favIcon = document.createElement("span");
          favIcon.className =
            "fav-icon" + (favorites[idea.title] ? " filled" : "");
          favIcon.innerHTML = favorites[idea.title] ? "❤️" : "🤍";
          favIcon.onclick = (e) => {
            e.stopPropagation();
            toggleFavorite(idea.title, favIcon);
          };

          item.innerHTML = idea.title.includes(" ")
            ? idea.title.split(" ")[0]
            : idea.title;
          item.appendChild(favIcon);
          menu.appendChild(item);
        });
      }

      function toggleFavorite(title, icon) {
        favorites[title] = !favorites[title];
        localStorage.setItem("favorites", JSON.stringify(favorites));
        icon.className = "fav-icon" + (favorites[title] ? " filled" : "");
        icon.innerHTML = favorites[title] ? "❤️" : "🤍";
      }

      function createSparkles() {
        const container = document.getElementById("sparkles-container");
        setInterval(() => {
          const star = document.createElement("div");
          star.classList.add("star");
          const size = Math.random() * 6 + 4 + "px";
          star.style.width = size;
          star.style.height = size;
          star.style.left = Math.random() * 100 + "%";
          star.style.top = Math.random() * 100 + "%";
          container.appendChild(star);
          setTimeout(() => star.remove(), 2500);
        }, 150);
      }

      function createHearts() {
        const container = document.getElementById("hearts-container");
        const heart = document.createElement("div");
        heart.classList.add("heart");
        heart.style.left = Math.random() * 100 + "%";
        heart.style.top = "100%";
        heart.style.transform =
          "rotate(-45deg) scale(" + (Math.random() * 0.5 + 0.5) + ")";
        container.appendChild(heart);

        let pos = 100;
        const interval = setInterval(() => {
          pos -= 1;
          heart.style.top = pos + "%";
          if (pos < -10) {
            clearInterval(interval);
            heart.remove();
          }
        }, 30);
      }

      function yesClicked() {
        setInterval(createHearts, 300);
        document.getElementById("page1").style.display = "none";
        document.getElementById("menu").style.display = "grid";
        createMenu();
      }

      function noClicked() {
        document.getElementById("page1").innerHTML = `
        <h1>fk off u have to </h1>
        <button class="shake" onclick="yesClicked()">Yes</button>
        <button class="shake" onclick="noAgain()">No</button>
      `;
      }

      function noAgain() {
        document.getElementById(
          "page1"
        ).innerHTML = `<h1>😭😭 I worked really hard on this</h1>`;
        setTimeout(() => {
          document.getElementById("page1").innerHTML = `
          <h1>Wanna go on an online date? ❤️</h1>
          <button onclick="yesClicked()">Yes</button>
          <button onclick="noClicked()">No</button>
        `;
        }, 2000);
      }

      function showDescription(title, text) {
        const menu = document.getElementById("menu");
        const desc = document.getElementById("description");
        const overlay = document.getElementById("overlay");

        menu.classList.add("blurred");
        overlay.style.display = "block";

        desc.innerHTML = `
        <h2>${title}</h2>
        <p>${text}</p>
        <button onclick="bookDate()">📅 Book Date</button>
        <div id="bookingMessage" class="booking-message" style="display:none;">
          To book a date, a snap of when and what date must be sent, be creative <3
        </div>
        <div id="finePopup" style="display:none;">fine 🙄</div>
      `;

        desc.style.display = "block";
        setTimeout(() => desc.classList.add("show"), 10);
      }

      function closeDescription() {
        const menu = document.getElementById("menu");
        const desc = document.getElementById("description");
        const overlay = document.getElementById("overlay");

        desc.classList.remove("show");
        setTimeout(() => {
          desc.style.display = "none";
          overlay.style.display = "none";
          menu.classList.remove("blurred");
          // hide fine popup too in case
          const fine = document.getElementById("finePopup");
          if (fine) fine.style.display = "none";
        }, 300);
      }

      function bookDate() {
        const bookingMsg = document.getElementById("bookingMessage");
        bookingMsg.style.display = "block";

        // Show fine popup below booking message
        const finePopup = document.getElementById("finePopup");
        finePopup.style.display = "block";
        finePopup.onclick = showThanks;
      }

      function showThanks() {
        const thanksOverlay = document.getElementById("thanksOverlay");
        thanksOverlay.style.display = "flex";
      }

      function hideThanks() {
        const thanksOverlay = document.getElementById("thanksOverlay");
        thanksOverlay.style.display = "none";
      }

      createSparkles();
    </script>
  </body>
</html>
