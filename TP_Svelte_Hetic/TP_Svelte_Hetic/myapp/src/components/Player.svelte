<script>
  import apdl from '../assets/apdl.mp4';
  import antidote from '../assets/antidote.mp3';
import { text } from 'svelte/internal';

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
<h2>Vidéo Player</h2>
<div class='audio-container'>
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
      Volume + { volume }
      {/if}
    </button>
    <button on:click={ volumeMinus }>
      {#if volume == 0}
      Volume minimum
      {:else}
      Volume - { volume }
      {/if}
    </button>
  </nav>
  <br>
  Ce composant permet de lire un fichier mp3/mp4 en passant en paramètre (pathAudio) le lien vers celui-ci !
</div>
{:else}
<h2>MP3 Player</h2>
<br>
<div class='audio-container'>
  <audio controls>
    <source src={pathAudio}>
  </audio>
<br>
  Ce composant permet de lire un fichier mp3/mp4 en passant en paramètre (pathAudio) le lien vers celui-ci !
</div>
{/if}

<style>
  button {
    cursor: pointer;
    outline: 0;
    color: #fff;
    background-color: #0d6efd;
    border-color: #0d6efd;
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

