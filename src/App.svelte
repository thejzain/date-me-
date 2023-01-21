<script>
  let cat = "https://media.tenor.com/zGm5acSjHCIAAAAC/cat-begging.gif";
  let noButton;
  let count = 0;
  let height, width;
  let noAlerts = [
    "I think you pressed wrong button",
    "Why ? 😥",
    "But why ? ",
    "Are you sure ?",
  ];

  function changePos() {
    if(count>=3){
      alert(noAlerts[Math.floor(Math.random()* noAlerts.length)])
    }
    count += 1;
    noButton.style.position = "absolute";
    noButton.style.top = Math.floor(Math.random() * height) + "px";
    noButton.style.left = Math.floor(Math.random() * width) + "px";
    
  }

  function yesButton() {
    alert("I love you .............. ><");
  }
</script>

<svelte:window bind:innerHeight={height} bind:innerWidth={width} />

<main>
  <div class="main-div">
    <h1>Will You Date Me ?</h1>
    <img src={cat} alt="cat" />
    <div class="container">
      <button id="yes" on:click={yesButton}>Yes</button>
      <button id="no" bind:this={noButton} on:focus on:mouseover={changePos}
        >No</button
      >
    </div>
  </div>
</main>

<style>
  button {
    margin: 10px;
    padding: 10px;
    font-size: large;
    border-radius: 10px;
  }

  .main-div {
    display: grid;
    place-items: center;
  }

  .container {
    display: block;
    padding: 10px;
  }
  #no {
    position: absolute;
  }
</style>
