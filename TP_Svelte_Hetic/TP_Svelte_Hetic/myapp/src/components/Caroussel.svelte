<script>
  export let pictures = [
    "https://www.jardiner-malin.fr/wp-content/uploads/2020/04/Cerisier-du-japon-japonais-Prunus-serrulata.jpg",
    "https://jardinage.lemonde.fr/images/dossiers/historique/baobab-170659.jpg",
    "https://voyagerloin.com/wp-content/uploads/2014/07/amazing-trees-1-2.jpg",
  ];

  export let interval = 2500;
  export let size = "md";
  export let showIndex = false;

  let ref = Number(0);

  const getSize = () => {
    switch (size) {
      case "sm":
        return 250;
      case "md":
        return 350;
      case "lg":
        return 450;
      default:
        return;
    }
  };

  setInterval(() => {
    if (ref >= pictures.length - 1) {
      ref = 0;
      return;
    }
    ref += 1;
  }, interval);

  const next = () => {
    if (ref >= pictures.length - 1) {
      ref = 0;
    }

    ref += 1;
  };

  const prev = () => {
    if (ref === 0) {
      ref = pictures.length;
    }
    ref -= 1;
  };
</script>

<figure
  class="Caroussel-wrapper"
  style="background-image: url({pictures[
    ref
  ]}); background-size: cover; height: {getSize()}px; width: {getSize() +
    300}px"
>
  <div class="tools" style="height: {getSize()}px">
    <button class="tools-btn" on:click={prev}><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-chevron-left" viewBox="0 0 16 16">
        <path fill-rule="evenodd" d="M11.354 1.646a.5.5 0 0 1 0 .708L5.707 8l5.647 5.646a.5.5 0 0 1-.708.708l-6-6a.5.5 0 0 1 0-.708l6-6a.5.5 0 0 1 .708 0z"/>
      </svg></button>
    <button class="tools-btn" on:click={next}><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-chevron-right" viewBox="0 0 16 16">
        <path fill-rule="evenodd" d="M4.646 1.646a.5.5 0 0 1 .708 0l6 6a.5.5 0 0 1 0 .708l-6 6a.5.5 0 0 1-.708-.708L10.293 8 4.646 2.354a.5.5 0 0 1 0-.708z"/>
      </svg></button>
  </div>
  {#if showIndex}
    <div class="counter"><span>{ref + 1} / {pictures.length}</span></div>
  {/if}
  
  <div class="indicators-wrapper">
    {#each pictures as picture, index}
      <li
        class="indicator"
        class:highlight={ref === index}
        on:click={() => (ref = index)}
      />
    {/each}
  </div>
</figure>


<style>
  h1 {
    color: red;
  }

  .indicator {
    height: 12px !important;
    width: 12px !important;
    border-radius: 50%;
    background-color: rgb(255, 255, 255);
    margin: 15px;
    box-shadow: 0 0 5px 0px rgb(156, 156, 156);
    list-style: none;
  }

  .counter {
    max-width : 100%; 
    padding: 0px 5px; 
    text-align: right;
    transform: translate(-10px, -30px);
  }
  .highlight {
    background-color: gray;
    transform: scale(1.2);
  }

  .indicators-wrapper {
    display: flex;
    flex-direction: row;
    flex-wrap: nowrap;
    align-content: center;
    justify-content: center;
    align-items: center;
  }

  .tools {
    display: flex;
    flex-direction: row;
    flex-wrap: nowrap;
    align-content: center;
    justify-content: space-between;
    align-items: center; 
  }

  .tools-btn {
    height: max-content;
    border-radius: 50%;
    text-align: center;
    background-color: transparent; 
  }

  .Caroussel-wrapper {
    box-shadow: inset 3px 4px 55px black, 0px 0px 15px 0px rgba(0, 0, 0, 0.123);
    border-radius: 5px;
  }
</style>
