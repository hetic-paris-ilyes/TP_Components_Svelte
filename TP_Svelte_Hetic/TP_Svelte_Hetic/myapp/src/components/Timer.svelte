<script>
  import { tweened } from 'svelte/motion';
  export let colorTimer = '#9AE6B4'
  export let displayInputs = false
  export let displayControls = false

  export let secondsTimer = 0
  export let minutesTimer = 1

  let identifier
  let hasStarted = false

  $: original = (minutesTimer * 60) + secondsTimer 
	$: timer = tweened(original)

  $: progressBar = $timer/original > 0 ? $timer/original : 2

  $: if (progressBar === 2) {
    resetTimer()
  }

  const startTimer = () => {
    if (secondsTimer > 0 || minutesTimer > 0) {
      if (hasStarted) {
        return;
      }

      hasStarted = true
      identifier = setInterval(() => {
        if ($timer > 0) $timer--;
      }, 1000);
    }
  }

  const pauseTimer = () => {
    hasStarted = false
    clearInterval(identifier);
  }

  const resetTimer = () => {
    secondsTimer = 0
    minutesTimer = 0
    pauseTimer()
  }

  if (displayControls === false) {
    startTimer()
  }

  $: minutes = Math.floor($timer / 60);
  $: minname = minutes > 1 ? "mins" : "min";
  $: seconds = Math.floor($timer - minutes * 60)

  $: angle = 360 * progressBar


  $:	background = `radial-gradient(white 50%, transparent 51%),
      conic-gradient(transparent 0deg ${angle}deg, gainsboro ${angle}deg 360deg),
      conic-gradient(${colorTimer} 0deg, ${colorTimer} 90deg, ${colorTimer} 180deg, ${colorTimer});`;
	
	$: cssVarStyles = `--background:${background}`

</script>


<div class="font-timer">
  <div class="display-timer" style="margin-bottom: 10px;">
    <div id="progress-circle" style="{cssVarStyles}">
      <span class="circle-time">{minutes}{minname} {seconds}s</span>
    </div>
  </div>
  {#if displayInputs}
    <div style="text-align: center; margin-bottom: 10px; margin-top: 10px;">
      <input bind:value={minutesTimer} type="number" id="minutes" min="0" max="60" placeholder="Minutes"> {minname}
      <input bind:value={secondsTimer} type="number" id="secondes" min="0" max="60" placeholder="Secondes"> s
    </div>
  {/if}
  {#if displayControls}
    <div style="text-align: center;">
      <svg on:click={startTimer} xmlns="http://www.w3.org/2000/svg" width="40" height="40" fill="currentColor" class="bi bi-play" viewBox="0 0 16 16"> <path d="M10.804 8 5 4.633v6.734L10.804 8zm.792-.696a.802.802 0 0 1 0 1.392l-6.363 3.692C4.713 12.69 4 12.345 4 11.692V4.308c0-.653.713-.998 1.233-.696l6.363 3.692z"/> </svg>
      <svg on:click={pauseTimer} xmlns="http://www.w3.org/2000/svg" width="40" height="40" fill="currentColor" class="bi bi-pause" viewBox="0 0 16 16"> <path d="M6 3.5a.5.5 0 0 1 .5.5v8a.5.5 0 0 1-1 0V4a.5.5 0 0 1 .5-.5zm4 0a.5.5 0 0 1 .5.5v8a.5.5 0 0 1-1 0V4a.5.5 0 0 1 .5-.5z"/> </svg>
      <svg on:click={resetTimer} xmlns="http://www.w3.org/2000/svg" width="40" height="40" fill="currentColor" class="bi bi-x" viewBox="0 0 16 16"> <path d="M4.646 4.646a.5.5 0 0 1 .708 0L8 7.293l2.646-2.647a.5.5 0 0 1 .708.708L8.707 8l2.647 2.646a.5.5 0 0 1-.708.708L8 8.707l-2.646 2.647a.5.5 0 0 1-.708-.708L7.293 8 4.646 5.354a.5.5 0 0 1 0-.708z"/> </svg>
    </div>
  {/if}
</div>



<style>
.display-timer {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.font-timer {
  font-family: -apple-system, BlinkMacSystemFont, 
    "Segoe UI", 
    Roboto, 
    Oxygen-Sans, 
    Ubuntu, 
    Cantarell, 
    "Helvetica Neue", 
    sans-serif
}

#progress-circle {
  background: var(--background);
  border-radius: 50%;
  width: 120px;
  height: 120px;
	transition: all 500ms ease-in;
	will-change: transform;
}

.circle-time {
  width: 122px;
  height: 122px;
  border-radius: 50%;
  line-height: 120px;
  text-align: center;
  position: absolute;
  z-index: 100;
  font-weight: 700;
  font-size: 15px;
}

.bi {
  cursor: pointer;
}

</style>