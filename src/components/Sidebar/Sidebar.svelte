<script>
  import items from './Items';
  let sidebarClosed = true

  const toggleSidebar = () => sidebarClosed = !sidebarClosed;

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
          <li class="Sidebar-item-value">
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
    transition: all 0.5s ease-out;
  }

  .Sidebar-elements.close {
    width: 117px;
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
    margin-left: 20px;
    width: 90%;
    transition: all 0.5s ease;
  }

  .Sidebar-elements.close .Sidebar-logo h1 {
    visibility: hidden;
  }

  .Sidebar-logo img {
    width: 70px;
    height: 80px;
  }

  .Sidebar-logo h1 {
    color: var(--secondary);
    margin-left: 15px;
  }

  .Sidebar-logo h1 em {
    color: var(--tertiary);
    font-style: normal;
  }
  
  .Sidebar-item-list {
    padding: 30px;
    width: 85%;
  }

  .Sidebar-item-value {
    list-style-type: none;
    display: flex;
    align-items: center;
    justify-content: flex-start;
    width: 80%;
    margin-top: 30px;
    cursor: pointer;
    transition: all 0.5s ease;
    padding: 10px;
    border-radius: 10px;
  }

  .Sidebar-item-value:hover {
    opacity: .6;
  }

  .Sidebar-item-value i {
    font-size: 30px;
    color: var(--tertiary);
  }

  .Sidebar-item-value span {
    font-size: 18px;
    font-weight: 500;
    color: var(--tertiary);
    text-transform: uppercase;
    margin-left: 10px;
  }

  .Sidebar-elements.close .Sidebar-item-value span {
    visibility: hidden;
  }
</style>