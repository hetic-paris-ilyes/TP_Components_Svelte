<script>

    let range = 0;
    let color1= "#009900";
    let breakpoint1= 0;
    let color2= "#633D35";
    let breakpoint2= 0;
    let color3= "#639b96";
    let breakpoint3= 0;
  
</script>  

 <div class="main">
  Code CSS à copier : <b>background: linear-gradient({range}deg, {color1} {breakpoint1}%,{color2} {breakpoint2}% ,{color3} {breakpoint3}%) </b>
  <br>
      Angle : 
      <input type="range" min="0" max="360" bind:value={ range }/>
      <br>
      Couleurs : 
      <input type="color" name="" id="col1" bind:value={ color1 }/>
      <input type="color" name="" id="col2" bind:value={ color2 }/>
      <input type="color" name="" id="col3" bind:value={ color3 }/>
      <br>
      Breakpoint : 
      <input type="range" min="0" max="100" bind:value={ breakpoint1}/>
      <input type="range" min="0" max="100" bind:value={ breakpoint2}/>
      <input type="range" min="0" max="100" bind:value={ breakpoint3}/>
      <div style="background: linear-gradient({range}deg, {color1} {breakpoint1}%,{color2} {breakpoint2}% ,{color3} {breakpoint3}%); height:100px; width: 500px; margin-top: 20px; border-radius: 30px;"/>   
  </div>
<style>

</style>