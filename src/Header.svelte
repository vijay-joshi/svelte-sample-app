<script>
    import {headerLinks} from './store/store.js';

    let links;

    headerLinks.subscribe(value => {
        links = value;
    })
</script>

      <nav class="navbar navbar-expand-lg navbar-light bg-light border-bottom">
        <button class="btn btn-primary" id="menu-toggle" on:click>Toggle Menu</button>

        <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>

        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <ul class="navbar-nav ml-auto mt-2 mt-lg-0">
            {#each links as link}
                <li class="nav-item active">
                    <a class="nav-link" href="#">{link}</a>
                </li>
            {/each}
          </ul>
        </div>
      </nav>
