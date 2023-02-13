<script>
  import { iconPaths } from "../../assets/IconPaths";

  export let icon;
  export let width = "1rem";
  export let height = "1rem";
  export let focusable = false;

  const iconPath = iconPaths[icon];
</script>

<svg class={$$props.class} {focusable} {width} {height} viewBox="0 0 32 32"
  >{@html icon}</svg
>

<style>
  svg {
    vertical-align: middle;
  }
</style>
