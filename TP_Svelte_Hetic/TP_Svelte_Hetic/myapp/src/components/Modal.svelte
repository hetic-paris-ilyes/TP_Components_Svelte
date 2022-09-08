<script>
  import Button from "./Button.svelte";
  export let title = "Here i am";
  export let text =
    "Thank to pop me out of that button, but now i'm done so you can close this window.";
  export let size = 25;
  export let color = "black";
  export let ftfam = 'system-ui, -apple-system, system-ui, "Helvetica Neue"';

  export let psize = 25;
  export let pcolor = "black";
  export let pftfam = 'system-ui, -apple-system, system-ui, "Helvetica Neue"';
</script>

<Button text="Let me Pop up" url="#popup1" />
<div id="popup1" class="overlay">
  <div class="popup">
    <h2 style="font-size: {size}px;  color:{color}; font-family:{ftfam};">
      {title}
      <slot name="title" />
    </h2>
    <a class="close" href="#">&times;</a>
    <div
      class="content"
      style="font-size: {psize}px;  color:{pcolor}; font-family:{pftfam};"
    >
      {text}
    </div>

    <slot name="image" />
    <slot />
  </div>
</div>

<style>
  .overlay {
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    background: rgba(0, 0, 0, 0.7);
    transition: opacity 500ms;
    visibility: hidden;
    opacity: 0;
  }
  .overlay:target {
    visibility: visible;
    opacity: 1;
  }

  .popup {
    margin: 70px auto;
    padding: 20px;
    background: #fff;
    border-radius: 5px;
    width: 30%;
    position: relative;
    transition: all 5s ease-in-out;
  }

  .popup h2 {
    margin-top: 0;
  }
  .popup .close {
    position: absolute;
    top: 20px;
    right: 30px;
    transition: all 200ms;
    font-size: 30px;
    font-weight: bold;
    text-decoration: none;
    color: #333;
  }
  .popup .close:hover {
    color: #319795;
  }
  .popup .content {
    max-height: 30%;
    overflow: auto;
  }

  @media screen and (max-width: 700px) {
    .popup {
      width: 70%;
    }
  }
  :global(.popup img) {
    width: 100%;
  }
</style>
