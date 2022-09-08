<script>
  import Caroussel from "./Caroussel.svelte";
  import Avatar from "./Avatar.svelte";
  import AvatarGroup from "./AvatarGroup.svelte";
  import Logo from "../assets/roosveltes.png";
  import GradientGenerator from './GradientGenerator.svelte';
  import Player from './Player.svelte';
</script>

<img src={Logo} alt="logo" id="logo" />

<div class="container">
  <div class="menu">
    <h3>Composants</h3>
    <ul>
      <li><a href="#avatar">Avatar</a></li>
      <li><a href="#avatarGroup">AvatarGroup</a></li>
      <li><a href="#caroussel">Caroussel</a></li>
      <li><a href="#icons">Icons</a></li>
    </ul>
  </div>
  <div class="main">

    <!-- // CARROUSEL -->
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
    <!-- //END CARROUSEL -->

    <!-- // AVATAR -->
    <h1 id="avatar">Avatar</h1>
    <p>
      The Avatar component is used to represent user, and displays the profile
      picture, initials or fallback icon.
    </p>
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
          <td
            >"Mikael Blomkvist"</td
          >
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
    <!-- // END AVATAR -->

    <!-- //AVATARGROUP -->
    <h1 id="avatarGroup">Avatar Group</h1>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Commodi
      recusandae quam ratione nesciunt debitis praesentium dolore omnis,
      necessitatibus repudiandae ut mollitia! Totam unde natus quibusdam. Facere
      incidunt tempore magni excepturi?
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
          <td
            >true | false</td
          >
        </tr>
        <tr>
          <td>orientation</td>
          <td>String</td>
          <td>"row | column"</td>
        </tr>
      </table>
    </div>
    <!-- // END AVATARGROUP -->

    <GradientGenerator/> -->
    <Player pathAudio="/src/assets/apdl.mp4"/>
  </div>
</div>

<div id="copyright">
  Copyright Roosevelt 2022 - Ilyes Boulkrinat, Vincent Monneger, Rakule Th,
  Daisy Bruneau
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
