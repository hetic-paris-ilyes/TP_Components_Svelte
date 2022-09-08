<script>

    let range = 0;
    let color1= "#009900";
    let breakpoint1= 0;
    let color2= "#633D35";
    let breakpoint2= 0;
    let color3= "#0E2C6F";
    let breakpoint3= 0;
  
</script>  
<h2>Générateur de gradient</h2>
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
    <div style="background: linear-gradient({range}deg, {color1} {breakpoint1}%,{color2} {breakpoint2}% ,{color3} {breakpoint3}%); height:100px; width: 500px; margin-top: 20px; margin-left:700px"/>
    <br>
    Ce composant permet de générer le css lié à un gradient que l'on peut générer en manipulant les différents boutons !
   
</div>
<style>

 h2 {
    text-align:center;
  }

  .main {
    text-align:center;
    justify-content: center;
    align-items: center;
  }
</style>