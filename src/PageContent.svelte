<script>
    import {headerLinks} from './store/store.js';
    import { createEventDispatcher } from 'svelte';

	const dispatch = createEventDispatcher();

    let menuItem = '';

	function addMenuItem() {
		dispatch('message', {
			text: menuItem
		});
    }
    

    let mainMenuItem = '';
    let links;
    headerLinks.subscribe(value => {
        links = value;
    });

    function addMainMenuItem() {
        links.push(mainMenuItem);
        headerLinks.update(() => links);
    }

</script>

      <div class="container-fluid">
        <h1 class="mt-4">Some heading</h1>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque vitae tempus nisi. Sed laoreet ex et sem interdum vehicula. Praesent eget placerat massa, a finibus est. Maecenas tempus ac magna eu suscipit. Donec congue nunc commodo, fringilla nulla quis, tempus massa. Donec facilisis, purus vel fermentum malesuada, elit nisl aliquet dui, ut aliquet lectus nibh vitae nibh. Quisque semper lectus ligula, non ornare quam laoreet vitae. Fusce congue risus diam, sed euismod ex hendrerit in. Maecenas in nulla felis. Maecenas accumsan lacus in massa tincidunt dapibus. Praesent tincidunt ante in commodo commodo. Morbi nec velit pulvinar, tristique odio quis, porta ante.</p>

        <p>Add sidebar item: <input bind:value={menuItem}>  <button on:click={addMenuItem}>Add this</button></p>

        <p>Add header item: <input bind:value={mainMenuItem}>  <button on:click={addMainMenuItem}>Add this</button></p>

      </div>