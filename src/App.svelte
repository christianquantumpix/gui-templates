<script lang="ts">
  import svelteLogo from './assets/svelte.svg'
  import viteLogo from '/vite.svg'
  import Counter from './lib/Counter.svelte'
</script>

<main>
  <div>
    <a href="https://vitejs.dev" target="_blank" rel="noreferrer">
      <img src={viteLogo} class="logo" alt="Vite Logo" />
    </a>
    <a href="https://svelte.dev" target="_blank" rel="noreferrer">
      <img src={svelteLogo} class="logo svelte" alt="Svelte Logo" />
    </a>
  </div>
  <h1>Vite + Svelte</h1>

  <div class="card">
    <Counter />
  </div>

  <h1>Custom Radio Buttons</h1>
<label class="container">One
  <input type="radio" checked name="radio">
  <span class="checkmark"></span>
</label>
<label class="container">Two
  <input type="radio" name="radio">
  <span class="checkmark"></span>
</label>
<label class="container">Three
  <input type="radio" name="radio">
  <span class="checkmark"></span>
</label>
<label class="container">Four
  <input type="radio" name="radio">
  <span class="checkmark"></span>
</label>

  <p>
    Check out <a href="https://github.com/sveltejs/kit#readme" target="_blank" rel="noreferrer">SvelteKit</a>, the official Svelte app framework powered by Vite!
  </p>

  <p class="read-the-docs">
    Click on the Vite and Svelte logos to learn more
  </p>
</main>

<style>
  .logo {
    height: 6em;
    padding: 1.5em;
    will-change: filter;
    transition: filter 300ms;
  }
  .logo:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
  }
  .logo.svelte:hover {
    filter: drop-shadow(0 0 2em #ff3e00aa);
  }
  .read-the-docs {
    color: #888;
  }

  /* The container */
.container {
  display: block;
  position: relative;
  padding: .5em;
  cursor: pointer;
  font-size: 22px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

/* Hide the browser's default radio button */
.container input {
  position: absolute;
  opacity: 0;
  cursor: pointer;
}

/* Create a custom radio button */
.checkmark {
  position: absolute;
  top: 0;
  left: 0;
  height: 2em;
  width: 2em;
  border-radius: 50%;
  border: .125em solid transparent;
  transition: all .22s cubic-bezier(.25, 0, .75, 1);
}

/* On mouse-over, add a grey background color */
.container:hover input ~ .checkmark {
  border: .125em solid #2196F3;
}

/* When the radio button is checked, add a blue background */
.container input:checked ~ .checkmark {
  border: .125em solid #2196F3;
}

/* Create the indicator (the dot/circle - hidden when not checked) */
.checkmark:after {
  content: "";
  position: absolute;
  opacity: 0;
  transition: all .22s cubic-bezier(.25, 0, .75, 1);
}

/* Show the indicator (dot/circle) when checked */
.container input:checked ~ .checkmark:after {
  opacity: 1;
}

/* Style the indicator (dot/circle) */
.container .checkmark:after {
 	top: .5em;
	left: .5em;
	width: 1em;
	height: 1em;
	border-radius: 50%;
	background: #2196F3;
}
</style>
