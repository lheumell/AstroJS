<script>
  export let title;
  export let url;
  export let alt;
  // export interface Props {
  //   title: string;
  //   url: string;
  //   alt: string;
  //   media_type: string;
  // }

  // const { title, url, alt, media_type } = Astro.props;
</script>

<div>
  <slot />
  <figure class="fig">
    <img class="image" src={url} {alt} />
    <figcaption>{title}</figcaption>
  </figure>
</div>

<style>
  .image {
    width: 150px;
    border-radius: 20px;
  }
  .fig {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
</style>
