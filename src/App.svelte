<script>
	let name = 'Joseph';
	let beltColour = 'black';
	let magicColor = 'blue';
	let firstName = 'Josh';
	let lastName = 'Wang';

	$: fullName = `${firstName} ${lastName}`;
	$: console.log(beltColour);

	const handleClick = () => {
		beltColour = 'orange';
		alert(name);
	};

	const handleInput = (e) => {
		beltColour = e.target.value;
	};

	let people = [
		{name:'yoshi', beltColour:'black',age:15, id:1},
		{name:'mario', beltColour:'orange',age:23, id:2},
		{name:'loigo', beltColour:'brown',age:21, id:3}
	]
</script>

<main>
	<h1>Hello {name}!</h1>
	<h1>{fullName} belt</h1>
	<h1>{beltColour} belt</h1>
	<h1>{magicColor}</h1>
	<p style="color:{magicColor}">aaaa</p>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
	<button on:click={handleClick}>Let's Click</button>
	<input type="text" on:input={handleInput} value={beltColour}>
	<input type="text" bind:value={magicColor}>
	{#each people as person (person.id)}
	<div>
		<h4>{person.name}</h4>
		<p>{person.age} years old, {person.beltColour} belt.</p>
	</div>
	{:else}
		<p>There are no people to show...</p>
	{/each}
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