<script>
  import GradientGenerator from './components/GradientGenerator.svelte';
  import Player from './components/Player.svelte';
  import Table from './components/Table.svelte';
  import Timer from './components/Timer.svelte';
  import { tableData } from './static/tableData'

</script>

<div>
    <Table tableData={tableData} variant="simple" />
    <Timer secondsTimer={5} minutesTimer={1} displayInputs={true} displayControls={true} />

    <GradientGenerator/>
    <Player pathAudio="/src/assets/apdl.mp4"/>
</div>