<script>
    let newItem = '';
	
    let todoList = [];
	
	function addToList() {
		todoList = [...todoList, {text: newItem, status: false}];
		newItem = '';
	}
	
	function removeFromList(index) {
		todoList.splice(index, 1)
		todoList = todoList;
    }
</script>

		<input width="50%" class="center" bind:value={newItem} type="text" placeholder="Insertar item">
		<button class="button" on:click={addToList}>+</button>

<br/>
{#each todoList as item, index}
	<input bind:checked={item.status} type="checkbox">
	<span class:checked={item.status}>{item.text}</span>
	<input on:click={() => removeFromList(index)} type="checkbox"> 
<br/>
{/each} 


<style> 
	.checked {
        text-decoration: line-through;
    }
		
	.center{
		text-align: center;
		margin-left: auto;
		margin-right: auto;
		vertical-align: middle 
	}
		
	.button{
		background-color: #40a8c4;
		width: 40px;
		height: 40px;
		border-radius: 20px;		
	}
</style>