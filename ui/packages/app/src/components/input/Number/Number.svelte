<script lang="ts">
	export let value: number;
	export let setValue: (val: number) => number;
	export let theme: string;

	function handle_input(event: Event) {
		setValue(parseFloat((event.target as HTMLInputElement).value));
	}
</script>

<input
	type="number"
	class="input-number w-full rounded box-border p-2 focus:outline-none appearance-none"
	{value}
	on:input={handle_input}
	{theme}
/>

<style lang="postcss" global>
	input::-webkit-outer-spin-button,
	input::-webkit-inner-spin-button {
		-webkit-appearance: none;
		margin: 0;
	}
	input[type="number"] {
		-moz-appearance: textfield;
	}
	.input-number[theme="default"] {
		@apply shadow transition hover:shadow-md dark:bg-gray-800;
	}
</style>
