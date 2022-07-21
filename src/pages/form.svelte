<Page name="form" id="page-form">
  <Navbar title="Form" backLink="Back"></Navbar>

  <!-- WORKS -->
  <img data-src="https://cdn.framework7.io/placeholder/nature-500x500-2.jpg" width="150" height="150"
    alt=""
    class="lazy lazy-fade-in demo-lazy"
    style="border: 2px solid red;" />

  {#await promise}
    LOADING
  {:then}
    <!-- DONT WORKS -->
    <img data-src="https://cdn.framework7.io/placeholder/nature-500x500-1.jpg" width="150" height="150"
    alt=""
    class="lazy lazy-fade-in demo-lazy"
    style="border: 2px solid red;" />
  {/await}

</Page>
<script>
  import {
    Page,
    Navbar,
  } from 'framework7-svelte';

  import { f7 } from 'framework7-svelte';
  import { $ as d7 } from 'dom7';

  async function load() {
    const pageEl = d7('#page-form');
    console.log("PAGE EL FROM SELECTIONS")
    console.log(pageEl);

    f7.lazy.create('#page-form');
    d7('img.lazy').trigger('lazy');

    console.log("DONE")
  }

  let promise = load();
</script>
