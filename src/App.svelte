<script>
import {writableArray} from './store.js';
let count = 0;
let type = '';
let types = [];

const addToArray = () => {
	$writableArray = [...$writableArray,type ];
}
function handleSubmit(){
	console.log("handle submit");
	return false;
}

const handleKeyup = ()  =>{
	console.log("key up");
	if(event.code  == 'Enter') {
		event.preventDefault();
		addToArray();
		type ='';
		return false;
	}
}
</script>

<main>
<h1>1000 times allah</h1>
<form on:submit|preventDefault={handleSubmit}>

<input type="text" name="times" bind:value={type} 
	autocomplete="off"
	on:keyup|preventDefault={handleKeyup}>
</form>
<div class="board">
Count: {$writableArray.length}
{#each $writableArray as type, index}
	<div>{index+1 } {type}</div>
{/each}
</div>
</main>

<style>
</style>