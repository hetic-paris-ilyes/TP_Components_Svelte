<script>
  export let links = [
    {
      name: "link1",
      url: "#0",
    },
    {
      name: "link2",
      url: "#1",
    },
    {
      name: "link3",
      url: "#2",
    },
    {
      name: "link4",
      url: "#3",
    },
  ];
</script>

<body>
  <input type="checkbox" id="drawer-toggle" name="drawer-toggle" />
  <label for="drawer-toggle" id="drawer-toggle-label" />
  <header>
    <slot />
  </header>
  <nav id="drawer">
    <ul>
      {#each links as link}
        <li><a href={link.url}>{link.name}</a></li>
      {/each}
    </ul>
  </nav>
</body>

<style>
  * {
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
    -o-box-sizing: border-box;
    box-sizing: border-box;
    /* animation */
    -webkit-transition: 0.25s ease-in-out;
    -moz-transition: 0.25s ease-in-out;
    -o-transition: 0.25s ease-in-out;
    transition: 0.25s ease-in-out;
    margin: 0;
    padding: 0;
    -webkit-text-size-adjust: none;
  }

  /* Makes sure that everything is 100% height */

  /* gets the actual input out of the way; 
  we're going to style the label instead */

  #drawer-toggle {
    /* position: absolute; */
    opacity: 1;
  }

  /* #drawer-toggle-label {
    -webkit-touch-callout: none;
    -webkit-user-select: none;
    -khtml-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    user-select: none;
    left: 0px;
    height: 50px;
    width: 50px;
    display: block;
    position: relative;
    background: rgba(255, 255, 255, 0);
    z-index: 1;
  } */

  /* adds our "hamburger" menu icon */

  #drawer-toggle-label:before {
    content: "";
    display: block;
    position: absolute;
    height: 2px;
    width: 24px;
    background: #319795;
    left: 13px;
    top: 18px;
    box-shadow: 0 6px 0 #319795, 0 12px 0 #319795;
  }

  header {
    width: 100%;
    position: fixed;
    left: 0px;
    /* background: #efefef; */
    padding: 10px 10px 10px 50px;
    font-size: 30px;
    line-height: 30px;
    z-index: 0;
  }

  /* drawer menu pane - note the 0px width */

  #drawer {
    position: fixed;
    top: 0;
    left: -300px;
    height: 100%;
    width: 300px;
    background: #319795;
    overflow-x: hidden;
    overflow-y: scroll;
    padding: 20px;
    -webkit-overflow-scrolling: touch;
  }

  /* actual page content pane */

  /* checked styles (menu open state) */

  #drawer-toggle:checked ~ #drawer-toggle-label {
    height: 100%;
    width: calc(100% - 300px);
    background: rgba(255, 255, 255, 0.8);
  }

  #drawer-toggle:checked ~ #drawer-toggle-label,
  #drawer-toggle:checked ~ header {
    left: 300px;
  }

  #drawer-toggle:checked ~ #drawer {
    left: 0px;
  }

  /* Menu item styles */

  #drawer ul {
    list-style-type: none;
  }

  #drawer ul a {
    display: block;
    padding: 10px;
    color: #c7c7c7;
    text-decoration: none;
  }

  #drawer ul a:hover {
    color: white;
  }

  /* Responsive MQ */

  @media all and (max-width: 350px) {
    #drawer-toggle:checked ~ #drawer-toggle-label {
      height: 100%;
      width: 50px;
    }

    #drawer-toggle:checked ~ #drawer-toggle-label,
    #drawer-toggle:checked ~ header {
      left: calc(100% - 50px);
    }

    #drawer-toggle:checked ~ #drawer {
      width: calc(100% - 50px);
      padding: 20px;
    }
  }
</style>
