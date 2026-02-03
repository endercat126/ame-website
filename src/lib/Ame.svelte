<img id="ame" src="/src/lib/assets/ame.webp" alt="ame"
onclick={() => {
new Audio("src/lib/assets/meow.wav").play()
}}/>
<img src="/src/lib/assets/petpet.gif" alt="petpet" id="cursor"
     style="top: {mousePos.y}px; left: {mousePos.x}px"/>

<script lang="ts">
    let mousePos = $state({ x: 0, y: 0 })
</script>

<svelte:window on:mousemove={(e) => {
    mousePos.x = e.clientX
    mousePos.y = e.clientY
}}/>

<style lang="scss">
    #ame {
      width: 8rem;
      user-select: none;
      -webkit-user-drag: none;
      cursor: none;
      animation: bounce 0.4s cubic-bezier(0.455, 0.030, 0.515, 0.955) infinite alternate both;
    }

    #cursor {
      position: fixed;
      margin: -2rem;
      transform: translate(-50%, -50%);
      scale: 0.4;
      display: none;
      pointer-events: none;
    }

    @keyframes bounce {
      0% {
        transform: scale(0.95);
        transform-origin: 50% 100%;
      }
      100% {
        transform: scale(1);
        transform-origin: 50% 100%;
      }
    }

    #ame:hover + #cursor {
      display: block;
    }
</style>