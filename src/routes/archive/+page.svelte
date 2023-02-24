<script>
	import Product from "../../components/product.svelte";
	
	const products = [
		{ title: "2022", price: 19 },
		{ title: "2021", price: 39 },
        { title: "2020", price: 39 },
        { title: "2019", price: 39 },
        { title: "2018", price: 39 },
	]
	
	let selected = null
	
	function toggle(product) {
		selected = selected == product ? null : product
	}
</script>

<main>
	<h1>Archive</h1>
	<p>Example of a custom Svelte transition that zooms content.</p>
	
	<ul>
		{#each products as product}
			<Product {product} selected={selected == product} on:click={() => toggle(product)}/>
		{/each}
	</ul>
</main>
		
<style>
    body{
  background-image: url("/images/Scan 5.jpeg") !important;
  background-size: 200vh;;
  height: 50vh;  
  margin: 0px;
  overflow: hidden;
 }
	
	:global(*) {
		box-sizing: border-box;
	}
	
	h1, p {
		text-align: center;	
	}
	
	ul {
		list-style: none;
		padding: 0;
		display: flex;
		flex-wrap: wrap;
		align-items: center;
		justify-content: center;
		gap: 2rem;
		margin: 3rem 0;
	}
</style>