<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My Apology</title>
  <style>
    body, html {
      margin: 0;
      padding: 0;
      font-family: Arial, sans-serif;
      height: 100vh;
      width: 100vw;
      display: flex;
      justify-content: center;
      align-items: center;
      overflow: hidden;
    }

    #container, #container2, #container3, #questionPage {
      width: 100vw;
      height: 100vh;
      display: none;
      text-align: center;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      position: absolute;
    }

    img {
      width: 250px;
      height: auto;
      opacity: 0;
      transition: opacity 2s ease;
    }

    h1, h2 {
      opacity: 0;
      transition: opacity 2s ease;
      color: white;
    }

    .option-btn {
      padding: 10px 20px;
      margin: 10px;
      font-size: 16px;
      color: white;
      background-color: #333;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      opacity: 0;
      transition: opacity 1s ease;
    }

    /* Celebration screen styles */
    #celebration {
      background-color: yellow;
      display: none;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      color: #ff4081;
      font-size: 50px;
      animation: party 1s ease-out forwards;
    }

    @keyframes party {
      0% { transform: scale(0); }
      100% { transform: scale(1); }
    }
  </style>
</head>
<body>

  <!-- First Page: Apology with Sage Green background -->
  <div id="container" style="background-color: #a0c4a4;">
    <h1 id="header1">My deepest apologies</h1>
    <img id="image1" src="https://i.pinimg.com/474x/14/3c/7f/143c7fa7d2630f11652901468fe0ed6e.jpg" alt="Apology Image">
  </div>

  <!-- Second Page: I Truly Apologize with Yellow background -->
  <div id="container2" style="background-color: #ffeb3b;">
    <h2 id="header2">I truly apologize</h2>
    <img id="image2" src="https://i.pinimg.com/474x/59/da/cc/59dacc18f68ef57500cac6d70cf5a874.jpg" alt="Second Image">
  </div>

  <!-- Third Page: Actually Everytime I See You with Black background -->
  <div id="container3" style="background-color: black;">
    <h2 id="header3">ACTUALLY every time I see you</h2>
    <img id="image3" src="https://i.pinimg.com/736x/8d/c8/6f/8dc86f723d091565d49653efebc1af03.jpg" alt="Third Image">
  </div>

  <!-- Fourth Page: Pani Puri Question -->
  <div id="questionPage" style="background-color: #ffeb3b;">
    <h1 id="header4">Would you indulge in some pani puri with me?</h1>
    <img id="image4" src="https://i.pinimg.com/474x/e5/ac/7f/e5ac7fb5e275457248a441da9d6d815f.jpg" alt="Pani Puri Image">
    <div>
      <button class="option-btn" onclick="showCelebration()">Yes</button>
      <button class="option-btn" onclick="showCelebration()">Hell yeah</button>
    </div>
  </div>

  <!-- Celebration Screen -->
  <div id="celebration">
    <img src="https://i.pinimg.com/474x/59/92/3b/59923b8264153d50a7a26a94f3191eb8.jpg" alt="Celebration Image">
    <p>🎉 🎉 🎉 Yay! 🎉 🎉 🎉</p>
  </div>

  <script>
    // Function to start the first page transition
    window.onload = function() {
      // Fade in the first page (Apology)
      document.getElementById("container").style.display = "flex";
      setTimeout(() => {
        document.getElementById("header1").style.opacity = 1;
        document.getElementById("image1").style.opacity = 1;

        // Fade out first page and show the second page
        setTimeout(() => {
          document.getElementById("header1").style.opacity = 0;
          document.getElementById("image1").style.opacity = 0;
          setTimeout(() => {
            document.getElementById("container2").style.display = "flex";
            document.getElementById("header2").style.opacity = 1;
            document.getElementById("image2").style.opacity = 1;
          }, 1000);
        }, 4000); // Keep the first page for 4 seconds
      }, 1000); // Fade in the first elements after 1 second

      // Fade out second page and show the third page
      setTimeout(() => {
        document.getElementById("container2").style.display = "none";
        document.getElementById("container3").style.display = "flex";
        document.getElementById("header3").style.opacity = 1;
        document.getElementById("image3").style.opacity = 1;
      }, 8000); // Keep second page for 4 seconds

      // Fade out third page and show the pani puri question page
      setTimeout(() => {
        document.getElementById("container3").style.display = "none";
        document.getElementById("questionPage").style.display = "flex";
        document.getElementById("header4").style.opacity = 1;
        document.getElementById("image4").style.opacity = 1;

        // Fade in the buttons
        setTimeout(() => {
          const buttons = document.querySelectorAll(".option-btn");
          buttons.forEach(button => button.style.opacity = 1);
        }, 1000);
      }, 12000); // Keep third page for 4 seconds
    };

    // Function to show the celebration screen when a button is clicked
    function showCelebration() {
      document.getElementById("questionPage").style.display = "none";
      document.getElementById("celebration").style.display = "flex";
    }
  </script>

</body>
</html>

