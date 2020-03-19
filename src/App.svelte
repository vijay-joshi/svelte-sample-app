<script>
	import Header from './Header.svelte';
	import Sidebar from './Sidebar.svelte';
	import PageContent from './PageContent.svelte';
	let sidebarOpen = true;
	let newMenuItem = '';

	function handleMessage(event) {
		newMenuItem = event.detail.text;
	}

</script>

  <div class="d-flex" id="wrapper">

	{#if sidebarOpen}
		<Sidebar newMenuItem={newMenuItem}></Sidebar>
	{/if}
    <!-- Page Content -->
    <div id="page-content-wrapper">

	<Header on:click={ e => { sidebarOpen = !sidebarOpen } }></Header>

	<PageContent on:message={handleMessage}></PageContent>

    </div>
    <!-- /#page-content-wrapper -->

  </div>
  <!-- /#wrapper -->

<style>

</style>