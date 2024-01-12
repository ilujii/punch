<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Punch Serhoe</title>
  <style>
      @media all {  
      body {
      text-align: center;
    }
    #gifContainer {
      display: none;
    }
       button {
      border-radius: 50%;
      width: 100px;
      height: 100px;
      font-size: 16px;
      background-color: red;
    }
       #instructions {
      font-size: 40px;
           color: navy;
           font-weight: bold;
      }
           
     footer {
      position: fixed;
      bottom: 0;
      width: 100%;
      background-color: #f1f1f1;
      padding: 10px;
      text-align: center;
      }
      
   }
   
  </style>
</head>
<body>

<p id="instructions">Press the button to punch Serhoe</p>
<div id="gifContainer">
  <img id="gif" src="firstframe.jpg" alt="GIF" style="width: 700px; height: 500px;">
</div>
    <button onclick="playGif()">PUNCH</button>

<p id="playCount">Your punch score: 0</p>
<p id="totalPlayCount">Total punches by Yabani fam: 0</p>
  <br> <br> 

    
    <footer>Made by X: @ilujii<span style="font-weight: bold;  color: goldenrod;" > FOR FUN.</span> No bad intentions towards anyone. </footer>
    

<script>
 
  let playCounter = 0;
  let gifPlayed = false;
let totalPlayCount = parseInt(localStorage.getItem("totalPlayCount")) || 0;
  document.getElementById('totalPlayCount').innerText = 'Total punches by Yabani fam: ' + totalPlayCount;
  // Display the first frame when the page loads
  window.onload = function() {
    const gifContainer = document.getElementById('gifContainer');
    gifContainer.style.display = 'block';
  };

  function playGif() {
   
    const gifContainer = document.getElementById('gifContainer');
    const gif = document.getElementById('gif');

    if (!gifPlayed) {
      gif.src = "serhoee.gif"; // Replace 'your-gif-url.gif' with the actual URL of your GIF
      gifContainer.style.display = 'block';

      playCounter++;
      document.getElementById('playCount').innerText = 'Your punch score: ' + playCounter;
        
totalPlayCount++;
    localStorage.setItem("totalPlayCount", totalPlayCount);
    document.getElementById('totalPlayCount').innerText = 'Total punches by Yabani fam: ' + totalPlayCount;
        
        
      // Set the duration for GIF play (1.2 seconds)
      setTimeout(() => {
        gifContainer.style.display = 'none';
        gifPlayed = false;
          gif.src = "firstframe.jpg"; // 
      gifContainer.style.display = 'block';
      }, 1200);
      
    }
  }
    
    
</script>

</body>
</html>
