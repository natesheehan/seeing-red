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
        background-color: #d6d6d6;
    }
    .cursor{
        background-image: url("images/cursor for website.png");
    }
</style>


<body transition:fade>
    <div class="cursor" style="height:100%;width:100%">
        <img src="images/fronk-chicken-nightmares-3-5.gif" alt="test" style="height: 38vh;position: fixed;bottom: 0;">
        <img src="images/logo.png" alt="">
    </div>


</body>