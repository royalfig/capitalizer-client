<script>
  //   import { Title } from "../../capitalizer/dist/index.esm";
  let value = "";
  let titles = [];
  let changed = [];
  let rulesEl = [];
  import { Title } from "../../../capitalizer/dist/index.esm";

  function capitalize() {
    if (!value) {
      titles = [];
      changed = [];
      rulesEl = [];
      return;
    }
    const { capitalizedTitles, changes, rules } = new Title("CMS", [value]);
    titles = capitalizedTitles;
    changed = changes;
    rulesEl = rules;
  }

  function createNewInput(e) {
    if (e.key === "Enter") {
      console.log("createComponent");
      // Individual elements. Enter fires event to container that creates element with
    }
  }
</script>

<section class="main">
  <div class="left">
    <div class="input-container">
      <p class="instructions">Type or paste your titles</p>
      <input
        type="text"
        bind:value
        on:input={capitalize}
        on:keyup={createNewInput}
      />
    </div>
  </div>

  <div class="right">
    {#each titles as title}
      <p>{title}</p>
    {/each}

    {#each changed as change}
      <p>{@html change}</p>
    {/each}

    {#each rulesEl as rule}
      <p>{rule}</p>
    {/each}
  </div>
</section>

<style>
  /* your styles go here */
  .instructions {
    position: relative;
    font-size: var(--small);
  }
  .instructions::before {
    height: 1em;
    width: 1em;
    background-color: var(--green);
    border-radius: 50%;
    content: "";
  }
  input {
    outline: 0;
    font-size: inherit;
    font-family: inherit;
    padding: 0.25em 0.5em;
    border: none;
    background-color: var(--light-blue);
    border-bottom: 1px solid var(--dark-blue);
    caret-color: var(--red);
    width: 100%;
  }

  .main {
    display: flex;
    flex-direction: column;
    gap: 2rem;
  }

  :global(.has-changed) {
    color: var(--red);
  }
</style>
