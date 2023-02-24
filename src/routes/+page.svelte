<script>
  import { fade } from "svelte/transition";
  import { browser } from "$app/environment";
  if(browser) {
      const cursor = document.querySelector('.cursor');
  
  const moveCursor = (e)=> {
    const mouseY = e.clientY;
    const mouseX = e.clientX;
     
    cursor.style.transform = `translate3d(${mouseX}px, ${mouseY}px, 0)`;
    
  }
  window.addEventListener('mousemove', moveCursor)
  
  }
  
  </script>
  <style>

      body {
        
        overflow: hidden;
        cursor:grab;
          background-color: #d6d6d6;
          background-image: url("images/logo.png");
          border-image-repeat: stretch;  
  border-image-slice: 30;
    background-size: 18vh;
      }
      .cursor{
          background-image: url("images/cursor for website.png");
      }

      .notepad{
        margin:auto;display:block;height:100vh;transform: rotate(2deg);position: relative;
      }
      .shop-link{
        margin:auto;display:block;height:90vh;transform: rotate(7deg); top: -100px;left: 33%;position:fixed
      }
      .archive-link{
        margin:auto;display:block;height:90vh;transform: rotate(3deg); top:20px;left: 33%;position:fixed;opacity:0.6
      }
      .comic-link{
        margin:auto;display:block;height:90vh;transform: rotate(9deg); top: 140px;left: 33%;position:fixed;opacity:0.6
      }
      .about-link{
        margin:auto;display:block;height:90vh;transform: rotate(-4deg); top: 260px;left: 33%;position:fixed;opacity:0.6
      }

      @media only screen and (max-width: 600px) {
        .shop-link{
        margin:auto;display:block;height:70vh;transform: rotate(7deg); top: -120px;left: 15%;position:fixed
      }
      .archive-link{
        margin:auto;display:block;height:70vh;transform: rotate(3deg); top:0px;left: 15%;position:fixed;opacity:0.6
      }
      .comic-link{
        margin:auto;display:block;height:70vh;transform: rotate(9deg); top: 120px;left: 15%;position:fixed;opacity:0.6
      }
      .about-link{
        margin:auto;display:block;height:70vh;transform: rotate(4deg); top: 240px;left: 15%;position:fixed;opacity:0.6
      }
}

  </style>
  
  
  <body transition:fade>
      <div class="cursor" style="height:100%;width:100%">
        <div style="position: relative; left: 0; top: 0;">
          <img src="images/notepad.png" alt="" class="notepad">
          <img src="images/result (1).png" alt="" class="shop-link">
          <img src="images/result (2).png" alt="" class="archive-link">
          <img src="images/result (3).png" alt="" class="comic-link">
          <img src="images/result (4).png" alt="" class="about-link">
        </div>

          <img src="images/fronk-chicken-nightmares-3-5.gif" alt="test" style="height: 38vh;position: fixed;bottom: 0;z-index:10">
      </div>
  
  
  </body>