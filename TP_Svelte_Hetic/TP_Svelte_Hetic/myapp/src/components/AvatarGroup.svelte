<script>
  export let group = false;
  export let orientation = "row"; /*column*/
</script>

<div class:avatar-group={group} style="flex-direction: {orientation}">
  <slot></slot>
</div>

<style>
  .avatar-group {
    /* display: flex; */
    align-items: center;
  }

  :global(body) {
    background-color: white;
  }
  
  div {
    display: flex;
    height: 65px;
    width: 100%; 
  }

  :global(.avatar-group .avatar-wrapper) {
    margin: 0px;
    margin-inline-start: -0.75rem;

  }
</style>
