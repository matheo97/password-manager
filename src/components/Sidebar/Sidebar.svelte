<script>
  import items from './Items';
  import ListEntities from '../../pages/ListEntities.svelte';

  let isSidebarClosed = true;
  let selectedItem = {
    icon: 'fa-unlock-alt',
    content: 'contraseñas',
    key: 'password'
  };

  const closeSideBar = () => (isSidebarClosed = true);

  const openSideBar = () => (isSidebarClosed = false);

  const toggleSidebar = () => (isSidebarClosed = !isSidebarClosed);

  const selectItem = itemKey => {
    selectedItem = itemKey;
    isSidebarClosed = true;
  };
</script>

<div class="Sidebar">
  <div
    class={`Sidebar-elements ${isSidebarClosed ? 'close' : ''}`}
    on:mouseover={openSideBar}
    on:mouseout={closeSideBar}
    on:focus={openSideBar}
    on:blur={closeSideBar}
  >
    <div class="Sidebar-logo">
      <img src="assets/logo.svg" alt="passify-logo" />
      <h1>Pass<em>’ify</em></h1>
    </div>
    <div class="Sidebar-item-container">
      <ul class="Sidebar-item-list">
        {#each items as item}
          <li
            class={`Sidebar-item-value ${
              selectedItem === item.key ? 'selected' : ''
            }`}
            on:click={() => selectItem(item.key)}
          >
            <i class={`fas ${item.icon}`} />
            <span class="Sidebar-item-name">{item.content}</span>
          </li>
        {/each}
      </ul>
    </div>
  </div>
  <div class="Sidebar-content">
    <div
      class={`Sidebar-content-fade-out ${isSidebarClosed ? 'close' : ''}`}
      on:click={closeSideBar}
    />
    <ListEntities toggleMenu={toggleSidebar} entity={selectedItem} />
  </div>
</div>

<style>
  .Sidebar {
    display: flex;
    position: relative;
  }

  .Sidebar-elements {
    width: 240px;
    height: 100vh;
    background-color: var(--primary);
    transition: width 0.4s ease-in-out;
    z-index: 5;
  }

  .Sidebar-elements.close {
    width: 80px;
  }

  .Sidebar-content {
    width: calc(100vw - 80px);
    height: 100vh;
    background-color: var(--background);
  }
  .Sidebar-content-fade-out {
    position: absolute;
    top: 0;
    left: 0;
    z-index: 2;
    opacity: 0.3;
    height: 100%;
    width: 100%;
    background-color: var(--secondary);
  }

  .Sidebar-content-fade-out.close {
    display: none;
  }

  .Sidebar-elements .Sidebar-logo {
    display: flex;
    align-items: center;
    justify-content: flex-start;
    margin-top: 30px;
    margin-left: 14px;
    width: 90%;
  }

  .Sidebar-logo img {
    width: 50px;
    height: 60px;
  }

  .Sidebar-logo h1 {
    color: var(--secondary);
    margin-left: 15px;
    font-size: 28px;
    opacity: 1;
    visibility: visible;
  }

  .Sidebar-elements.close .Sidebar-logo h1 {
    opacity: 0;
    visibility: hidden;
    transition: opacity 0.2s linear;
  }

  .Sidebar-logo h1 em {
    color: var(--tertiary);
    font-style: normal;
  }

  .Sidebar-item-list {
    padding-left: 20px;
  }

  .Sidebar-item-value {
    list-style-type: none;
    display: flex;
    align-items: center;
    justify-content: flex-start;
    width: 80%;
    margin-top: 30px;
    cursor: pointer;
    padding: 10px;
    border-radius: 10px;
  }

  .Sidebar-item-value.selected {
    opacity: 0.6;
  }

  .Sidebar-item-value:hover {
    opacity: 0.6;
  }

  .Sidebar-item-value i {
    font-size: 25px;
    color: var(--tertiary);
  }

  .Sidebar-item-value span {
    font-size: 15px;
    font-weight: 500;
    color: var(--tertiary);
    text-transform: uppercase;
    margin-left: 10px;
    opacity: 1;
    visibility: visible;
  }
  .Sidebar-elements.close .Sidebar-item-value span {
    opacity: 0;
    visibility: hidden;
    transition: opacity 0.2s linear;
  }

  @media only screen and (max-width: 1024px) {
    .Sidebar-elements {
      position: absolute;
      left: 0;
      transition: left 0.3s ease-out;
    }

    .Sidebar-elements.close {
      position: absolute;
      left: -240px;
      transition: left 0.2s ease-in;
      width: 240px;
    }

    .Sidebar-content {
      width: 100vw;
    }
  }
</style>
