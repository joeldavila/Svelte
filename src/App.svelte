<script>
  import Color from "./Color.svelte";
  import Alpha from "./Alpha.svelte";
  let redValue = 0;
  let greenValue = 0;
  let blueValue = 0;
  let alpha = 1;
  let display = "display"
  let setDisplay = function(){
    if (display == "flex"){
      return

    }else{
      return "none"
    }

  }

  function RGBAToHexA(r, g, b) {
    r = r.toString(16);
    g = g.toString(16);
    b = b.toString(16);

    if (r.length == 1) r = "0" + r;
    if (g.length == 1) g = "0" + g;
    if (b.length == 1) b = "0" + b;

    return "#" + r + g + b;
  }
</script>

<div class="container">
  <h1>Color Designer</h1>
  <div class="container">
    <Color color="Red" bind:value={redValue} />
    <Color color="Green" bind:value={greenValue} />
    <Color color="Blue" bind:value={blueValue} />
    
  </div>
  <div style="display:{display}" class="container">
    <Alpha color="Alpha" bind:value={alpha} />
  </div>

  <div
    class="box"
    style="background-color: rgba({redValue},{greenValue},{blueValue},{alpha});"
  />
  <div />
  <p>
    rgba({redValue},{greenValue},{blueValue},{alpha})
  </p>
  <span>Use Alpha value only for RGBA, for Hex# move the Alpha value to 1</span>

  <p>
    Hex Color:{RGBAToHexA(redValue, greenValue, blueValue)}
  </p>
</div>

<style>
  * {
    font-family: Verdana, Geneva, Tahoma, sans-serif;
  }
  .box {
    margin-top: 20px;
    min-width: 70%;
    max-width: 80%;

    height: 200px;
    display: flex;
    justify-content: center;
    border-radius: 20px;
  }
  p {
    color: lightslategray;
    font-size: 35px;
  }

  .container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 90%;
    margin: 0 auto;
  }

  span {
    font-size: 10px;
    position: relative;
    top: -30px;
    color: red;
  }
</style>
