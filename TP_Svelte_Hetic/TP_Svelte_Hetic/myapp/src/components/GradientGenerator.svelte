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
<code style="font-size: 18px;"><i><b>background: linear-gradient({range}deg, {color1} {breakpoint1}%,{color2} {breakpoint2}% ,{color3} {breakpoint3}%) </b></i></code>
  <br>
  <br>
      Angle : 
      <br>
      <input  class='range_css' type="range" min="0" max="360" bind:value={ range }/>
      <br>
      Couleurs : 
      <br>
      <input type="color" name="" id="style1" bind:value={ color1 }/>
      <input type="color" name="" id="style1" bind:value={ color2 }/>
      <input type="color" name="" id="style1" bind:value={ color3 }/>
      <br>
      Breakpoint : 
      <br>
        <input class='range_css' style="background:{color1}" type="range" min="0" max="100" bind:value={ breakpoint1}/>
        <input class='range_css' style="background:{color2}" type="range" min="0" max="100" bind:value={ breakpoint2}/>
        <input class='range_css' style="background:{color3}" type="range" min="0" max="100" bind:value={ breakpoint3}/>
      <div class="form-range" style="background: linear-gradient({range}deg, {color1} {breakpoint1}%,{color2} {breakpoint2}% ,{color3} {breakpoint3}%); height:100px; width: 500px; margin-top: 20px; border-radius: 30px;"/>   
  </div>
<style>

#style1 {
  -webkit-appearance: none;
  -moz-appearance: none;
  appearance: none;
  width: 50px;
  height: 50px;
  background-color: transparent;
  border: none;
  cursor: pointer;
}
#style1::-webkit-color-swatch {
  border-radius: 15px;
  border: none;
}
#style1::-moz-color-swatch {
  border-radius: 15px;
  border: none;
}
/*input range CSS3*/
.range_css{
margin-top: 10px;
-webkit-appearance:none;
width:180px;
height:1rem;
background:lightgray;
cursor: grab;
border-radius:1.5rem}

/*****ie*****/

.range_css::-ms-track {
height:1.4rem;
border-radius:1.5rem;
background:transparent;
border-color:transparent;
color:transparent;/*enleve les traits*/}

.range_css::-ms-fill-lower {
height:1.4rem;
background:linear-gradient(to bottom,#26a65b 10%,#36e27d);
border:0 solid transparent;
border-radius:1.5rem}

.range_css::-ms-fill-upper {
background:linear-gradient(to bottom,#26a65b 10%,#36e27d);
border:0 solid transparent;
border-radius:1.5rem}

.range_css::-ms-thumb {
border:1px solid #ddd;
width:.8rem;
background:white;
height:.8rem;
border-radius:50%;
box-shadow:0 0 .125rem #aaa}

.range_css:focus::-ms-fill-lower,
.range_css:focus::-ms-fill-upper {

background:linear-gradient(to bottom,#26a65b 10%,#36e27d)

}

.range_css::-ms-tooltip{display:none}/*enleve le title*/

/*****fin ie*****/

/*****firefox*****/
.range_css::-moz-range-thumb{
border:1px solid #ddd;
width:1.4rem;
height:1.4rem;
border-radius:50%;
box-shadow:0 0 .125rem #aaa}

.range_css::-moz-range-track{
border:3px solid transparent;
padding:.5rem;
height:1rem;
border-radius:1.5rem;
background:none}
/*****fin firefox*****/


/*****Chrome,Opera*****/
.range_css::-webkit-slider-thumb{
-webkit-appearance:none;  
border:1px solid #ddd;
width:1.4rem;
height:1.4rem;
border-radius:50%;
background:white;
box-shadow:0 0 .125rem #aaa}
</style>