<script lang="ts">
	import type { Category } from '$lib/model/category';

	interface Props {
		categories: Category[];
		states: {
			current_category: number;
		};
	}

	let { categories, states }: Props = $props();
	let order_count = $state(0);
	const add_order = () => {
		order_count += 1;
	};
</script>

<nav class="fixed top-0 flex h-screen w-1/4 flex-col items-stretch bg-white p-4 shadow">
	<h1 class="text-4xl font-bold">MoreCoffee</h1>
	<section class="drop-shadow-x mt-8 flex flex-col rounded-2xl p-2">
		<h3 class="mb-2 text-xl font-semibold">Category</h3>
		<ul class="flex flex-col gap-1 *:rounded-lg *:p-2 *:hover:category-active *:hover:duration-150">
			{#each categories as category}
				<!-- content here -->
				{#if category.id == states.current_category}
					<!-- content here -->
					<li class="category-active">
						<button>{category.name}</button>
					</li>
				{:else}
					<!-- else content here -->
					<li class="">
						<button
							onclick={() => {
								states.current_category = category.id;
							}}>{category.name}</button
						>
					</li>
				{/if}
			{/each}
		</ul>
	</section>
	<button class="mt-auto rounded-xl bg-black py-2 text-2xl font-bold text-white" onclick={add_order}
		>Order ({order_count})</button
	>
</nav>
