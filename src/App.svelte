<script>
  import Input from './Input.svelte'
</script>

<main>
  <h1>[ some name here ]</h1>
  <!-- <p>Save all your packages in one place</p> -->
  <Input />
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
