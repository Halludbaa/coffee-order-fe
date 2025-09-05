<script lang="ts">
	import Navbar from '../components/navbar.svelte';
	import type { Category } from '$lib/model/category';
	import type { Product } from '$lib/model/product';

	let current_category = $state(0);

	const products: Product[] = [
		{
			name: 'Latte',
			price: 25_000
		},
		{
			name: 'Cappucino',
			price: 25_000
		},
		{
			name: 'Espresso',
			price: 25_000
		},
		{
			name: 'Machiato',
			price: 25_000
		}
	];

	let idx = 0;
	const categories: Category[] = [
		{
			id: idx++,
			name: 'Coffee'
		},
		{
			id: idx++,
			name: 'Matcha'
		},
		{
			id: idx++,
			name: 'Milk base'
		},
		{
			id: idx++,
			name: 'Dessert'
		}
	];

	const format_idr = (amount: number): String => {
		return 'Rp' + amount.toLocaleString('id-ID');
	};

	$inspect(current_category);
</script>

<Navbar {categories} states={{ current_category }} />

<main class="ml-[25%] h-screen bg-slate-50 px-4 py-2">
	<h3 class="py-8 text-2xl font-bold">
		{categories.find((category) => category.id == current_category)?.name}
	</h3>
	<button onclick={() => (current_category += 1)}>Click This</button>
	<section class="grid grid-cols-3 gap-4 *:h-80 *:rounded-lg *:bg-white *:shadow">
		{#each products as product}
			<div class="">
				<div class="h-60 w-full rounded-t-lg bg-gray-300">
					<!-- image -->
				</div>
				<div class="flex w-full flex-col p-2">
					<span class="block text-lg font-medium">{product.name}</span>
					<span class="mt-auto block text-lg font-semibold">{format_idr(product.price)}</span>
				</div>
			</div>
		{/each}
	</section>
</main>
