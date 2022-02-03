<script>
  import { returnUrl } from './Urls.svelte'
  import List from './List.svelte'

  let carriers = [
    'USPS',
    'UPS',
    'FedEx',
    'DHL',
    'OnTrac',
    'Canada Post',
    'Royal Mail',
  ]

  let tracking = ''
  let name = ''
  let selectedCarrier = 'USPS'

  var list = [];

  if (localStorage.getItem("list") === null) {
    localStorage.list = JSON.stringify(list); 
  } else {
    list = JSON.parse(localStorage.getItem("list"));
  }

	$: view = list;

  function addToList() {
    list = [
      { carrier: selectedCarrier, tracking: tracking, name: name },
      ...list,
    ]

    localStorage.list = JSON.stringify(list);

    tracking = ''
    name = ''
    
  }
</script>

<select bind:value={selectedCarrier}>
  {#each carriers as carrier}
    <option value={carrier}>{carrier}</option>
  {/each}
</select>
<input bind:value={tracking} type="text" placeholder="tracking number" />
<input bind:value={name} type="text" placeholder="name/description" />
<button on:click={addToList}>Add</button>


{#each list as item, index}
  <List bind:list={list} name={item.name} carrier={item.carrier} url={returnUrl(item.carrier, item.tracking)} index={index}/>
{/each}

<style>
</style>
