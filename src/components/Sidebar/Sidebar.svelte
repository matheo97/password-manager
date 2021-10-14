<script>
  import items from './Items';

  let sidebarClosed = true;
  let selectedItem = null;

  const toggleSidebar = () => sidebarClosed = !sidebarClosed;

  const selectItem = (itemKey) => selectedItem = itemKey;

</script>

<div class="Sidebar">
  <div 
    class={`Sidebar-elements ${sidebarClosed ? 'close': ''}`} 
    on:mouseover={toggleSidebar} 
    on:mouseout={toggleSidebar}
    on:focus={toggleSidebar}
    on:blur={toggleSidebar}
  >
    <div class="Sidebar-logo">
      <img src='assets/logo.svg' alt="passify-logo">
      <h1>Pass<em>’ify</em></h1>
    </div>
    <div class="Sidebar-item-container">
      <ul class="Sidebar-item-list">
        {#each items as item}
          <li 
            class={`Sidebar-item-value ${selectedItem === item.key ? 'selected' : ''}`}
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
    <slot></slot>
  </div>
</div>

<style>
	.Sidebar {
		display: flex;
	}

  .Sidebar-elements {
    width: 240px;
    height: 100vh;
    background-color: var(--primary);
    transition: width 0.4s ease-in-out;
  }

  .Sidebar-elements.close {
    width: 80px;
  }

  .Sidebar-content {
    width: calc(100vw - 240px);
    height: 100vh;
    background-color: var(--tertiary);
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
    transition: opacity .2s linear;
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
    opacity: .6;
  }

  .Sidebar-item-value:hover {
    opacity: .6;
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
    transition: opacity .2s linear;
  }
</style>