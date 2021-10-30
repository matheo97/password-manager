<script>
  import Sidebar from './components/Sidebar/Sidebar.svelte';
</script>

<main>
  <Sidebar />
</main>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Lato:wght@100;300;400;500;600&display=swap');

  :root {
    /* colors */
    --primary: #5ac97a;
    --secondary: #000;
    --tertiary: #fafafa;
    --grey: #c7c7c7;
    --background: #e5e5e5;
    --primary-hover: rgb(52, 117, 70);
    --tertiary-hover: rgb(177, 177, 177);
    --sub-title: #939393;

    /* breakpoints */
    --tablet: 1024px;
    --phone: 640px;
  }

  :global(body) {
    background-color: var(--background);
    color: var(--secondary);
    font-family: 'Lato', sans-serif;
    margin: 0;
    padding: 0;
  }

  :global(h1, h2, h3) {
    margin: 0;
    padding: 0;
  }
</style>
