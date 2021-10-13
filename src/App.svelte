<script>
  import Sidebar from './components/Sidebar/Sidebar.svelte';
	export let name;
</script>

<main>
  <Sidebar>
    <h1>Hello {name}! Munera</h1>
    <p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
  </Sidebar>
</main>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Lato:wght@100;300;400;500;600&display=swap');

	:root {
    --primary: #5AC97A;
    --secondary: #000;
    --tertiary: #FAFAFA;
    --grey: #C7C7C7;
    --primary-hover: rgb(52, 117, 70);
    --tertiary-hover: rgb(177, 177, 177);
  }

  :global(body) {
    background-color: var(--tertiary);
    color: var(--secondary);
    font-family: "Lato", sans-serif;
    margin: 0;
    padding: 0;
  }

  :global(h1, h2, h3) {
    margin: 0;
    padding: 0;
  }
</style>