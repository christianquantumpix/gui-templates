<script>
  // based on suggestions from:
  // Sami Keijonen https://webdesign.tutsplus.com/tutorials/how-to-make-custom-accessible-checkboxes-and-radio-buttons--cms-32074
  // and Inclusive Components by Heydon Pickering https://inclusive-components.design/toggle-button/

  export let options;
  export let userSelected = options[0].value;
	
	const uniqueID = Math.floor(Math.random() * 100)

  const slugify = (str = "") =>
    str.toLowerCase().replace(/ /g, "-").replace(/\./g, "");
</script>

<div role="radiogroup" 
				 class="group-container"
				 aria-labelledby={`label-${uniqueID}`}
				 id={`group-${uniqueID}`}>
  {#each options as { value, label }}
    <input
      type="radio"
      id={slugify(label)}
      bind:group={userSelected}
      value={value} />
    <label for={slugify(label)}> {label} </label>
  {/each}
</div>

<style>
			:root {
		--accent-color: CornflowerBlue;
		--gray: #ccc;
	}
	
   .group-container {
		 display: block;
		 cursor: pointer;
		 margin: 3em;
		 -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
    }

  label {
    line-height: 1.5em;
		background: red;
		font-weight: bold;
  }

  input[type="radio"] {
		display: none;
  }

  input[type="radio"] + label {
    display: block;
    position: relative;
    text-align: left;
  }

  input[type="radio"] + label::before {
      content: "";
     display: inline-block;
      width: 2em;
      height: 2em;
      background: transparent;
      border: 2px solid var(--gray, #ccc);
      border-radius: 50%;
		margin: .5em .5em .5em .5em;
		vertical-align: middle;
  }

  input[type="radio"]:checked + label::before {
    xborder: 2px solid var(--gray, #ccc);
    xborder-radius: 50%;
  }

  input[type="radio"] + label::after {
    content: "";
    position: absolute;
    display: block;
    width: 1.3em;
    height: 1.3em;
    top:  .475em;
    left: .475em;
		margin: .5em .5em .5em .5em;
    background: var(--accent-color, #282828);
    border-radius: 50%;
    transform: scale(0);
  }

  input[type="radio"]:checked + label::after {
    opacity: 1;
    transform: scale(1);
  }

  input[type="radio"]:focus + label::before {
    /* box-shadow: 0 0 0 1px var(--accent-color, #282828); */
    border-radius: 50%;
  }  
  
  input[type="radio"]:disabled + label {
    color: darken(var(--gray, #ccc), 10);
  }

  input[type="radio"]:disabled + label::before {
    background: var(--gray, #ccc);
  } 
  /* gravy */


  input[type="radio"] + label::before {
      transition: background 0.35s cubic-bezier(.25, 0, .75, 1);
  }

  input[type="radio"]:checked + label::before {
    transition: background 0.35s cubic-bezier(.25, 0, .75, 1);
  }

  input[type="radio"] + label::after {
    transition: transform 0.22s cubic-bezier(.25, 0, .75, 1);
  }

  input[type="radio"]:checked + label::after {
    transition: transform 0.22s cubic-bezier(.25, 0, .75, 1);
  }

  input[type="radio"]:focus + label::before {
    /* box-shadow: 0 0px 8px var(--accent-color, #282828); * /
    border-radius: 50%;
  }

</style>
