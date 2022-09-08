<script>
  export let text = "default value";
  export let size = 25;
  export let bgcolor = "#319795";
  export let color = "#fff";
  export let ftfam = 'system-ui, -apple-system, system-ui, "Helvetica Neue"';
  export let url = "https://chakra-ui.com/docs/components/button/usage";
</script>

<a href={url}>
  <button
    style="font-size: {size}px; background-color:{bgcolor}; color:{color}; font-family:{ftfam};"
  >
    {text}
  </button>
</a>

<!-- 
    button
    link : {url}
    text: font-size px {size}/ color {color} / font-family {ftfam}/ background-color {bgcolor}
 -->
<style>
  button {
    align-items: center;
    background-clip: padding-box;
    border: 1px solid transparent;
    border-radius: 0.25rem;
    box-sizing: border-box;
    cursor: pointer;
    display: inline-flex;
    font-weight: 600;
    justify-content: center;
    line-height: 1.25;
    margin: 0;
    min-height: 3rem;
    padding: calc(0.875rem - 1px) calc(1.5rem - 1px);
    position: relative;
  }
  a {
    text-decoration: none;
  }
</style>
