<script>
    // based on: https://codepen.io/sarazond/pen/LYGbwj

</script>

<div id="background" class="relative flex-1 h-full w-full z-0">
    <div id="stars" class="stars absolute inset-0 -z-10"></div>
    <div id="stars2" class="stars absolute inset-0 -z-10"></div>
    <div id="stars3" class="stars absolute inset-0 -z-10"></div>

    <div class="flex flex-col items-center p-4 gap-4 relative z-10 w-full h-full ">
        <slot/>
    </div>
</div>

<style lang="scss">
  @use "sass:math";
  @use "sass:string";

  @function multi-box-shadow ($n) {
    $value: '#{math.random(2000)}px #{math.random(2000)}px transparent';
    @for $i from 2 through $n {
      $value: '#{$value} , #{math.random(2000)}px #{math.random(2000)}px'
    }

    @return string.unquote($value);
  }

  $shadows-sml: multi-box-shadow(700);
  $shadows-med: multi-box-shadow(200);
  $shadows-big: multi-box-shadow(100);

  #background {
    height: 100%;
    background: radial-gradient(ellipse at bottom, oklch(12% 0.02 300) 0%, /* Equivalent to your dark purple */
            oklch(0% 0 0) 100%       /* Pure black */);
    overflow: hidden;
  }

  @keyframes animStar {
    from {
      transform: translateY(0px);
    }
    to {
      transform: translateY(-2000px);
    }
  }

  #stars {
    width: 1px;
    height: 1px;
    background-color: transparent;
    box-shadow: $shadows-sml;
    animation: animStar 50s linear infinite;

    &:after {
      content: " ";
      position: absolute;
      top: 2000px;
      width: 1px;
      height: 1px;
      background-color: transparent;
      box-shadow: $shadows-sml;
    }
  }

  #stars2 {
    width: 2px;
    height: 2px;
    color: #ffa3f8;
    background-color: transparent;
    box-shadow: $shadows-med;
    animation: animStar 100s linear infinite;

    &:after {
      content: " ";
      position: absolute;
      top: 2000px;
      width: 2px;
      height: 2px;
      background-color: transparent;
      box-shadow: $shadows-med;
    }
  }

  #stars3 {
    width: 3px;
    height: 3px;
    background-color: transparent;
    box-shadow: $shadows-big;
    animation: animStar 150s linear infinite;

    &:after {
      content: " ";
      position: absolute;
      top: 2000px;
      width: 3px;
      height: 3px;
      background-color: transparent;
      box-shadow: $shadows-big;
    }
  }

  .stars, .stars::after {
    color:mediumpurple;
    border-radius: 3000px;

  }
</style>