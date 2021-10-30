<script>
  import Card from '../components/Card/Card.svelte';
</script>

<div class="ListEntities">
  <div class="ListEntities content">
    <div class="menu">
      <i class="fas fa-bars" />
    </div>
    <div class="hello-message">
      <span class="name">Hola Orlando,</span>
      <span class="date">10th Oct, 2021</span>
    </div>
    <div class="search-input">
      <input type="text" placeholder="Buscar contraseñas" />
      <i class="fas fa-search" />
    </div>
    <div class="card-container">
      <div class="card-elements">
        <Card />
        <Card />
        <Card />
        <Card />
        <Card />
        <Card />
        <Card />
        <Card />
        <Card />
        <Card />
        <Card />
        <Card />
      </div>
    </div>
  </div>
</div>

<style>
  .ListEntities {
    background-color: var(--tertiary);
    height: 100vh;
    width: 100%;
    display: flex;
    flex-flow: column;
    align-self: center;
  }

  .ListEntities.content {
    background-color: var(--tertiary);
    height: 100vh;
    position: relative;
    max-width: 1200px;
    width: 100%;
  }

  .menu {
    visibility: hidden;
    color: var(--secondary);
    font-size: 20px;
  }

  .hello-message .name {
    display: block;
    font-weight: 500;
    font-size: 21px;
  }

  .hello-message .date {
    display: block;
    color: var(--sub-title);
  }

  .search-input {
    position: relative;
    background-color: var(--tertiary);
    min-width: 335px;
    min-height: 48px;
    border-radius: 16px;
    box-shadow: 1px 4px 44px -2px var(--grey);
    margin-top: 23px;
  }
  .search-input input {
    background-color: transparent;
    resize: none;
    outline: none;
    border: none;
    transform: translateY(3px);
    width: 70%;
    position: absolute;
    left: 15px;
    top: 5px;
  }

  .search-input i {
    font-size: 22px;
    position: absolute;
    right: 15px;
    top: 5px;
  }

  .card-container {
    overflow-y: auto;
    overflow-x: hidden;
    width: 100%;
    display: flex;
    justify-content: center;
    background-color: red;
  }

  .card-elements {
    overflow-y: auto;
    overflow-x: hidden;
    background-color: green;
    max-width: 1050px;
    width: 100%;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    justify-items: center;
  }

  @media only screen and (max-width: 1160px) {
    .card-elements {
      grid-template-columns: repeat(2, 1fr);
    }
  }

  @media only screen and (max-width: 1024px) {
    .ListEntities {
      background-color: var(--tertiary);
      height: 100vh;
      position: relative;
    }

    .ListEntities.content {
    }

    .menu {
      visibility: visible;
    }
  }

  @media only screen and (max-width: 712px) {
    .card-elements {
      grid-template-columns: 1fr;
    }
  }
</style>
