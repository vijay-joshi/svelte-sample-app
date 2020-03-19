<script>
    export let newMenuItem;
    let menuItems = ['Dashboard', 'Overview', 'Events', 'Profile', 'Status'];

    function updateMenuItems(newMenuItem) {
        if(newMenuItem !== '') {
            menuItems = [...menuItems, newMenuItem];
        }
    }

    $: updateMenuItems(newMenuItem);

</script>

    <!-- Sidebar -->
    <div class="bg-light border-right" id="sidebar-wrapper">
      <div class="list-group list-group-flush">
      {#each menuItems as item }
       <a href="#" class="list-group-item list-group-item-action bg-light">{item}</a>
      {/each}
      </div>
    </div>
    <!-- /#sidebar-wrapper -->

<style>
#sidebar-wrapper {
  min-height: 100vh;
  margin-left: -15rem;
  -webkit-transition: margin .25s ease-out;
  -moz-transition: margin .25s ease-out;
  -o-transition: margin .25s ease-out;
  transition: margin .25s ease-out;
}

#sidebar-wrapper .sidebar-heading {
  padding: 0.875rem 1.25rem;
  font-size: 1.2rem;
}

#sidebar-wrapper .list-group {
  width: 15rem;
}

#page-content-wrapper {
  min-width: 100vw;
}

#wrapper.toggled #sidebar-wrapper {
  margin-left: 0;
}

@media (min-width: 768px) {
  #sidebar-wrapper {
    margin-left: 0;
  }

  #page-content-wrapper {
    min-width: 0;
    width: 100%;
  }

  #wrapper.toggled #sidebar-wrapper {
    margin-left: -15rem;
  }
}

</style>