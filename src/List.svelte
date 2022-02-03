<script>
	export let name;
	export let carrier;
	export let url;
	export let index;

	export let list;

	function removeFromList(index) {
    list.splice(index, 1)
    list = list;
    localStorage.list = JSON.stringify(list);
  }

  function openLink(url) {
    window.open(url, '_blank');
  }
</script>

<div class="box">
	<h5 class="name">{name[0].toUpperCase() + name.substring(1)} | {carrier} </h5>
    <button class="remove" on:click={() => openLink(url)}>View</button>
    <button class="remove" on:click={() => removeFromList(index)}>Remove</button>
</div>

<style>
	.box {
		min-width: 200px;
		max-width: 250px;
		border: 1px solid #aaa;
		border-radius: 2px;
		box-shadow: 2px 2px 8px rgba(0,0,0,0.1);
		padding: 1em;
		margin: 20px auto 0px;
        width: 50%;
    
	}
</style>