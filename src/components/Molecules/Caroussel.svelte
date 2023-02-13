<script>
  import Image from "../Atoms/Image.svelte";
  import Icon from "../Atoms/Icon.svelte";
  import { fly } from "svelte/transition";

  export let images = [];

  let currentIdx = 0;
  function next() {
    currentIdx = (currentIdx + 1) % images.length;
  }
  function previous() {
    if (currentIdx === 0) {
      currentIdx = images.length - 1;
    } else {
      currentIdx -= 1;
    }
  }
</script>

<div class="buttons flex justify-center">
  <button on:click={previous} aria-label="Previous">
    <Icon name="trash" />
  </button>
  <h2>{images[currentIdx].title}</h2>
  <button on:click={next} aria-label="Next">
    <Icon name="trash" />
  </button>
</div>
<div class="images">
  {#each images as image, idx}
    {#if idx === currentIdx}
      <div class="image-container" transition:fly={{ y: 10 }}>
        <Image
          title={image.title}
          url={image.url}
          alt={image.explanation}
          media_type={image.media_type}
        >
          <a href={`/${image.date}`}>Learn more</a>
        </Image>
      </div>
    {/if}
  {/each}
</div>

<style>
  /* .buttons {
    display: flex;
    justify-content: center;
  } */
</style>
