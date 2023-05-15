<svelte:options tag="my-card" />

<script lang="ts">
	export let name = "svelte";
	export let self: HTMLDivElement;
	function sayMyName() {
		alert(name);
		self.dispatchEvent(
			new CustomEvent("done", {
				detail: "anything"
			})
		);
	}
</script>

<div id="app" bind:this={self}>
	<h1 class="name">{name}</h1>
	<button on:click={sayMyName}>呼唤我的名字</button>
</div>

<style>
	#app .name {
		color: red;
	}
</style>
