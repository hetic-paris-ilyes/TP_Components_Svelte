<script>
  import Caroussel from "./Caroussel.svelte";
  import Avatar from "./Avatar.svelte";
  import AvatarGroup from "./AvatarGroup.svelte";
  import Logo from "../assets/roosveltes.png";
  import GradientGenerator from "./GradientGenerator.svelte";
  import Player from "./Player.svelte";
  import IconsGenerator from "./IconsGenerator.svelte";
  import Timer from "./Timer.svelte";
  import Table from "./Table.svelte";
  import { tableData } from "../static/tableData";

  const exampleTable = `[{
    name: 'Kapabangala',
    age: '45',
    ville: 'Paris',
    job: 'dev'
  }]`;
</script>

<img src={Logo} alt="logo" id="logo" />

<div class="container">
  <div class="menu">
    <h3>Composants</h3>
    <ul>
      <li><a href="#avatar">Avatar</a></li>
      <li><a href="#avatarGroup">AvatarGroup</a></li>
      <li><a href="#button">Button</a></li>
      <li><a href="#caroussel">Caroussel</a></li>
      <li><a href="#drawer">Drawer</a></li>
      <li><a href="#gradientgenerator">GradientGenerator</a></li>
      <li><a href="#icons">Icons Generator</a></li>
      <li><a href="#player">Player</a></li>
      <li><a href="#popup">Popup</a></li>
      <li><a href="#tableGenerator">Table</a></li>
      <li><a href="#timer">Timer</a></li>
    </ul>
  </div>
  <div class="main">
    <!-- // AVATAR -->
    <div>
      <h1 id="avatar">Avatar</h1>
      <p>
        The Avatar component is used to represent user, and displays the profile
        picture, initials or fallback icon.
      </p>
      <Avatar
        state="online"
        name="Mikael Blomkvist"
        src="https://wallup.net/wp-content/uploads/2018/10/07/458379-cat-animal-pet-cats-kitty-cute-sweet.jpg"
      />
      <Avatar
        state="busy"
        name="Mikael Blomkvist"
        src="https://wallup.net/wp-content/uploads/2018/10/07/458379-cat-animal-pet-cats-kitty-cute-sweet.jpg"
      />

      <Avatar
        state="offline"
        name="Mikael Blomkvist"
        src="https://images.hdqwalls.com/download/1/cute-kitty.jpg"
      />

      <h3>Usage</h3>
      <pre><code> {'<Avatar name="Mikael Blomkvist" size="md" state="online" />'} </code></pre>
      <h3>Props</h3>
      <div class="table">
        <table>
          <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Value</th>
          </tr>

          <tr>
            <td>name</td>
            <td>String</td>
            <td>"Mikael Blomkvist"</td>
          </tr>
          <tr>
            <td>size</td>
            <td>String</td>
            <td>"sm | md | lg"</td>
          </tr>
          <tr>
            <td>src</td>
            <td>String</td>
            <td>"https://monimage.png"</td>
          </tr>
          <tr>
            <td>state</td>
            <td>String</td>
            <td>"offiline | online | busy"</td>
          </tr>
        </table>
      </div>
    </div>
    <!-- // END AVATAR -->

    <!-- //AVATARGROUP -->
    <div>
      <h1 id="avatarGroup">Avatar Group</h1>
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Commodi
        recusandae quam ratione nesciunt debitis praesentium dolore omnis,
        necessitatibus repudiandae ut mollitia! Totam unde natus quibusdam.
        Facere incidunt tempore magni excepturi?
      </p>
      <AvatarGroup group>
        <Avatar
          state="busy"
          name="Mikael Blomkvist"
          src="https://i.pinimg.com/originals/3e/79/60/3e796019c03bc5502f39e5dba0d57030.jpg"
        />

        <Avatar
          state="online"
          name="Mikael Blomkvist"
          src="https://wallup.net/wp-content/uploads/2018/10/07/458379-cat-animal-pet-cats-kitty-cute-sweet.jpg"
        />

        <Avatar
          state="online"
          name="Mikael Blomkvist"
          src="https://images.hdqwalls.com/download/1/cute-kitty.jpg"
        />
      </AvatarGroup>
      <h3>Usage</h3>
      <pre><code> {'<AvatarGroup orientation="row" group />'} </code></pre>
      <h3>Props</h3>
      <div class="table">
        <table>
          <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Value</th>
          </tr>

          <tr>
            <td>group</td>
            <td>Boolean</td>
            <td>true | false</td>
          </tr>
          <tr>
            <td>orientation</td>
            <td>String</td>
            <td>"row | column"</td>
          </tr>
        </table>
      </div>
    </div>
    <!-- // END AVATARGROUP -->

    <!-- // BUTTON -->
    <div />
    <!-- //END BUTTON -->

    <!-- // CARROUSEL -->
    <div>
      <h1 id="caroussel">Caroussel</h1>
      <p>The Caroussel component is used to display pictures.</p>
      <Caroussel size="lg" showIndex />
      <h3>Usage</h3>
      <pre><code> {'<Caroussel size="lg" showIndex />'} </code></pre>
      <h3>Props</h3>
      <div class="table">
        <table>
          <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Value</th>
          </tr>

          <tr>
            <td>pictures</td>
            <td>Array</td>
            <td
              >["https://mypicture1.com", "https://mypicure2.com",
              "https://mypicture3.com"]</td
            >
          </tr>
          <tr>
            <td>size</td>
            <td>String</td>
            <td>"sm | md | lg"</td>
          </tr>
          <tr>
            <td>showIndex</td>
            <td>Boolean</td>
            <td>true | false</td>
          </tr>
          <tr>
            <td>interval</td>
            <td>Number</td>
            <td>2500</td>
          </tr>
        </table>
      </div>
    </div>
    <!-- //END CARROUSEL -->

    <!-- // DRAWER -->
    <div />
    <!-- // END DRAWER -->

    <!-- //GRADIENT GENERATOR -->
    <div>
      <h1 id="gradientgenerator">The Gradient Generator</h1>
      <p>
        The Gradient Generator component is used to create a gradient and copy
        the css linked to it.
      </p>
      <GradientGenerator />

      <h3>Usage</h3>
      <pre><code>{"<GradientGenerator/>"}</code></pre>
    </div>
    <!-- // END GRADIENT GENERATOR -->

    <!-- // ICONSGENERATOR -->
    <div>
      <h1 id="iconsGenerator">Icons Generator</h1>
      <p>
        The Icons Generator component is used to quickly add icons to your
        project.
      </p>
      <div class="icons-example_wrapper">
        <IconsGenerator icon="warning" fillColor="#16a5a3" size={45} border />
        <IconsGenerator icon="warning" fillColor="black" size={35} />
        <IconsGenerator icon="warning" fillColor="#16a5a3" size={25} border />
        <IconsGenerator icon="warning" fillColor="black" size={15} />
      </div>
      <div class="icons-example_wrapper">
        <IconsGenerator icon="phone" fillColor="#16a5a3" size={45} border />
        <IconsGenerator icon="phone" fillColor="#black" size={35} />
        <IconsGenerator icon="phone" fillColor="#16a5a3" size={25} border />
        <IconsGenerator icon="phone" fillColor="black" size={15} />
      </div>
      <div class="icons-example_wrapper">
        <IconsGenerator
          icon="phone"
          fillColor="black"
          size={55}
          url="https://images.hdqwalls.com/download/1/cute-kitty.jpg"
          border
        />
        <IconsGenerator
          size={45}
          url="https://images.hdqwalls.com/download/1/cute-kitty.jpg"
        />
      </div>
      <h3>Usage</h3>
      <pre><code> {'<IconsGenerator icon="warning" fillColor="#16a5a3" size={45} border/>'} </code></pre>
      <h3>Props</h3>
      <div class="table">
        <table>
          <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Value</th>
          </tr>

          <tr>
            <td>icon</td>
            <td>String</td>
            <td
              >"phone | back | chat | chat-quote | chevron-up | chevron-down |
              chevron-left | chevron-right | cup-hot | cursor | download |
              warning"</td
            >
          </tr>
          <tr>
            <td>size</td>
            <td>Number</td>
            <td>25</td>
          </tr>
          <tr>
            <td>url</td>
            <td>String</td>
            <td>"https://monimage.com</td>
          </tr>
          <tr>
            <td>fillColor</td>
            <td>String</td>
            <td>"black | #16a5a3"</td>
          </tr>
          <tr>
            <td>border</td>
            <td>Boolean</td>
            <td>true | false</td>
          </tr>
        </table>
      </div>
    </div>
    <!-- // END ICONSGENERATOR -->

    <!-- // MP4 PLAYER -->
    <div>
      <h1 id="player">MP4 Player</h1>
      <p>
        The MP4 Player component is used to play a video and interact with !
      </p>

      <Player pathAudio="/src/assets/apdl.mp4" />

      <h3>Usage</h3>
      <pre><code> {'<Player pathAudio="cheminverslavideo.mp4" />'} </code></pre>
      <h3>Props</h3>
      <div class="table">
        <table>
          <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Value</th>
          </tr>

          <tr>
            <td>pathAudio</td>
            <td>String</td>
            <td>"../assets/videodefou.mp4"</td>
          </tr>
          <tr>
            <td>pathAudio</td>
            <td>String</td>
            <td>"../assets/audidefou.mp3"</td>
          </tr>
        </table>
      </div>
    </div>
    <!-- // END MP4 PLAYER -->

    <!-- // POPUP -->
    <div />
    <!-- // END POPUP -->

    <!-- //TABLE -->
    <div>
      <h1 id="tableGenerator">Table</h1>
      <p>
        It's a table to parse data. Columns are the keys of the first object.
      </p>
      <Table {tableData} variant="simple" />
      <h3>Usage</h3>
      <pre><code> {'<Table tableData={tableData} variant="simple" />'} </code></pre>
      <h3>Props</h3>
      <div class="table">
        <table>
          <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Value</th>
          </tr>

          <tr>
            <td>tableData</td>
            <td>Array&lt;object&gt</td>
            <td>{exampleTable}</td>
          </tr>
          <tr>
            <td>variant</td>
            <td>String</td>
            <td>'simple' | 'striped'</td>
          </tr>
          <tr>
            <td>gap</td>
            <td>String</td>
            <td>'sm' | 'md' | 'lg'</td>
          </tr>
          <tr>
            <td>borderColor</td>
            <td>String</td>
            <td>'#9AE6B4'</td>
          </tr>
          <tr>
            <td>fontColor</td>
            <td>String</td>
            <td>'#9AE6B4'</td>
          </tr>
        </table>
      </div>
    </div>
    <!-- // END TABLE -->
    <!-- //TIMER -->
    <div>
      <h1 id="timer">Timer</h1>
      <p>
        It's a timer. You can let it count onMounted of the page or you can use
        some controls and inputs to set the value of the timer.
      </p>
      <Timer />
      <h3>Usage</h3>
      <pre><code> {'<Timer colorTimer="black" displayInputs={true} displayControls={true} minutesTimer={1} secondsTimer={45} />'} </code></pre>
      <h3>Props</h3>
      <div class="table">
        <table>
          <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Value</th>
          </tr>

          <tr>
            <td>colorTimer</td>
            <td>Boolean</td>
            <td>true | false</td>
          </tr>
          <tr>
            <td>displayInputs</td>
            <td>Boolean</td>
            <td>true | false</td>
          </tr>
          <tr>
            <td>displayControls</td>
            <td>Boolean</td>
            <td>true | false</td>
          </tr>
          <tr>
            <td>secondsTimer</td>
            <td>Number</td>
            <td>60</td>
          </tr>
          <tr>
            <td>minutesTimer</td>
            <td>Number</td>
            <td>60</td>
          </tr>
        </table>
      </div>
    </div>
    <!-- // END TIMER -->
  </div>
</div>

<div id="copyright">
  Copyright Roosevelt 2022 - Ilyes Boulkrinat, Vincent Monneger, Rakule
  Thavarasa, Daisy Bruneau
</div>

<style>
  /* :global(body) {
    background-color: black;
  } */

  :global(#app) {
    overflow: hidden;
  }

  #logo {
    width: 390px;
    position: fixed;
  }

  .container {
    display: flex;
    width: 75%;
    /* gap: 25px; */
    padding: 0 15%;
  }

  :global(body) {
    font-family: system-ui;
  }

  pre {
    padding: 15px;
    background-color: black;
    color: white;
    border-radius: 10px;
  }

  .menu {
    position: fixed;
    width: 15%;
    border-right: 1px solid #639b96;
    top: 25%;
  }

  h3,
  #copyright {
    color: #639b96;
  }
  .menu li {
    list-style: none;
  }

  .menu li a {
    text-decoration: none;
    color: black;
  }

  .menu li a:focus {
    color: #639b96;
  }
  .main {
    padding-left: 5%;
    width: 50%;
    display: flex;
    flex-direction: column;
    flex-wrap: nowrap;
    align-content: flex-start;
    justify-content: center;
    align-items: flex-start;
    text-align: justify;
    position: relative;
    left: 25%;
    margin-top: 5%;
  }

  .icons-example_wrapper {
    margin: 5px 0px;
    display: flex;
    flex-direction: row;
    flex-wrap: nowrap;
    align-content: center;
    justify-content: center;
    align-items: flex-end;
    gap: 15px;
  }

  .table {
    border: 1px solid #ddd;
    border-radius: 15px;
    overflow: hidden;
  }
  table {
    border-collapse: collapse;
  }

  tr,
  td,
  th {
    /* border: 1px solid black; */
    padding: 15px;
    border-bottom: 1px solid #ddd;
  }
  #copyright {
    width: 100%;
    text-align: center;
    margin-top: 5%;
  }
</style>
