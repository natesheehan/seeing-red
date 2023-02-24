<script>
	import zoom from './zoom'
	import { fade, slide } from 'svelte/transition'
	import { sineIn, quintInOut } from 'svelte/easing'
	
	export let product
	export let selected
	
	let node
</script>

<li class:selected on:click bind:this={node}>
	<h2>{product.title}</h2>
</li>

{#if selected}
	<div in:zoom={{node, delay: 0, easing: quintInOut}} out:zoom={{node, delay: 400, easing: quintInOut}} class="expanded-view" on:click>
		<img src="images/long johns and jacket.png" style="height:40vh" alt="">
        <h2>{product.title}</h2>
		<span in:fade={{delay: 300}} out:fade={{delay: 0}} class="price">
			{product.price.toLocaleString('en-US', {style: 'currency', currency: 'USD'})}
		</span>
		
		<footer in:slide={{delay: 600}} out:slide={{delay: 0}}>
			<button>Buy Now</button>
		</footer>
	</div>
{/if}

<style>
	li, .expanded-view {
		width: 200px;
		height: 200px;
		border: solid 1px #ccc;
		background: #eee;
		border-radius: 3px;
	}
	
	li {
		display: flex;
		justify-content: center;
		align-items: center;
		transition: all 0.3s;
		cursor: pointer;
	}
	li:hover {
		border-color: indigo;
		background: #fff;
	}
	
	.expanded-view {
		position: absolute;
		top: 0px;
		left: 0px;
		background: #eee;
		
		padding: 2rem;
	}
	.expanded-view h2 {
		transition: all 0.3s;
	}
	.price {
		font-size: 2rem;
	}
	
	:global(.expanded-view.expanding h2) {
		font-size: 4rem
	}
	
	footer {
		width: 100%;
		position: fixed;
		bottom: 0px;
		padding: 1rem 0;
	}
	
	footer button {
		width: calc(100vw - 4rem);
    margin: 0 0 1rem 0;
    font-size: 3rem;
		background: teal;
		color: #eee;
		border-radius: 15px;
	}
</style>