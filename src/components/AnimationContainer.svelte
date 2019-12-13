<script>
	let boutons = [
		"Règlement", 
		"FAQ", 
		"Contact", 
		"Archives"
	]

</script>

<style>
	div{
		border: 1px solid black;
		width: 100%;
		min-height: 250px;
	}
	ul{
		list-style: none;
		padding: 0;
		margin: 0;
	}
	button{
		width: 125px;
		margin: 15px;
	}
</style>

<div>
	<div>
		{#each boutons as x}
		<ul>
			<li>
				<button>{x}</button>
			</li>
		</ul>
			
		{/each}
	</div>
	<div></div>
</div>