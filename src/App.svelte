<script>
  import audio from "./asset/peter.mp3"
  let cat = "https://media.tenor.com/zGm5acSjHCIAAAAC/cat-begging.gif";
  let noButton;
  let video, response;
  let count = 0;
  let height, width;
  

  function changePos() {
    count += 1;
    noButton.style.position = "absolute";
    noButton.style.top = Math.floor(Math.random() * height-50) + "px";
    noButton.style.left = Math.floor(Math.random() * width-50) + "px";
    
  }

  function yesButton() {
    console.log("I love you .............. ><");
    video.style.display = "block"
    video.play()
  }

  function responsehandler(){
    response.style.display = "block"
  }
  
</script>

<svelte:window bind:innerHeight={height} bind:innerWidth={width} />

<main>
  <div>
    <div class="main-div">
      <h1>Will You Date Me ?</h1>
      <img src={cat} alt="cat" />
      <div class="container">
        <button id="yes" on:click={yesButton}>Yes</button>
        <button id="no" bind:this={noButton} on:focus on:mouseover={changePos}
          >No</button
        >
      </div>
      <video on:ended={responsehandler} bind:this={video} src="https://socialfinds.xyz/wp-content/uploads/2021/06/Oh-My-God-Wow.mp4?_=1" width="350px" style="display: none;">
        <track kind="captions">
      </video>
    </div>
    <div id="response" bind:this={response}>
      <h1>I love you...</h1>
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

  #response{
    display: none;
    position: absolute;
    top: 30%;
    left: 30%;
    background-color: antiquewhite;
    padding: 20px;
    border-radius: 30px;
    animation-name: res  ;
    animation-duration: 3s;
  }

  @keyframes res{
    from{
      opacity: 0;
    }
    to{
      opacity: 1;
      transform: rotate(720deg);
    }
  }

</style>
