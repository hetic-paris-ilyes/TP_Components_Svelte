<script>
  import AvatarDefault from "../assets/avatar-default.png";

  //Params
  export let name = "";
  //   "Welcome To j KK";
  export let size = "md";
  export let src = "";
  // "https://wallup.net/wp-content/uploads/2018/10/07/458379-cat-animal-pet-cats-kitty-cute-sweet.jpg";

  export let state = "";
  
  //logic
  let initialsOutput = name.split(" ");
  let initialsT = "";

  const getInitials = () => {
    initialsOutput.forEach((initial, index) => {
      if (index > 1) {
        return;
      } else {
        initialsT += initial[0];
      }
    });
    return initialsT;
  };

  const getSize = () => {
    switch (size) {
      case "sm":
        return "15px";
      case "md":
        return "25px";
      case "lg":
        return "45px";
      default:
        return;
    }
  };

  const getState = () => {
    switch (state) {
      case "online":
        return "green";
      case "offline":
        return "gray";
      case "busy":
        return "orange";
      default:
        return;
    }
  };

  getInitials();
  getSize();
</script>

<figure
  class="avatar-wrapper"
  style="background-image: url({src}); background-size: cover; height: {getSize()}; width: {getSize()}"
>
  {#if !src && !name}
    <img
      src={AvatarDefault}
      alt="default"
      style="height: 100%; width: 100%; "
    />
  {/if}
  {#if name && !src}
    <h1 style="font-size: {getSize()}">{initialsT.toUpperCase()}</h1>
  {/if}

  {#if state}
    <div
      style="width: {getSize()}; height: {getSize()}; max-height: 20px; max-width: 20px; background-color: {getState()}; border-radius: 50%; transform: translate(120%, 120%); position: absolute; z-index: 1000; border: 3px solid white; "
    />
  {/if}
</figure>

<style>
  .avatar-wrapper {
    background-color: white;
    padding: 25px;
    border-radius: 50%;
    display: flex;
    flex-direction: row;
    flex-wrap: nowrap;
    align-content: center;
    justify-content: center;
    align-items: center;
    box-shadow: 2px 0px 5px 0em grey;
    border: 3px solid white;
  }

  .avatar-wrapper:hover {
    position: relative;
    z-index: 5000;
    transform: scale(1.2);
    /* box-shadow: 0 0 15px 5em; */
  }

  h1 {
    color: black;
  }

  /* :global(body) {
    background-color: white;
  } */
</style>
