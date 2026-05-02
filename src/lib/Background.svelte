<script>
    // based on: https://codepen.io/sarazond/pen/LYGbwj

</script>

<div id="background" class="relative flex-1 h-full w-full z-0">
    <div id="page-background">

        <div id="content-container" class="flex flex-col items-start p-4 gap-4 relative z-10 w-full h-full ">
            <slot/>
        </div>
    </div>

</div>

<style lang="scss">
  #background {
    margin: 0;
    background-color: black;
    min-height: 100vh;

    background-image:
        url("/assets/background2.gif");

    background-repeat: repeat;
    background-size: auto 320px;
    image-rendering: pixelated;
  }

  #page-background {
    position: absolute;
    margin: 30px;
    width: calc(100% - 60px);
    height: calc(100% - 60px);
    border: 5px dashed #FFAADA;
    background: rgba(0, 0, 0, 0.68);
    backdrop-filter: blur(3px);
  }
</style>