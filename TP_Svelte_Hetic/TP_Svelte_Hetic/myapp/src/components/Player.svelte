<script>

  export let pathAudio;

  let isPaused = true;
  let volume = 1;
  let isMp4 = false;
  let muted = false;
  let isPathGood = false;

  if (pathAudio.split('.')[1] === "mp4")
  {
    isMp4 = true;
    isPathGood = true;
  }
  else if (pathAudio.split('.')[1] === "mp3") 
  {
      isPathGood = true;
  }


  const toggle = () => {
    isPaused = !isPaused;
  };

  const mute = () => {
    muted = !muted;
  };

  const volumePlus = () => {
    if (volume === 1) {
      return;
    }

    volume = (volume * 10 + 1) / 10;
  };

  const volumeMinus = () => {
    if (volume === 0) {
      return;
    }

    volume = (volume * 10 - 1) / 10;
  };
</script>

{#if isPathGood}


{#if isMp4}
 <!-- svelte-ignore a11y-media-has-caption -->
 <video src={ pathAudio } bind:paused={ isPaused } bind:volume={ volume } bind:muted={ muted }/>
 <nav>
   <button class:is-hidden={ !isPaused } on:click={ toggle }>
     Play 
   </button>
   <button class={ isPaused ? 'is-hidden' : '' } on:click={ toggle }>
     Pause 
   </button>
   <button on:click={ mute }>
     {#if !muted}
     Mute
     {:else}
     Unmute
     {/if}
   </button>
   <button on:click={ volumePlus }>
     {#if volume == 1}
     Volume maximum !
     {:else}
     Volume + 
     {/if}
   </button>
   <button on:click={ volumeMinus }>
     {#if volume == 0}
     Volume minimum
     {:else}
     Volume -
     {/if}
   </button>
   <br>
   Volume = {volume * 100}
 </nav>


{:else}
    <audio controls>
      <source src={pathAudio}>
    </audio>

{/if}

<style>
  button {
    margin-top:5px;
    cursor: pointer;
    outline: 0;
    color: #fff;
    background-color: #639b96;
    border-color: #639b96;
    display: inline-block;
    font-weight: 400;
    line-height: 1.5;
    text-align: center;
    border: 1px solid transparent;
    padding: 6px 12px;
    font-size: 16px;
    border-radius: .25rem;              
  }
  .audio-container {
    text-align:center;
    justify-content: center;
    align-items: center;
  }
  h2 {
    text-align:center;
  }
  video {
    width: 400px;
  }
  .is-hidden {
    display: none;
  }
</style>

{:else}
Le chemin de ton fichier est pas bon !
{/if}

